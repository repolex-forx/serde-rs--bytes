# Repolex Knowledge Graph of serde-rs/bytes

RDF knowledge graph data for [serde-rs/bytes](https://github.com/serde-rs/bytes), parsed by [repolex](https://repolex.ai).

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
rlex download serde-rs/bytes
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 34f3c7d442716d0f28db7c3641882648ce387b60
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 34f3c7d442716d0f28db7c3641882648ce387b60.nq.gz
│   └── repolex
│       └── 34f3c7d442716d0f28db7c3641882648ce387b60
│           └── chunk-001.nq.gz
├── blob
│   ├── 019a7cb7d23ec7625ff4211b79ffc09a8ff9259b.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 2654f1404e837ccc562d835436b2037b53188a57.nq.gz
│   ├── 27c35e612434ed61dd5f152aab83666035bf3347.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 37889a8c1f8272db9bd90c90fe29932e510967f5.nq.gz
│   ├── 38328ccf29edf7e49885882cc409ee63ee5a2721.nq.gz
│   ├── 46c55ebef8bb46b5cd43d8a97c1ce00db344415e.nq.gz
│   ├── 4d299017298e0c91b493578c4092f78a7308af36.nq.gz
│   ├── 6b864b95d8efa7e87b1da2899c93816e3bd3826a.nq.gz
│   ├── 754b4b9e7128ddeaa62e9f45b71152f37e1a7c9b.nq.gz
│   ├── 81fcda58c1ba1db3f351b7104a60a719b346b636.nq.gz
│   ├── a0423cf0a23125fef3ad3fc619a528ce630f70f5.nq.gz
│   ├── e0a0e9f0405077aa2bb03540115187e0b1333bc6.nq.gz
│   └── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 34f3c7d442716d0f28db7c3641882648ce387b60.nq.gz
├── filetree
│   └── 34f3c7d442716d0f28db7c3641882648ce387b60.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 25 files
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

[serde-rs/bytes](https://github.com/serde-rs/bytes)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
