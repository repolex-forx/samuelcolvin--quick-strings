# Repolex Knowledge Graph of samuelcolvin/quick-strings

RDF knowledge graph data for [samuelcolvin/quick-strings](https://github.com/samuelcolvin/quick-strings), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/quick-strings
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e427ddeef31de44794c400d87b0c0121bca0a72
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2e427ddeef31de44794c400d87b0c0121bca0a72
│           └── chunk-001.nq.gz
├── blob
│   ├── 1a45eee7760d240bfa8ac1989088e0349169f264.nq.gz
│   ├── 2a9079bc3502009910ba26b16cb391d2995f8147.nq.gz
│   ├── 3a8cabc9e988187922461e910f02cd5813d0d10c.nq.gz
│   ├── 517773409b5b8202a54e2c49607991ed749a293c.nq.gz
│   ├── 55a426d8c9dcb7ef540565bc31db04bc58599f8e.nq.gz
│   ├── 6393ce1fae6af898c359e8909f087bde4b175609.nq.gz
│   ├── 658cb2c97458109d821307739ae110cb825d92e2.nq.gz
│   ├── 79f96fbbd3e6188ce2cc238baea6fdcb0acdd6bd.nq.gz
│   ├── 7f3b2468a323865270f6d39ab9dd7f4b40422fcb.nq.gz
│   ├── a692d25c94fb02ebaf8665f58f30a5e3d026af79.nq.gz
│   ├── b1a0f826e36a0589175da5cef07df557dacf59a0.nq.gz
│   └── d26566c402213afea2715c65660d1b12a50944e5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2e427ddeef31de44794c400d87b0c0121bca0a72.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 19 files
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

[samuelcolvin/quick-strings](https://github.com/samuelcolvin/quick-strings)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
