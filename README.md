# Repolex Knowledge Graph of jupyter/nbviewer.org-deploy

RDF knowledge graph data for [jupyter/nbviewer.org-deploy](https://github.com/jupyter/nbviewer.org-deploy), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/nbviewer.org-deploy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 46d27d053886a4ed2e2ee70b3abc754858476cdd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 46d27d053886a4ed2e2ee70b3abc754858476cdd
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b9f3d43562bfa8d5b102fdcc28116bafcec9bce.nq.gz
│   ├── 12abf402a5b3c8057b70a8046a3a5cda4c387d73.nq.gz
│   ├── 131d284d8e8c1062181edf17a2c8f48fe620e60d.nq.gz
│   ├── 1598ae644b2d7743d7583a62cae247d36bfc87e6.nq.gz
│   ├── 1de998aacff94c724b19aefebaf0cc8ffdac8676.nq.gz
│   ├── 2db0a59673b3180afa49920f5d19f271ffaa9a6f.nq.gz
│   ├── 38b621c1e43d74bdb643be214f294d6b0dfe4a43.nq.gz
│   ├── 3f6073e2af6a3f4dd3b943022598beafaec55f61.nq.gz
│   ├── 40b2cf96314bf0f3dabf6efdc5c33357bf349898.nq.gz
│   ├── 412221728205cd19c8270cc8a9aaa71aec117a50.nq.gz
│   ├── 46e587f684fba83b738e77da7b7c5aeef735ad44.nq.gz
│   ├── 47e4e7bfdde1671cfe6a466267f9304de8bc3b63.nq.gz
│   ├── 4c20c6f00c2814b6b039cc3612bdfc1b64391a9d.nq.gz
│   ├── 53e292dc64d2da493f652e8156cedb7f35896c8c.nq.gz
│   ├── 54ceb8ab99ed93a2f93742c2673e2d1110d74eba.nq.gz
│   ├── 5d671ca86029cc34f26b14c3451d9ce5f4f93688.nq.gz
│   ├── 6bf38baaf6c37fc677df40875bc3ee2b5b1e7f05.nq.gz
│   ├── 71edef26c6c943e5ddf7ab938a50593046bb7a89.nq.gz
│   ├── 78041c052cc1cae83e57f19bdc97af8f3766235f.nq.gz
│   ├── ad5e900d71e86ab066f8d14238fe14839338ec93.nq.gz
│   ├── aefb9416faf4354f7942004d2d7adeb02e8b7c36.nq.gz
│   ├── b13a9ab5a4c824c8eb4be4e1577ac7e7a94d9240.nq.gz
│   ├── c80c9a4020c8691f6b07ab7b601bae9b1705337d.nq.gz
│   ├── cefcaaf9db5dca4e792a5cffc9bbeb0b2ca54eb7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f3d15784ec1818c32e6e5009291a1bb19eb51fde.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 46d27d053886a4ed2e2ee70b3abc754858476cdd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[jupyter/nbviewer.org-deploy](https://github.com/jupyter/nbviewer.org-deploy)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
