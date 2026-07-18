---
name: generating-project-docs
description: Use when a project has a source document (PRD, proposal, brief, spec, SRS, client email, meeting notes) and needs standard planning documents created — requirements, architecture, rules, phases, design, and memory files. Also use when asked to "set up project docs", "bootstrap the docs folder", or prepare a project for AI-assisted development.
---

# Generating Project Docs

## Overview

Transform ONE source document into SIX standard planning documents that give any developer (human or AI) full project context. Every statement in the generated docs must be traceable to the source, explicitly marked as an assumption, or flagged as a gap. **Never silently invent facts.**

## When to Use

- A PRD, proposal, brief, spec, or requirements email exists and the project needs structured docs
- Starting AI-assisted development and the project needs persistent context files
- Onboarding docs are requested for an existing project (use the codebase itself as the source document)

**When NOT to use:** No source material exists at all — gather requirements first (interview the user), then use this skill on the notes.

## The Six Documents

Generate into `docs/` (or the folder the user specifies), in this order — later docs reference earlier ones:

| Order | File | Answers | Template |
|-------|------|---------|----------|
| 1 | `Project-Requirement.md` | WHAT to build and WHY | [templates/project-requirement.md](templates/project-requirement.md) |
| 2 | `Architecture.md` | HOW it's structured technically | [templates/architecture.md](templates/architecture.md) |
| 3 | `Design.md` | WHAT it looks like, how users flow through it | [templates/design.md](templates/design.md) |
| 4 | `Rules.md` | HOW to write code for it (conventions, standards) | [templates/rules.md](templates/rules.md) |
| 5 | `Phases.md` | WHEN things get built (order, milestones) | [templates/phases.md](templates/phases.md) |
| 6 | `Memory.md` | WHERE the project stands right now (living context) | [templates/memory.md](templates/memory.md) |

## Process

1. **Read the source document completely** before writing anything. Multiple sources? Read all, note conflicts.
2. **Extract and classify** every fact into the six buckets above. One fact can land in multiple docs.
3. **Mark provenance** as you write:
   - Plain text — stated in the source
   - `*(assumed)*` — reasonable inference; state the reasoning
   - `> ⚠ GAP:` — required information the source doesn't provide
4. **Resolve gaps before generating** — if critical gaps exist (unknown tech stack, unclear target users, no success criteria), ask the user first. Minor gaps stay as `⚠ GAP` markers in the docs.
5. **Generate all six docs from the templates.** Fill every section; write `_Not specified in source._` rather than deleting a section or inventing content. Delete only sections that are genuinely inapplicable (e.g., UI sections for a headless API).
6. **Cross-link** — requirement IDs (FR-1, NFR-2) defined in Project-Requirement.md are referenced by ID everywhere else; phases reference requirement IDs they deliver.
7. **Verify** — checklist:
   - [ ] All six files exist and every template section is filled or explicitly marked
   - [ ] No fact appears that is absent from the source and unmarked
   - [ ] Requirement IDs are unique and referenced consistently
   - [ ] Memory.md "Current status" says the project is at documentation stage
8. **Report** — list the files created, the assumptions made, and the open gaps needing the user's answers.

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Inventing a tech stack because the source omits one | Ask the user, or mark `⚠ GAP` in Architecture.md |
| Copying the same paragraphs into all six docs | Each doc answers a different question; cross-reference by ID instead |
| Writing Memory.md as a static summary | It's a living file with an update protocol — follow its template |
| Skipping "boring" sections (NFRs, out-of-scope) | These prevent the most rework; fill or mark them |
| Generating docs before reading the whole source | Later sections change interpretation of earlier ones |
