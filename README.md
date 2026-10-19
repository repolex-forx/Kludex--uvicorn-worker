# Repolex Knowledge Graph of Kludex/uvicorn-worker

RDF knowledge graph data for [Kludex/uvicorn-worker](https://github.com/Kludex/uvicorn-worker), parsed by [repolex](https://repolex.ai).

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
rlex download Kludex/uvicorn-worker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cd29cc6447cff3abc968e930023dc97e5e5080f9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cd29cc6447cff3abc968e930023dc97e5e5080f9
│           └── chunk-001.nq.gz
├── blob
│   ├── 01f725981abad30a01b8fcdfe46219b950afbd4b.nq.gz
│   ├── 10a33521e039bb075de113b091f838418dbc7e80.nq.gz
│   ├── 21259099ac7c32f4fec6d23c934617b546ecafd9.nq.gz
│   ├── 2e5813738009b79ca30ceffd6b6ec1402f46cb47.nq.gz
│   ├── 4fdf27640a5b4e1c3ac1d136be9d59e554ac728e.nq.gz
│   ├── 514989628bde642e4bdd26f96587def94f334135.nq.gz
│   ├── 5244cda7e8aaf0c30b4774b7207fad6e7d1cd1c7.nq.gz
│   ├── 595829bbd01e92c4a31818d73885870bd484356f.nq.gz
│   ├── 612d62898a54f3b071baf1b4a92252328549e6c0.nq.gz
│   ├── 660ac8e5af25d65f185077e3a02466ffc819550c.nq.gz
│   ├── 668fc0feb11b02e7d863270595717847b549b8ca.nq.gz
│   ├── 8535696a3fa7506b1b4c6b927557c788b876f4f4.nq.gz
│   ├── 8ff3584f9d7dbce62a47fbed1bd107509bd1d7cd.nq.gz
│   ├── 950ac78926628c84bc5fb5d40a0983d8f670f2ec.nq.gz
│   ├── 9eb2e848f775a343435ea84177475f9b9057537a.nq.gz
│   ├── c4fc73181745a5dc327dee45a77b9d3205a3796f.nq.gz
│   ├── dd6a0667eb3c3a97328c87f011ad1ebd44c30741.nq.gz
│   ├── e611d38394a267b1405dce0ce5207f6d7d6ef653.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── edd300997c861fb10aa968dad9590df20453b7af.nq.gz
│   └── f58ee89fc75119dbf00c70f9dfd9258b53f46a05.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cd29cc6447cff3abc968e930023dc97e5e5080f9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[Kludex/uvicorn-worker](https://github.com/Kludex/uvicorn-worker)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
