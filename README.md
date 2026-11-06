# Repolex Knowledge Graph of sphinx-contrib/findanything

RDF knowledge graph data for [sphinx-contrib/findanything](https://github.com/sphinx-contrib/findanything), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/findanything
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3ee1369ffd58a2fa32683275d540172ad73c5f2c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3ee1369ffd58a2fa32683275d540172ad73c5f2c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dfb79b9282a941e59cea54dbbda633062df43ac.nq.gz
│   ├── 22714117335ba15248084dea2ac235f328325acc.nq.gz
│   ├── 2abdf18dd5cbc668265c393303bfc0f4e033760b.nq.gz
│   ├── 401fd62ccae40b7864b9ce174e4b07c61cefc89b.nq.gz
│   ├── 411faa7e5d5a899ebf12bf634fc7ac8a5684c4cf.nq.gz
│   ├── 467e797128f546254f152760d8deff0fc4434ae3.nq.gz
│   ├── 54ae4680f63cf4145d7c0cf21fdfcfa06770a225.nq.gz
│   ├── 58de9b32b6c9f9c6fc948b769a70576affca09a4.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── 9954368ca4064ac14e0ed651946aa529f0a92e01.nq.gz
│   ├── 9ef670fce559f2908969d8096d52251a9125de48.nq.gz
│   ├── ac18f29a63f06f05a9f69263b1428f4d64fa9eb8.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── b73395d37c836d9e8a88a7b03152391bfab61517.nq.gz
│   ├── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
│   ├── c4f99af00854e29666f9721b1d582d623fbfdafb.nq.gz
│   ├── c5793bfed5a2da627188278baef00d1e9d86a0c7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e717bef32a1126845e14565b260da8c6c2835fc8.nq.gz
│   └── fff285f36f980aba3944b0febe894a663ec6ed01.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3ee1369ffd58a2fa32683275d540172ad73c5f2c.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 26 files
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

[sphinx-contrib/findanything](https://github.com/sphinx-contrib/findanything)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
