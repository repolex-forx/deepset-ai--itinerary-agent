# Repolex Knowledge Graph of deepset-ai/itinerary-agent

RDF knowledge graph data for [deepset-ai/itinerary-agent](https://github.com/deepset-ai/itinerary-agent), parsed by [repolex](https://repolex.ai).

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
rlex download deepset-ai/itinerary-agent
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c65f7e455ca26b40f24e159ce6a1619a84c6a5b2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c65f7e455ca26b40f24e159ce6a1619a84c6a5b2
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b4e41af037bef5ac29fc779338d76d9ea887fd4.nq.gz
│   ├── 204d404cd04352963f00b58dc8f4adf1eefe72f0.nq.gz
│   ├── 2984745aa36c9d863b85e16d9436c514e6b5cb9e.nq.gz
│   ├── 3a276bc23becb647d8c6f35905dcbcb45bd62d27.nq.gz
│   ├── 78a6acf40883abe97538dda669a322497196c0df.nq.gz
│   ├── 79d44dcba870b6ef9dbf8d46e08156931edfae7d.nq.gz
│   ├── a2b331b9d9ae25dab34ec702354ea062f4cd4ad0.nq.gz
│   ├── b2c1aa20f411cf891864d9e3bdfa67a294399f05.nq.gz
│   ├── bdac3399b8842778485b6ced9ecbaa8c8fc2b866.nq.gz
│   └── c33499b6eff8be581989be7146827a74cda635ec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c65f7e455ca26b40f24e159ce6a1619a84c6a5b2.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[deepset-ai/itinerary-agent](https://github.com/deepset-ai/itinerary-agent)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
