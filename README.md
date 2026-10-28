# Repolex Knowledge Graph of explosion/spacy-vectors-builder

RDF knowledge graph data for [explosion/spacy-vectors-builder](https://github.com/explosion/spacy-vectors-builder), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download explosion/spacy-vectors-builder
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f5247248d76e8358704e7c72c1c139229b51db7b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f5247248d76e8358704e7c72c1c139229b51db7b
│           └── chunk-001.nq.gz
├── blob
│   ├── 4199bba93437645659d76d6fbc46dc3dad4d2836.nq.gz
│   ├── 5fc3c9560ed016ade3b9ff127288935d7b9b5183.nq.gz
│   ├── 638ef40f5a4030a9f900c89b8a017a39855210f3.nq.gz
│   ├── 94912e6e1fa855d4b343cf087350659f9faf831c.nq.gz
│   ├── cc3f130282bad31d489b464c739ee8b4bf8c9772.nq.gz
│   ├── d0174ed1b56ee45e812e45cc0b360f46954bf8c5.nq.gz
│   ├── e4ea88ae5532c586094edbc82da4be9a5b36a8c6.nq.gz
│   ├── e7d0b3017756f86ffe69cf58bbc8a5cd759297a0.nq.gz
│   └── fc6897cc00df5abc6ac07d4edf98f593812ec240.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f5247248d76e8358704e7c72c1c139229b51db7b.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[explosion/spacy-vectors-builder](https://github.com/explosion/spacy-vectors-builder)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
