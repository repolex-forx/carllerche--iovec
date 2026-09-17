# Repolex Knowledge Graph of carllerche/iovec

RDF knowledge graph data for [carllerche/iovec](https://github.com/carllerche/iovec), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download carllerche/iovec
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d564f78c6346e534b6e45eeb12349b507e088cc7
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── d564f78c6346e534b6e45eeb12349b507e088cc7.nq.gz
│   └── repolex
│       └── d564f78c6346e534b6e45eeb12349b507e088cc7
│           └── chunk-001.nq.gz
├── blob
│   ├── 11fca39fc6c825b7425cf54b77a20c3a93bac2a9.nq.gz
│   ├── 1cb29f17f19f5b8ea015a0ce9b0c65f922604b52.nq.gz
│   ├── 1e091a46c9bfeffcc926cb52b83357e3f6664719.nq.gz
│   ├── 37acedd78bc630d94fda2b13347e51c033a39e6f.nq.gz
│   ├── 3e0efc99e8761b0c00dbde2d69c39d20debc3552.nq.gz
│   ├── 3ef3728bb0a2495220b180a4209e3fa668f3214e.nq.gz
│   ├── 4428146b9851b9eefedc49ecde3838d4ce82f224.nq.gz
│   ├── 4dbc0674f85beab4978bbe09f9922f53cc98ad9d.nq.gz
│   ├── 6c296bec80dfb6f0be6892cf443ec35f868707ab.nq.gz
│   ├── 6d2ea7bd73bc38155daa9f82cd1614aa39846595.nq.gz
│   ├── 87d73e7f9191e1eae2211fa1ba9ca43f6437e00e.nq.gz
│   ├── a21a72399ce5df86289ebdf4d007373f6e498df5.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── e04e8fa51a588b883bd549ad8f4ec37355a5503c.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d564f78c6346e534b6e45eeb12349b507e088cc7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 24 files
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

## Source repository

[carllerche/iovec](https://github.com/carllerche/iovec)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
