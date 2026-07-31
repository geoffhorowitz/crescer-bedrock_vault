# Magnetometer Processing Pipeline

**Summary**: Technical details of Bedrock's magnetometer data processing workflow, including despiking, coefficient compensation, ambient-vs-residual separation, and threshold-based anomaly detection.

**Last updated**: 2026-07-21

---

## OBF File Format

The processed magnetometer data is delivered in OBF files from Bedrock's Mosaic cloud platform (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01). Each OBF record contains:
- Daytime, latitude, longitude
- Depth and altitude of the AUV
- Raw components: amplitude X, Y, Z (these are "raw_raw" — before coefficient compensation)
- Total field: computed from the three components
- Amplitude after despiking filter applied
- Motion data: roll, pitch, heading

The amplitude with coefficient compensation applied but no despiking is also available in the same file (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Processing Steps

The processing pipeline runs offline after data is loaded to the cloud (not onboard) (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01):

1. **Coefficient Compensation**: Corrects for vehicle-induced magnetic interference. Applied automatically with pre-tuned parameters that have been tested across multiple datasets. The filter is static and applied consistently across all survey lines (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

2. **Despiking**: Removes high-frequency noise from electrical interference with other sensors (multibeam, sub-bottom profiler). This is an automatic filter designed to keep the smooth version centered within high-frequency oscillations without losing detail (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

3. **Ambient Field Estimation**: A low-pass filter (rolling average/median) extracts the smooth, slowly varying Earth's magnetic field. The goal is to create a smooth baseline curve (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

4. **Residual Field**: Subtracting the ambient field from the total field yields the local field variations that indicate ferrous objects. The residual oscillates around zero, with negative-positive pairs for dipole targets (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

5. **Analytical Signal**: A derivative-based proxy that collapses positive and negative dipole responses into a single peak of maximum energy, making anomaly location easier to identify. Used instead of the raw residual for picking because the residual can show mixed positive/negative values depending on flight direction (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Threshold Standards

- **5 nanotesla**: Signals above this threshold warrant attention (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01)
- **10 nanotesla**: Signals above this threshold are anomalies automatically (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01)

These thresholds only make sense post-filtering. Unfiltered high-frequency spikes can reach 10-20 nT but are artificial vehicle noise, not real targets (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Anomaly Picking

Bedrock picks anomalies line by line from the processed data, then correlates them across sensors — bathymetry, sidescan sonar, and sub-bottom profiler — to distinguish pipelines from UXOs from rocks (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01). Magnetic analysis provides the ferrous component that other sensors cannot detect (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Altitude Effects

AUV altitude directly affects signal strength: the farther from the target, the smaller the magnetic reading (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01). Standard survey altitude for UXO-style surveys is 3-4 meters, but surveys with sidescan sonar as the primary sensor run higher at 6-7 meters (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01). Upward continuation can be used to interpolate the field and level lines to a consistent altitude.

## Onboard Considerations

Onboard the AUV, the data available is likely the raw_raw (uncompensated, unfiltered) stream. The despiking filter may be feasible to replicate onboard, but coefficient compensation presents a significant challenge as it requires vehicle-specific calibration parameters (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Map Grid Interpolation

Bedrock creates magnetic maps by grid-interpolating residual values across survey lines using inverse distance weighting. This produces a more complete surface than line-by-line viewing, but requires dense line spacing (4-5 meters) to avoid false information (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Amplitude Discrepancy

Ratul Shashank's pipeline reproduces Bedrock's anomaly detections at the correct locations, but peak amplitudes are 2 to 2.5 times greater than Bedrock's values. The results hold across both raw data with despiking and filtered amplitude-filtered data — both produce similarly elevated amplitudes. Geoff Horowitz expresses skepticism that raw data can replicate filtered results without Bedrock's offline calibration coefficients, but tentatively accepts the finding. The consensus is that relative signal presence matters more than absolute amplitude values for detection purposes, so the discrepancy is deprioritized pending validation (source: Aux Discussion Mag Data - 2026_07_17).

## Multiple Survey Passes Purpose

The purpose of multiple survey passes over the same area is to reduce measurement uncertainty. Geoff explicitly disagrees with the interpretation that repeated passes are primarily for vehicle magnetic field compensation — that is handled during a separate calibration step on flat, object-free seabed before the survey begins. Calibration includes testing sensors out of water and roaming flat seabed to capture vehicle and motor signatures. Multiple passes simply improve confidence that a reading is genuine (source: Aux Discussion Mag Data - 2026_07_17).

## Mag As Decision Factor, Not Binary Filter

Geoff emphasizes that magnetometer data should not be used as a binary filter to narrow the SSS search area. Non-ferrous objects and buried targets may produce no detectable mag signature, so filtering on mag alone would cause significant missed detections. Instead, mag data should serve as an additional channel that adjusts the model's confidence score — increasing confidence when a mag signal aligns with an SSS detection, decreasing when it doesn't (source: Aux Discussion Mag Data - 2026_07_17).

## MAG Data Client Meeting Exclusion

The team decided to exclude MAG data from the upcoming client meeting agenda (July 23) unless specific questions arise that require client input. Current location accuracy remains unchanged at a 5-10 m range. Geoff acknowledges the accuracy is still useful but prefers not to present it to Bedrock at this time (source: Iris Sync - 2026_07_20).

## MAG Visualization

Ratul Shashank to create 2-pane visualizations juxtaposing side-scan sonar imagery with MAG amplitude. The visualization will highlight the exact location of the amplitude peak on the SSS images, improving visual clarity for internal review (source: Iris Sync - 2026_07_20).

## S7K Multi-Beam Z-Axis Direction

The Z-axis in S7K/MBES point cloud data is positive downward: the ship position is at Z=0, and greater depth yields more positive Z values. Ratul initially interpreted positive Z as above sea level, which was the source of apparent depth discrepancies on the Rory McKenzie survey data (source: Aux Discussion Mag Data - 2026_07_17).

## S7K Sound Velocity Profile

The S7K file contains a sensor speed datagram that provides a crude approximation of the sound velocity profile. Using this datagram instead of a constant 1500 m/s for sound speed reduces positional deviation from the reference LAS file from ~8 cm to under 6 cm. The datagram captures surface-layer sound velocity; deeper water layers are not represented (source: Aux Discussion Mag Data - 2026_07_17).

## Related pages

- [[magnetometer-fusion]]
- [[data-quality-and-gaps]]
- [[bedrock-meeting-transcripts-summary]]

---

**Sources**: raw/meeting_transcripts/Bedrock__Crescer_ Mag Discussion - 2026_07_01; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17; raw/meeting_transcripts/Iris Sync - 2026_07_20
