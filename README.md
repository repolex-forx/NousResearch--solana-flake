# Repolex Knowledge Graph of NousResearch/solana-flake

RDF knowledge graph data for [NousResearch/solana-flake](https://github.com/NousResearch/solana-flake), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/solana-flake
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c1e48211971952ef6b3975c6d8fdc1f79ed7418a
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c1e48211971952ef6b3975c6d8fdc1f79ed7418a.nq.gz
│   └── repolex
│       └── c1e48211971952ef6b3975c6d8fdc1f79ed7418a
│           └── chunk-001.nq.gz
├── blob
│   ├── 22f0d280e4dd75ee603c755a28c7332edee6bca1.nq.gz
│   ├── 2eaf529c30349334d536defa186f709ae858ce39.nq.gz
│   ├── 4302c5a808ff85eb1f55f6bad99d897999c915b0.nq.gz
│   ├── 49518a39c9c07e298b4e7de9d7c16caa8fb38485.nq.gz
│   ├── 8a9fe94042e66f3a2ec8ca8fc2df4cae99c4d85d.nq.gz
│   ├── ce6432ba6f2426a09e80a107043537a4708c54d6.nq.gz
│   ├── dad884a2ffa62ac06e4a2c62a5f2c1e2915ce4c2.nq.gz
│   ├── e94621ee65f3b3e9333528af1cb68dbea4a4227d.nq.gz
│   ├── eb06186650e0347160bd3080c090a2a2f97b0b4c.nq.gz
│   └── ef12c672e79923fe4873ba2ef5d9a37438b2474e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c1e48211971952ef6b3975c6d8fdc1f79ed7418a.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[NousResearch/solana-flake](https://github.com/NousResearch/solana-flake)

---
*Parsed on 2026-10-08 by [repolex](https://repolex.ai)*
