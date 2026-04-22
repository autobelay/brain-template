# Agent Instructions

> This is your company knowledge base (Obsidian vault). It is the canonical source of truth for product vision, architecture, strategy, and operational knowledge.

## Git Discipline

**Commit early, commit often.** This vault is backed by git and synced via the Obsidian Git plugin.

- **Never leave uncommitted changes in the working directory.** After every meaningful edit — even a single document — stage and commit immediately.
- **Commit after every logical unit of work.** One document updated? Commit. A batch of related docs created? Commit. Don't accumulate uncommitted changes.
- **Write clear commit messages.** Summarize what changed and why. Follow the existing commit style (conventional-ish, lowercase, concise).
- **Push when possible.** If the branch tracks a remote, push after committing to keep the remote in sync.

## Vault Structure

```
Home.md                  — Landing page and navigation
Engineering/             — Architecture, ADRs, guides, runbooks
Product/                 — Vision, roadmaps, specs
Strategy/                — Company vision, competitive analysis, goals
Operations/              — Processes, hiring, legal
People/                  — Team directory
Meetings/                — Meeting notes
Daily/                   — Daily notes
Inbox/                   — Quick capture, triage later
Templates/               — Note templates (ADR, Product Spec, etc.)
Attachments/             — Images and file attachments
```

## Conventions

- **Obsidian wikilinks** (`[[Page Name]]`) for all internal links. This is how knowledge compounds.
- **Frontmatter** on every document: `tags`, `date`, `status` at minimum.
- **`_Index.md`** files in each section folder serve as the table of contents.
- **Templates** in `Templates/` — use them for structured notes (ADRs, specs, meeting notes).
- Prefer **editing existing files** over creating new ones unless the content is genuinely new.
- Keep documents **focused** — one topic per document. Link liberally between related docs.
- No emojis in document content unless the user explicitly requests them.

## When Working in This Vault

1. Read `Home.md` and relevant `_Index.md` files to orient yourself.
2. Check `git status` before starting work — ensure a clean working tree.
3. Make your changes.
4. Commit immediately after completing each logical unit of work.
5. Verify `git status` shows a clean working tree before finishing.
