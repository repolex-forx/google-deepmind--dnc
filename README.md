# Repolex Knowledge Graph of google-deepmind/dnc

RDF knowledge graph data for [google-deepmind/dnc](https://github.com/google-deepmind/dnc), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/dnc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f5981c66ac6fe27978014c314c4aba39f1962ee3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f5981c66ac6fe27978014c314c4aba39f1962ee3
│           └── chunk-001.nq.gz
├── blob
│   ├── 036daefa3e461a22b406d385b845ce98d7bf70dd.nq.gz
│   ├── 0786fdf434684f6ef3b5eac90cb7813bdb9c4d2a.nq.gz
│   ├── 147fbcbb3877189248e42a9d1a801d869165089b.nq.gz
│   ├── 20fe7c2f1b658b3a2a3adfd1bd32d090906eede5.nq.gz
│   ├── 211d454a1896b86f4ab77fe3787262b3b1d3c2a7.nq.gz
│   ├── 5009c779a0406f1e5ee77e8f9a8fc3941283fa91.nq.gz
│   ├── 97365b13c584bc4de78baaf6c7d6b58f7fa1ddcd.nq.gz
│   ├── 9da1b8972548e39ed1c22dbdd6f18dfd5ca9b1a9.nq.gz
│   ├── a5c3ee4dba895a07fd0a29995696f38ab4827a1a.nq.gz
│   ├── a60134bc24fc6213b0f62356ebf1d49c9317f078.nq.gz
│   ├── ad52579d87d760582e08c16d0baa19c0f6016e06.nq.gz
│   ├── b9a9d94ba58d16fd37ed9dc6633d9ede9d439869.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── db14b2a68ad23bb6248af2d97383c7f67a065446.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f604c3cb7f1a96b18537a2056b06935a98937ba1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f5981c66ac6fe27978014c314c4aba39f1962ee3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[google-deepmind/dnc](https://github.com/google-deepmind/dnc)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
