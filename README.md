# Repolex Knowledge Graph of nikvaessen/jiwer

RDF knowledge graph data for [nikvaessen/jiwer](https://github.com/nikvaessen/jiwer), parsed by [repolex](https://repolex.ai).

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
rlex download nikvaessen/jiwer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 46f6364dcd4fdff9583c53dc00caf50399e9db37
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 46f6364dcd4fdff9583c53dc00caf50399e9db37
│           └── chunk-001.nq.gz
├── blob
│   ├── 032573de07b6dc2760ef582ca54eca62a3dfd057.nq.gz
│   ├── 15f355bcf12bc118d075181b78f5b212d978d6f8.nq.gz
│   ├── 1754c75eab51d52f0cb0be61fa4dfbb904adfdcd.nq.gz
│   ├── 178a176b12271669585c7f46dd70ec90615a4e18.nq.gz
│   ├── 278a9667bfbcb9171ff196ac7ccc61d6116a9ed2.nq.gz
│   ├── 2fef05c6e4105e161bb42be456e22a294f673cba.nq.gz
│   ├── 3932a3a10f67c774ee6ff4719df9253a970e0be6.nq.gz
│   ├── 3eff73a0729f45a8dd0beb6228b10ec872200514.nq.gz
│   ├── 415feb43c2fcee4cfd88a4fe19ee60389bc4128f.nq.gz
│   ├── 441249f00f4c27bb60ceadf63c840b037a2e5155.nq.gz
│   ├── 4f69272e069141735cbdfb3e7472f4f1d380d4a0.nq.gz
│   ├── 62be95413615f7e07a1fa3cf8d1765e7cafefb92.nq.gz
│   ├── 6d63cb391129c68ea8c4931efcc14fe8a74a818b.nq.gz
│   ├── 846a816752edf1e31c7867dbf258b9205a700a56.nq.gz
│   ├── 8a26b2c6902a0147a6ea707f764f81fd58c6d1a3.nq.gz
│   ├── 8b99d85cba42011c5bb782466351b52125e62cc1.nq.gz
│   ├── a1bb5442a9af2d380979e9cf452f273011ccdc36.nq.gz
│   ├── a1c712ef73fedc693b3907490eba255f64928ac7.nq.gz
│   ├── ac378f2b1a9a48f242d60e54784d2fa9baf2da09.nq.gz
│   ├── b19f00d98c886f8e7df4ba10776b5807af62cd84.nq.gz
│   ├── b4cdb67854b9f43139c191bf4a12b89e2e2c73f1.nq.gz
│   ├── c35662e10f828261e83490d034cb965451035d6d.nq.gz
│   ├── ce605d20cf2f5d5cf8e89dfff5bb8faa61b3aa4e.nq.gz
│   ├── db3d33767b3ccb230f9d4648211c4be20ac57646.nq.gz
│   ├── e16c81b7af85130d9d64950b9748a187c15fe797.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e94741089443d7f8908408986d7a7fc50f94f479.nq.gz
│   ├── eaa70010f8db948e555e95c2ba27507f5ddb192d.nq.gz
│   ├── f6b42b403da10ec29ebed4939e20a08b41bcf69b.nq.gz
│   └── fb463cead2b4cc073f830995b44668b6a9759e7e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 46f6364dcd4fdff9583c53dc00caf50399e9db37.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 36 files
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

[nikvaessen/jiwer](https://github.com/nikvaessen/jiwer)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
