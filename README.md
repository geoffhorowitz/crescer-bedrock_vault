# Crescer Bedrock Vault

This repository contains the structured project management vault and LLM-maintained knowledge base for Crescer AI's sidescan sonar and magnetometer ATR project with Bedrock.

## Repository Structure

```
├── README.md                      # Repository overview and navigation
├── TODO.md                        # Open items and long-term technical fixes
├── AGENTS.md                      # LLM Wiki guidelines and citation rules
├── agent_guidance/
│   ├── best-practices.md          # LLM best practices (SSOT, scope-reflective naming)
│   └── project_management.md      # Operating rules for project management documents
├── project_management/            # Project actions and processes (Dated entries)
│   ├── bedrock-communications.md  # Client-facing updates and meeting records
│   ├── decisions.md               # Significant engineering and client decisions
│   ├── learnings.md               # Pitfalls, technical findings, and lessons learned
│   └── open-items.md              # Active and resolved action items
├── raw/                           # Raw client documents and meeting notes (Immutable)
└── wiki/                          # Concept pages and source summaries (Technical knowledge)
    ├── index.md                   # Wiki table of contents
    └── log.md                     # Wiki ingest and refactoring changelog
```

## How to Interact with this Repository

### Knowledge Base & Concepts
Technical knowledge, datasets, sensor details, and pipeline specifications are stored in `wiki/`.
- To get a high-level overview of concepts and source summaries, view the [[Wiki Index](file:///home/gh/gitrepos/crescer/bedrock_vault/wiki/index.md)].
- When writing code or updating models, reference `agent_guidance/best-practices.md` to ensure adherence to single-source-of-truth guidelines.

### Project Tracking & Governance
Action items, decisions, and meetings are tracked in `project_management/`.
- Refer to `agent_guidance/project_management.md` for conventions.
- Update `project_management/open-items.md` whenever an action item changes status.
- Document any client communication in `project_management/bedrock-communications.md`.
