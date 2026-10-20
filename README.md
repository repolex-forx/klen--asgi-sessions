# Repolex Knowledge Graph of klen/asgi-sessions

RDF knowledge graph data for [klen/asgi-sessions](https://github.com/klen/asgi-sessions), parsed by [repolex](https://repolex.ai).

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
rlex download klen/asgi-sessions
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bc83d86f7c79ace1dfde93a3561bb22348912e4e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bc83d86f7c79ace1dfde93a3561bb22348912e4e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d7db2e70341d714b105c6f518ededec1b6c0b2b.nq.gz
│   ├── 173e3e3451628279dc77d4ad893e3efb60cc3da9.nq.gz
│   ├── 1f131f7c4c3c1b431dc91dbf4388abacbc5818e9.nq.gz
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 2247d5f95a7193c7221b9464debe167763b4fae3.nq.gz
│   ├── 32cd411778a0827a5ed910f9b06bffe2739bbc4b.nq.gz
│   ├── 3fd76f24e34b0aa33aa0f4339373b5120b0ba2d6.nq.gz
│   ├── 4f918468371e898e949aeeba02cfe0e5203b0785.nq.gz
│   ├── 6614487bd14cfef52707f44df71db1ec3b0ff124.nq.gz
│   ├── 7ff3010f7bc0e8115494a194539f511b132d1765.nq.gz
│   ├── 97bb86ca44080a201660fc341f1d3f41bed85286.nq.gz
│   ├── a6fde06370cd994163972128ddb31c4cdcec5ee8.nq.gz
│   ├── ab4d5aa6736673c2612144bfb28b2a56f9bb81a1.nq.gz
│   ├── c170db324bd1094adb90facd6e700e2c3f6f0417.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ec0141a562a86028de729afd7b62928b5e580a59.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bc83d86f7c79ace1dfde93a3561bb22348912e4e.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 22 files
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

[klen/asgi-sessions](https://github.com/klen/asgi-sessions)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
