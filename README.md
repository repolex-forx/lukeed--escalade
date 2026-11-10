# Repolex Knowledge Graph of lukeed/escalade

RDF knowledge graph data for [lukeed/escalade](https://github.com/lukeed/escalade), parsed by [repolex](https://repolex.ai).

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
rlex download lukeed/escalade
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fa5be167391581849cff04dbc75dc2978744b642
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fa5be167391581849cff04dbc75dc2978744b642
│           └── chunk-001.nq.gz
├── blob
│   ├── 26c58f2f3165162e35bf72c190d4c70955dbc9ec.nq.gz
│   ├── 3cdc5bd1fee04733ea106fd6cdde40ec094880cb.nq.gz
│   ├── 422df7d13c27516ee6f012fe8f06d95cdd04fca7.nq.gz
│   ├── 4e1190b17e12e84a5277b64542f90c606970f5ca.nq.gz
│   ├── 550699cf98e1c9b4de9b01128d072c1d8f6bd7e0.nq.gz
│   ├── 69f31218efa359fa45341d2eb5d151ae241a7ec2.nq.gz
│   ├── 78046cbfd8e1448f11144761019e9f32ab31b246.nq.gz
│   ├── 8337712ea57f00733b5709b27efb3de797e95575.nq.gz
│   ├── 8f48e06477547f8dfc8e75b628e6baa561694e57.nq.gz
│   ├── 9c3daa69e1ecd6bee2d487249d140fceb129fc33.nq.gz
│   ├── 9d5b5890c38169867e93a5dd6d3e9ed829370243.nq.gz
│   ├── a12633f2d163908ba9658bc195e80a67bf97a940.nq.gz
│   ├── aa0e61693c7c02139b859511446c90045c106b6f.nq.gz
│   ├── b889db5eb7c10b5d7c8cd901e8be909e26979477.nq.gz
│   ├── bf95be03425c909cd4aaef11fdb7ac6fe31e2dd3.nq.gz
│   ├── c023d37b286d1f16630ed054d492c027184dffc0.nq.gz
│   ├── e07ee0d387a9e5531d4bfa596272ed7b7c8ce124.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f78820146540cef1081cfe7c08f4e576cc7e7386.nq.gz
│   ├── f7adfccd910efddba6757a6b965a9bf6b11d67ab.nq.gz
│   ├── fa6089faba3cf381229744c9f21ed3ae9ed5014a.nq.gz
│   └── fb4e82e2ab06560d03fe75997ed4bd64d376ede8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fa5be167391581849cff04dbc75dc2978744b642.nq.gz
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

[lukeed/escalade](https://github.com/lukeed/escalade)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
