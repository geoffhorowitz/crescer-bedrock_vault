# Best Practices

Running project-specific guidance the agent has learned while maintaining this repository.

## Maintenance rule

Keep this file to 256 lines or fewer. If adding a best practice would make the file longer than 256 lines, ask the user what to do before editing it.

## Practices

- Use `[[wiki-links]]` for navigation and `(source: filename)` citations for provenance; not every citation needs a wiki link.
- Link a concept page to a source-summary page only when that source is central to the concept.
- Keep `Related pages` focused on what a reader would likely click next, usually 4-8 links.
- Avoid linking the same term repeatedly in one page; link the first meaningful mention.
- Prefer fewer, useful links over graph density.
- **Single Source of Truth (SSOT)**: Restrict authoritative facts, parameters, or legal clauses to a single primary page. Other pages referencing those facts should summarize briefly and link to the primary page using `[[wiki-links]]`.
- **Scope-Reflective Naming**: Page titles must precisely match their scope. When splitting a topic across multiple dimensions (e.g., contractual requirements vs. technical implementation), use explicit suffixes in the filenames (e.g., `[topic]-requirements.md` vs. `[topic]-methods.md`) to prevent boundary ambiguity.
- **Separation of Concerns**: Keep catalogs or inventories of assets distinct from diagnostic or analytical reports of those assets (such as errors, data quality gaps, or pipeline issues). Connect them via links rather than merging them.
- **Dataset Terminology**: The dataset occasionally mislabeled as "ENTX" or "ENTx" in speech-to-text meeting transcripts is authoritatively **ANTX**. Always use **ANTX** across all wiki and project management documentation.
