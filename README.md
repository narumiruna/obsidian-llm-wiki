# Obsidian LLM Wiki

This repository is based on Andrej Karpathy's shared workflow for building an LLM-maintained personal wiki.

## What This Is

This vault is a file-first knowledge system:
- `raw/` keeps source material.
- `wiki/` keeps synthesized notes.
- `INDEX.md` helps you find important pages.
- `LOG.md` records what changed and when.

You focus on choosing sources and asking good questions. The LLM focuses on organizing, linking, and maintaining the knowledge layer.

## Quickstart

1. Add one source note to `raw/`.
2. Create or update a related note in `wiki/`.
3. Capture the key ideas with clear evidence from the source.
4. Add internal links (`[[...]]`) so the new note connects to existing topics.
5. Update `INDEX.md` so the note is easy to discover.
6. Append an entry to `LOG.md` with date and operation type.
7. Repeat with the next source, one step at a time.

## Day-to-Day Loop

### Ingest
Read a new source and extract high-signal claims into the wiki.

### Query
Ask questions against existing wiki notes, then file useful answers back into `wiki/` as durable pages.

### Lint
Periodically review for contradictions, stale claims, missing links, and orphan notes.

## What to Update Every Run

When knowledge changes (new note, major synthesis, or substantial revision), update both:
- `INDEX.md` for discoverability
- `LOG.md` for chronological traceability

## Where Rules Live

`AGENTS.md` defines the operating rules for human/LLM collaboration in this vault.

## References

- [llm-wiki by @karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [Thread by @karpathy](https://x.com/karpathy/status/2039805659525644595?s=46)
- [How I use Obsidian by Steph Ango](https://stephango.com/vault)
- [kepano-obsidian by Steph Ango](https://github.com/kepano/kepano-obsidian)
