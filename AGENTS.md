# Repository Guidelines

## Purpose
This vault is a compiled knowledge base. Sources are collected in `raw/`, then synthesized into durable notes in `wiki/`.

## Repository Layout
- `raw/`: source captures and references. Treat as immutable.
- `wiki/`: curated notes, synthesis pages, and derived outputs.
- `templates/`: reusable note templates.
- `.obsidian/`: local Obsidian configuration.
- `INDEX.md`: discoverability catalog of important notes.
- `LOG.md`: append-only timeline of ingest/query/lint operations.
- `MEMORY.md`: reusable pitfalls (`GOTCHA`) and preferences (`TASTE`).

## Non-Negotiable Rules
- Do not rewrite `raw/` files except obvious extraction fixes.
- Use Obsidian-compatible markdown with `[[wikilinks]]` for internal notes.
- Keep one clear purpose per note; split files when they become hard to navigate.
- Keep frontmatter consistent when present (`title`, `created`, `updated`, `tags`, `source`).
- Stage explicitly (`git add <path>`). Do not use `git add -A`.

## Standard Workflow
1. Ingest: capture or read source material in `raw/`.
2. Synthesize: create/update notes in `wiki/` with evidence-backed claims.
3. File query outputs back into `wiki/` when they add durable value as summaries, comparisons, analyses, or new concept pages.
4. Cross-link: add meaningful links to related notes and concepts.
5. Update catalog: modify `INDEX.md` for new or materially changed notes.
6. Update timeline: append a dated entry to `LOG.md` for ingest, query, and lint work using:
   `## [YYYY-MM-DD] ingest|query|lint | <topic>`

If vault knowledge changed, steps 5 and 6 are mandatory in the same task. Even when no wiki files change, substantial ingest, query, or lint work should still be logged in `LOG.md`.

## Quality Checks
- Verify key claims against source notes in `raw/`.
- Check for contradictions, stale statements, and orphan pages.
- Confirm newly added notes are reachable from `INDEX.md`.
- Run `git status` before finishing.

## Command Shortcuts
- `rg "<keyword>" raw wiki` : locate entities/claims quickly.
- `fd -e md . raw wiki templates` : list markdown files in scope.
- `rg "^## \\[" LOG.md` : inspect recent operational history.

## Commit & PR Guidance
- Commit format: `docs(scope): imperative summary`.
- Keep commits focused and reversible.
- PRs should include intent, changed files, index/log updates, and open questions.

## Agent Notes
- Read `MEMORY.md` before major edits.
- Agents may proactively run lint checks after substantive wiki changes or when asked. Lint passes should check contradictions, stale statements, orphan pages, weak cross-links, important concepts that lack their own pages, candidate article pages, data gaps that may justify web research, and missing index/log updates, then append a `lint` entry to `LOG.md` when work is performed.
- After non-trivial discoveries, add one concise reusable entry to `MEMORY.md`.
