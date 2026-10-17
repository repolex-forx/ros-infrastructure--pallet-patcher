# Repolex Knowledge Graph of ros-infrastructure/pallet-patcher

RDF knowledge graph data for [ros-infrastructure/pallet-patcher](https://github.com/ros-infrastructure/pallet-patcher), parsed by [repolex](https://repolex.ai).

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
rlex download ros-infrastructure/pallet-patcher
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a6143ef05a0f5a83ba93a90d13cf949ba3def5f2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a6143ef05a0f5a83ba93a90d13cf949ba3def5f2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d258cf24344fe2d67c9909fd194a3b367ad81d0.nq.gz
│   ├── 0d8f2d635e2d78270aca88a8174d75db090aefbb.nq.gz
│   ├── 119d51c03748293f138b3e3264fb8602db6ca3f2.nq.gz
│   ├── 11b757c27c03c107f6f5638d35e123a201d1065d.nq.gz
│   ├── 1d3caded4c1f38003160442e2db38768cda3f81d.nq.gz
│   ├── 2006ac9a10828966958ef224080eb021dee37116.nq.gz
│   ├── 20f73efea46fdcfe0edb38b5e10580756d93cd03.nq.gz
│   ├── 23c4cb3b50919fe9d0ee76c19ecfdc907a84636a.nq.gz
│   ├── 2c82b8c0f47b552b308b30a3a3a556e8fdacdc7a.nq.gz
│   ├── 326bb66d4c74f0cf8cf0dfc4e79909001f37da84.nq.gz
│   ├── 335bc232342318ced406526a8b60c73724d0ff75.nq.gz
│   ├── 37d2f30551eb851ad3cf4ccec5180c78ecfee3b4.nq.gz
│   ├── 535dc801b06e096b44566a77293b4d76ddcd88a5.nq.gz
│   ├── 58ab74666bcf3c1302ef6d5a36020debe99f9438.nq.gz
│   ├── 6e493a1aae3aeba544ff8f716ee2526d55e25e4c.nq.gz
│   ├── 71e49422926beba0b5c39c003eb4089366cc8cee.nq.gz
│   ├── 7f1a2288dd45278c5e0861218c0b155c2e114d20.nq.gz
│   ├── 960354b531f3362bad3fbbd05dcbca7ae2e7c883.nq.gz
│   ├── 9dd6ed362bfed501ee4344efe387b33241f5e7ec.nq.gz
│   ├── 9e269b9a816efb7f3cc46b13904da93d211ff47a.nq.gz
│   ├── aad7119d14495d486cce2965cea183c7a4c687d8.nq.gz
│   ├── aef13b99731ac6fb92503dcace68db36eb3ee4c8.nq.gz
│   ├── b90fbc640372cbb66cb9f72ef552693cd9e3af9c.nq.gz
│   ├── ba5a00373c812acab0c6a655e66d3faef98512af.nq.gz
│   ├── c0916e652a57734da8b1a37a459b10c29de30b25.nq.gz
│   ├── c83489e53658e9064a8a3891c7ec2a6694fce3b6.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── def703ca3de110feb7df78707050e22612035ce7.nq.gz
│   ├── e1c03339e9982d0f008575fc421218c4fc38dcea.nq.gz
│   ├── e582053ea018c369be05aae96cf730744f1dc616.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f1948bfddb4d426009d8f9e6f7c465402a6b8439.nq.gz
│   ├── f2d69815fe82b9d88bd6d7030ef845d291bc746f.nq.gz
│   ├── f4e491ed91e632e73495d588baf315b403c546e4.nq.gz
│   ├── f5eeeda83e6d9da8872cf42336b99c43f795bf89.nq.gz
│   └── f988285435bdce10e046ee09929f30366c5e5d61.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a6143ef05a0f5a83ba93a90d13cf949ba3def5f2.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 43 files
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

[ros-infrastructure/pallet-patcher](https://github.com/ros-infrastructure/pallet-patcher)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
