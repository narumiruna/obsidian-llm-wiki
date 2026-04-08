# Obsidian LLM Wiki

This repository is based on Andrej Karpathy's shared workflow for building an LLM-maintained personal wiki.

## What This Is

This vault is a file-first knowledge system:
- `raw/` keeps source material.
- `wiki/` keeps synthesized notes.
- `INDEX.md` helps you find important pages.
- `LOG.md` records what changed and when.

You focus on choosing sources and asking good questions. The LLM focuses on organizing, linking, and maintaining the knowledge layer.

You can browse and read the vault in Obsidian.

## Usage

### Ingest
Use the Chrome extension [Obsidian Web Clipper](https://chromewebstore.google.com/detail/obsidian-web-clipper/cnjifjpddelmedmihgijeibhnjfabmlf) to clip web pages you want to preserve into `raw/`. Then ask the LLM to process the source into the wiki.

### Query
Use Codex CLI (or another coding agent such as Claude Code) to ask questions against the vault or request a new note in `wiki/`. The LLM searches relevant notes, synthesizes an answer, and can file useful results back into the wiki as durable pages.

## What to Update Every Run

When knowledge changes (new note, major synthesis, or substantial revision), the LLM should update both:
- `INDEX.md` for discoverability
- `LOG.md` for chronological traceability

## Where Rules Live

`AGENTS.md` defines the operating rules for human/LLM collaboration in this vault.

## References

- [llm-wiki by @karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- [Thread by @karpathy](https://x.com/karpathy/status/2039805659525644595?s=46)
- [How I use Obsidian by Steph Ango](https://stephango.com/vault)
- [kepano-obsidian by Steph Ango](https://github.com/kepano/kepano-obsidian)
