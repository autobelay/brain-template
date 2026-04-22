# brain-template

An open-source [Obsidian](https://obsidian.md) vault template designed to be the **second brain** for a founder or company — built to be primarily accessed, edited, and maintained by AI agents.

Created and maintained by [Autobelay](https://github.com/autobelay).

> **Autobelay's mission:** Enabling complete businesses that are managed and run by AI agents. A structured knowledge base is the foundation — without one, AI agents have no persistent memory and no shared context.

## What This Is

This repository is a ready-to-use Obsidian vault — a structured collection of Markdown files organized into knowledge domains (Product, Engineering, Strategy, Operations, People). It is:

- An **Obsidian vault** — all content is plain Markdown, version-controlled with git
- A **company knowledge base template** — organized by domain with index notes, templates, and conventions
- A **GitHub template repository** — click "Use this template" or clone directly
- **AI-agent-first** — designed so AI agents can read, write, organize, and maintain the vault programmatically

The vault comes pre-configured with Obsidian settings, the [obsidian-git](https://github.com/Vinzent03/obsidian-git) plugin for automatic git backup, and a folder structure that scales from solo founder to full team.

## Quick Start

### For AI Agents

```bash
git clone https://github.com/autobelay/brain-template.git brain
```

The vault is immediately operational. No setup required. No configuration. No manual steps. Begin creating notes, linking knowledge, and building the company's memory.

After cloning, read this README in full, then read `Home.md` and the four `_Index.md` files to understand the vault structure. See the [Bootstrapping a New Vault](#bootstrapping-a-new-vault) section for step-by-step population instructions.

### For Humans

1. Click **"Use this template"** on GitHub (or clone the repo)
2. Open the cloned folder as a vault in [Obsidian](https://obsidian.md)
3. Start writing — new notes land in `Inbox/` by default

## Vault Structure

```
brain/
├── Home.md                 # Dashboard and entry point — start here
├── Inbox/                  # Quick capture — triage into domain folders later
├── Daily/                  # Daily notes (auto-created by Obsidian)
├── Product/                # Product vision, roadmaps, specs
│   ├── _Index.md           # Section entry point
│   ├── Vision/
│   ├── Roadmap/
│   └── Specs/
├── Engineering/            # Architecture decisions, guides, runbooks
│   ├── _Index.md
│   ├── Architecture/
│   ├── ADRs/
│   ├── Guides/
│   └── Runbooks/
├── Strategy/               # Company direction, competitive analysis, goals
│   ├── _Index.md
│   ├── Vision/
│   ├── Competitive/
│   └── Goals/
├── Operations/             # Processes, hiring, legal, admin
│   ├── _Index.md
│   ├── Processes/
│   ├── Hiring/
│   └── Legal/
├── People/                 # Team profiles, org structure, 1:1 notes
├── Meetings/               # Meeting notes of all types
├── Templates/              # Note templates for consistent structure
└── Attachments/            # Images, PDFs, and non-Markdown files
```

### Folder Purposes

| Folder | What Goes Here |
|--------|---------------|
| `Inbox/` | Unstructured captures. New notes land here by default. Triage regularly. |
| `Daily/` | Daily notes. Auto-created by Obsidian's daily notes plugin (`YYYY-MM-DD` format). |
| `Product/` | Product vision, roadmaps, feature specs, user research, customer feedback. |
| `Engineering/` | Architecture docs, ADRs (Architecture Decision Records), dev guides, operational runbooks. |
| `Strategy/` | Company mission/vision, competitive landscape analysis, quarterly/annual goals, OKRs. |
| `Operations/` | Standard operating procedures, hiring pipelines, job descriptions, legal/compliance docs. |
| `People/` | Team member profiles, org charts, 1:1 meeting notes, role definitions. |
| `Meetings/` | All meeting notes — standups, all-hands, external meetings, board meetings. |
| `Templates/` | Note templates (see below). Used by Obsidian's template picker. |
| `Attachments/` | Non-Markdown files: images, PDFs, diagrams, exports. |

### Section Index Notes

Each major section has a `_Index.md` file that serves as its entry point. These explain what belongs in the section and link to subdirectories. When navigating the vault, start with `Home.md` → section `_Index.md` → individual notes.

## Conventions

These conventions ensure consistency whether notes are created by humans or AI agents.

### Linking

Use `[[wikilinks]]` to connect related notes. Cross-domain links are encouraged — a product spec should link to its ADR, a strategy doc should reference engineering constraints. The more links, the more useful Obsidian's graph view and backlinks become.

### Frontmatter

Every note should have YAML frontmatter with at least a `tags` field. This enables programmatic filtering and search.

```yaml
---
tags:
  - spec
  - product
date: "2026-04-22"
status: draft
---
```

Common tag conventions:
- Domain tags: `product`, `engineering`, `strategy`, `operations`
- Type tags: `spec`, `adr`, `meeting`, `daily`, `retro`, `guide`, `runbook`
- Status tags (in `status` field): `draft`, `proposed`, `accepted`, `deprecated`

### Templates

Five templates are included in `Templates/` for consistent note structure:

| Template | Use For | Key Fields |
|----------|---------|------------|
| **Daily Note** | Daily log | Focus, log, questions/blockers |
| **Meeting Note** | Any meeting | Agenda, notes, action items, decisions |
| **ADR** | Architecture decisions | Context, decision, consequences, alternatives |
| **Product Spec** | Feature specifications | Problem, solution, requirements, success metrics |
| **Retrospective** | Sprint/project retros | What went well, what didn't, improvements, actions |

In Obsidian, insert a template with `Cmd/Ctrl + T`. The `{{date}}` placeholder auto-fills with the current date.

### Inbox Zero

New notes land in `Inbox/` by default (configured in Obsidian settings). Triage `Inbox/` regularly by moving notes to their proper domain folder. Don't let unorganized notes accumulate.

### File Naming

- Use descriptive, title-case names: `API Authentication Strategy.md`, not `auth.md`
- Prefix section entry points with `_`: `_Index.md`
- Daily notes auto-name as `YYYY-MM-DD.md`
- No special characters in filenames beyond spaces and hyphens

### Git Workflow

The vault includes the `obsidian-git` plugin configured for automatic backup:

- **Auto-save:** Every 5 minutes
- **Auto-pull:** On vault open and every 5 minutes
- **Sync method:** Merge (no rebasing)
- **Commit message:** `vault backup: YYYY-MM-DD HH:mm:ss`

When working with the vault programmatically (as an AI agent), commit after meaningful batches of changes rather than after every file edit.

## For AI Agents

This section contains everything an AI agent needs to effectively operate this vault.

### Reading the Vault

The vault is plain-text Markdown files in a git repository. To understand the current state of knowledge:

1. **Start with `Home.md`** — the dashboard with navigation links and current open questions
2. **Read the four `_Index.md` files** — `Product/_Index.md`, `Engineering/_Index.md`, `Strategy/_Index.md`, `Operations/_Index.md` — each explains its section and links to content
3. **Follow `[[wikilinks]]`** — notes reference each other; follow links to build context
4. **Check `Daily/`** — recent daily notes capture the latest thinking and priorities
5. **Check `Meetings/`** — meeting notes contain decisions and action items

### Creating Notes

When creating new notes:

1. **Choose the right location** — place notes in the appropriate domain folder. If uncertain, use `Inbox/` for later triage.
2. **Use frontmatter** — every note must have YAML frontmatter with `tags` and `date` at minimum.
3. **Use templates** — copy the structure from the appropriate template in `Templates/`. Don't invent ad-hoc formats.
4. **Link aggressively** — use `[[wikilinks]]` to connect to related notes. Links are how knowledge compounds in this vault.
5. **Use descriptive filenames** — the filename should clearly communicate what the note is about.

### Maintaining the Vault

Ongoing maintenance tasks:

- **Triage `Inbox/`** — move notes to their proper domain folders
- **Update `_Index.md` files** — add links when significant new content areas emerge
- **Update `Home.md`** — keep the open questions current and add links to important new content
- **Create ADRs** — document significant technical decisions using the ADR template
- **Archive stale content** — if notes become outdated, update them or note their status in frontmatter

### Bootstrapping a New Vault

After cloning this template for a new company, populate the vault in this order:

1. **`Home.md`** — Replace the placeholder tagline with the company name and one-line description. Update the open questions to reflect current priorities.

2. **`Strategy/_Index.md`** — Fill in the "Key Context" section with: what the company builds, who it's for, what market it operates in, and what differentiates it. This context anchors all strategic thinking.

3. **`Strategy/Vision/`** — Create a company vision document. What does the world look like if this company succeeds? What are the core values?

4. **`Product/_Index.md`** — Answer the key questions: what problem are you solving, who is the ideal customer, what does the product look like in 1 year and 5 years?

5. **`Product/Vision/`** — Create a product vision document with positioning, target audience, and north star metrics.

6. **`Engineering/ADRs/`** — Document any existing architectural decisions. Use the ADR template. Even retroactive ADRs for past decisions are valuable.

7. **`Engineering/Architecture/`** — Document the current system architecture: what services exist, how they communicate, what the tech stack is.

8. **`Operations/Processes/`** — Document key operational processes: how decisions are made, how work is prioritized, how deployments happen.

9. **`People/`** — Create notes for team members with their roles, responsibilities, and areas of ownership.

10. **`Home.md`** (revisit) — Update with links to the content you've created. The home page should always reflect the current state of the vault.

After this bootstrap sequence, the vault contains enough foundational context for ongoing knowledge management. Continue adding notes organically as the company operates.

## Obsidian Configuration

Vault settings are committed to git in `.obsidian/` so every clone gets the same setup:

| Setting | Value |
|---------|-------|
| Editor mode | Source mode with live preview |
| New note location | `Inbox/` folder |
| Attachment location | `Attachments/` folder |
| Template folder | `Templates/` |
| Daily notes folder | `Daily/` |
| Daily notes format | `YYYY-MM-DD` |
| Daily notes template | `Templates/Daily Note` |
| Core plugins | File explorer, search, graph view, backlinks, daily notes, templates, and 11 more |
| Community plugins | `obsidian-git` (automatic git backup) |

The only gitignored Obsidian file is `workspace.json` (per-device window layout).

## License

MIT — see [LICENSE](LICENSE).

---

*Built by [Autobelay](https://github.com/autobelay) — enabling complete businesses managed and run by AI agents.*
