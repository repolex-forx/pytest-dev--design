# Repolex Knowledge Graph of pytest-dev/design

RDF knowledge graph data for [pytest-dev/design](https://github.com/pytest-dev/design), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/design
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7d3f9708bf9ad727d67bcf303d70587f009a1e58
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7d3f9708bf9ad727d67bcf303d70587f009a1e58
│           └── chunk-001.nq.gz
├── blob
│   ├── 01597f591447caf0a2500acec7331067c61ebf93.nq.gz
│   ├── 073dd779b22f46c6eaec8f91a138d2734076df42.nq.gz
│   ├── 112ee7cdd7907e31ac96763426ef2d06f06cd15e.nq.gz
│   ├── 191d1868dd5ec615340215ba98e890d72fdb6b82.nq.gz
│   ├── 1a2ab50c714c7ec8bda681e852d95c131d409417.nq.gz
│   ├── 1ab00965c097e12f16dcbeb35a4d19ce354f1ffb.nq.gz
│   ├── 1d2bc0f816dc81ac86fa381bd106579f162fe4c4.nq.gz
│   ├── 2bc8842562457ba6d1dca38b0a558ccb2217caae.nq.gz
│   ├── 4cb06be79b77f1b615e9d2800af611562000fc53.nq.gz
│   ├── 5dcda30faf2f064a266cef7f54aee04c24d8740c.nq.gz
│   ├── 608e319e520e26692ecc50930a707fbd07ce7db9.nq.gz
│   ├── 6408c90c8704d61c1501d4a0f39d2e47f5fd9be2.nq.gz
│   ├── 93e97ec2ab51d1606d50547000ed85d2cb7532c7.nq.gz
│   ├── 9e1cab3970f304b2b6a2ab5467b4c6c25fd8ef8d.nq.gz
│   ├── d6e9790899fa3b225288bf87c8debbf83d08fd90.nq.gz
│   ├── e05ceb1123333580509dc63a614cbaf0e05c13dc.nq.gz
│   ├── efffb5aadcffb822cdea69b36e0b9d1c712d4955.nq.gz
│   └── fee1e6d7013c696adde54569d67b109050025ef4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7d3f9708bf9ad727d67bcf303d70587f009a1e58.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[pytest-dev/design](https://github.com/pytest-dev/design)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
