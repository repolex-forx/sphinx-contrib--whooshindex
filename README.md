# Repolex Knowledge Graph of sphinx-contrib/whooshindex

RDF knowledge graph data for [sphinx-contrib/whooshindex](https://github.com/sphinx-contrib/whooshindex), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/whooshindex
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c53faf2ece7ded55ed58c200fd7bee3c19d40da5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c53faf2ece7ded55ed58c200fd7bee3c19d40da5
│           └── chunk-001.nq.gz
├── blob
│   ├── 078fb80fe4e61ccc6d40b93559607d1530437d13.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 37467bdc4752a31da7763d7cf24051ab5a8a4307.nq.gz
│   ├── 3869452fdaf35f3bf3fa60a29962a938c3f2804c.nq.gz
│   ├── 458aadd6352f3defb4e402e5948c3c7c8c86b676.nq.gz
│   ├── 5378c4ad362c02c7a5f04c1de9f83560faf98ca1.nq.gz
│   ├── 5d6e15ef57d2e637c15a0b014b6ab5330be55865.nq.gz
│   ├── 5ff9a2af66ba65862cc41772fbfb815850aa4907.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   └── c74d9ce6aa9da39e9ebf3721f83150846251bea2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c53faf2ece7ded55ed58c200fd7bee3c19d40da5.nq.gz
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

[sphinx-contrib/whooshindex](https://github.com/sphinx-contrib/whooshindex)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
