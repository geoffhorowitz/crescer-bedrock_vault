# Project Management Mind Map

**Summary**: Visual mind map and index of the Bedrock x Crescer AI project management components, tracking files, and workflow relationships.

**Last updated**: 2026-07-28

---

## Mind Map

```mermaid
mindmap
  root((Bedrock Project Management))
    Open Items
      Active Action Items
      Task Statuses (Open / In-Progress / Resolved)
      Owner & Source Provenance
      File: open-items.md
    Decisions
      Architecture & Evaluation Strategy
      Data Splitting & Geographic Isolation
      Mag Fusion & Multi-Modal Design
      File: decisions.md
    Learnings
      Technical Pitfalls & Insights
      Model Overlap Fragmentation
      Dataset Coordinate Traps
      File: learnings.md
    Client Communications
      SOW Deliverables & Milestones
      Sync Reports & Demos
      Label Verification & Recall Preference
      File: bedrock-communications.md
    Roadmap & Tracking
      Short-Term Priorities (next_steps.md)
      Long-Term Technical Fixes (TODO.md)
      Repository Governance (AGENTS.md & best-practices.md)
```

---

## Component Breakdown

| Component File | Primary Function | What It Tracks |
| :--- | :--- | :--- |
| `open-items.md` | Action Items & Blockers | Unresolved tasks, data requests, owners, and progress status (`Open`, `In-Progress`, `Resolved`). |
| `decisions.md` | Governance & Strategy | Explicit engineering and product decisions, dated with full rationale. |
| `learnings.md` | Knowledge Retention | Non-obvious pitfalls, dataset quirks (e.g., S7K depth Z-axis orientation), and post-mortem findings. |
| `bedrock-communications.md` | Client Alignment | Sent reports, client requests/feedback, meeting notes, and SOW milestone acceptance records. |
| `next_steps.md` | Sprint Roadmap | Active domain-by-domain engineering priorities derived from recent syncs. |
| `TODO.md` | Technical Backlog | Known open issues, root causes, and long-term resolution plans for the engineering team. |

---

**Sources**: project_management/open-items.md; project_management/decisions.md; project_management/learnings.md; project_management/bedrock-communications.md
