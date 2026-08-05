# Project Management Guidance

Operating conventions for the `project_management/` folder.

## Files

The folder contains four files:

- `open-items.md` — Active and resolved action items, blockers, and follow-ups
- `learnings.md` — Lessons learned, pitfalls, and insights from execution
- `bedrock-communications.md` — Customer-facing updates, reports sent, and key messages
- `decisions.md` — Significant decisions with rationale and date

## When to update

When ingesting a source or answering a question, check for:

1. **Open items** — Any unresolved action items, requests for data, or pending client decisions. Add to `open-items.md` with source reference and status (open/in-progress/resolved).
2. **Learnings** — Any non-obvious insight about what worked, what didn't, or what surprised the team. Add to `learnings.md`.
3. **Decisions** — Any explicit decision made by the team or client. Add to `decisions.md` with the "why."
4. **Communications** — Any mention of reports sent to Bedrock, feedback received, or messages that shaped direction. Add to `bedrock-communications.md`.

## Wiki vs. project management

- The **wiki** is for concepts and technical knowledge (what ATR is, how the mag pipeline works, what the datasets are).
- **Project management** is for actions and process (who needs to do what, what was decided, what we learned, what we told the client).
- When uncertain, default to wiki for knowledge and project management for actions.

## Rules

- Keep entries concise: one paragraph per item, bulleted when possible.
- Date every entry.
- Reference the source file that contains the information.
- When an open item is resolved, mark it resolved with the date and brief note — do not delete it.
- Do not duplicate wiki content in project management files; link to wiki pages instead using `[[wiki-links]]`.
- Follow the same page name convention as the wiki: lowercase with hyphens where applicable.
