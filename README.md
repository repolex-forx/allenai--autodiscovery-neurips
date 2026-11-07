# Repolex Knowledge Graph of allenai/autodiscovery-neurips

RDF knowledge graph data for [allenai/autodiscovery-neurips](https://github.com/allenai/autodiscovery-neurips), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/autodiscovery-neurips
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 66aa2d513cafdb23bf38313ebef522ade93f8cd9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 66aa2d513cafdb23bf38313ebef522ade93f8cd9
│           └── chunk-001.nq.gz
├── blob
│   ├── 12c0a09972b35c9a64b004521cf9193663e677ca.nq.gz
│   ├── 180c80bfdb66feb563b22075ede39cff426c66d3.nq.gz
│   ├── 266bccd22fc5295817783c5bc3093d0f61d3d997.nq.gz
│   ├── 2725413ff6bea2992394aad73bc94a28e40fa10b.nq.gz
│   ├── 3bbff48d0acfb66bd04860adfeb96a509bb71ec7.nq.gz
│   ├── 4305ce0010d4340ca2c5e904970117426932dee8.nq.gz
│   ├── 574948441c684fa56371b3bd44ffc2fe99a03c7b.nq.gz
│   ├── 5c0cca51d5d977657529f64be692b7458265a916.nq.gz
│   ├── 691c18ad9c250e28d2a81e4f919b7fde897597c7.nq.gz
│   ├── 6e3ea052d62abe32c920c8ea9330189f062c6cac.nq.gz
│   ├── 7a3af978cb5d283693a528fe0a5627dfc3eb6a40.nq.gz
│   ├── 82114f2765a286bb2708155b43d9ddea90afec84.nq.gz
│   ├── 824085e66f8ce3eb9365f7d978f16a07a7d1f235.nq.gz
│   ├── 88c4bd3d963dd8ba01af177aecdac9ae505b3a49.nq.gz
│   ├── 940872282ab5399a3bdeb919b2f77b4d1d3e72b4.nq.gz
│   ├── a04bf22ddc68e1519b01e0f798ce1ab673420245.nq.gz
│   ├── a225aefbeb25921ba7f8e292725c5345b5130cd8.nq.gz
│   ├── aae9e2ab4c21c68b951f527e61062a19b729f6f8.nq.gz
│   ├── bd89c7f75d0eae257266b8e30c87149cf5f67feb.nq.gz
│   ├── c0dd7c783f4e9b3dcd2bff271f759c1efc0e1711.nq.gz
│   ├── cfa03f561def59f74494c7d921d410258f544783.nq.gz
│   └── da834fd5a35dc65ed0c26004e2f5f45e62fc88ef.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 66aa2d513cafdb23bf38313ebef522ade93f8cd9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[allenai/autodiscovery-neurips](https://github.com/allenai/autodiscovery-neurips)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
