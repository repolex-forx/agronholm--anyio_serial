# Repolex Knowledge Graph of agronholm/anyio_serial

RDF knowledge graph data for [agronholm/anyio_serial](https://github.com/agronholm/anyio_serial), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/anyio_serial
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fe0b3520bb2fbfe12edd9599f7d113516c6ffeb2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fe0b3520bb2fbfe12edd9599f7d113516c6ffeb2
│           └── chunk-001.nq.gz
├── blob
│   ├── 3abf130748cb657718acab8235dc0b7f8529af22.nq.gz
│   ├── 4e176a7cd737c1043ba836deb1f85fbb82f0929a.nq.gz
│   ├── 5868a7c1ab8c07b16468f290348041cd5cb28234.nq.gz
│   ├── 59016158682477848f267a44a9a798d4a436d635.nq.gz
│   ├── 754452379da3ec17969cd4e5481e853fd225a7a6.nq.gz
│   ├── c52e7d824322688564af8b1c38fa19eed6913ad6.nq.gz
│   └── f8c76d447cffad5a3bc661dfb227f214fabcf976.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fe0b3520bb2fbfe12edd9599f7d113516c6ffeb2.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 13 files
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

[agronholm/anyio_serial](https://github.com/agronholm/anyio_serial)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
