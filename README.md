# Repolex Knowledge Graph of bentoml/llm-router

RDF knowledge graph data for [bentoml/llm-router](https://github.com/bentoml/llm-router), parsed by [repolex](https://repolex.ai).

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
rlex download bentoml/llm-router
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 322dcbb7dc53710f0239387a68de06f88c8204cc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 322dcbb7dc53710f0239387a68de06f88c8204cc
│           └── chunk-001.nq.gz
├── blob
│   ├── 493c5aa46a4fd7a0f6c080e90279c3a5c845dd32.nq.gz
│   ├── 82f927558a3dff0ea8c20858856e70779fd02c93.nq.gz
│   ├── 9beca3c64531f796a69e1638b133bfcc8f33a5ab.nq.gz
│   ├── 9c3656ae8432f7396c0f1a3f7f3a137cc8f4841e.nq.gz
│   ├── 9f57d1c5030a2b21bd4f7da5ea2a54960b08af6a.nq.gz
│   ├── b7fbfb72192f2c8477985bd38d58d491c37201a7.nq.gz
│   ├── bfd2c78a207e53e9f8bcdcbf39bdf5ce1fb1839e.nq.gz
│   ├── d9cf1150b84cca06b20e7dcae3a5941ad67e1d87.nq.gz
│   ├── d9e02b7256a9d03c4ceeaa9fb0a44e8ffa5bd2e0.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── edda27eafe72a117c6e3531c1c5341f862c9b6e0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 322dcbb7dc53710f0239387a68de06f88c8204cc.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 18 files
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

[bentoml/llm-router](https://github.com/bentoml/llm-router)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
