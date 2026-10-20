# Repolex Knowledge Graph of coleifer/irc

RDF knowledge graph data for [coleifer/irc](https://github.com/coleifer/irc), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/irc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bbc47e2bf4d899cca5a06bea5534f28775b940a4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bbc47e2bf4d899cca5a06bea5534f28775b940a4
│           └── chunk-001.nq.gz
├── blob
│   ├── 0728e43784a7a79c81c870ced1489c95c56d2cec.nq.gz
│   ├── 19428a00f0908646c654cd24d0cecde3da6a3cd9.nq.gz
│   ├── 2016f15fea9724d1f5309b78d2ac49f4d7b40d61.nq.gz
│   ├── 2395d4df2d17bf1b63013831d9c3f95492c3b34e.nq.gz
│   ├── 23f90d8d32fa79d6cc83eede6f1726771dceaf87.nq.gz
│   ├── 394bc74b874b40b34a394b9707becceb99c3bff5.nq.gz
│   ├── 3aabe1f0e5f5ac30862b1b09ed608e38ffbf27e8.nq.gz
│   ├── 434c7b225e72e2c2bd9ac799dde8dc61f9463ba7.nq.gz
│   ├── 4a63abe68f639ef8b5d1e25ca733ecaeca39cbc8.nq.gz
│   ├── 591a0966022c699d8fa30463939ebcd14551a3f5.nq.gz
│   ├── 64c7bd7b68ea8dbaeb1d182f98f7e88d15b1a33c.nq.gz
│   ├── 7e3beb43c1152ae6c6093801c3d0d332b19b8ad4.nq.gz
│   ├── 86b580c53fdba8a2515d93696c0da48179d9c9c3.nq.gz
│   ├── 926ea1f5f8bebfc039c1345b64d86a341f7979e8.nq.gz
│   ├── 94be2afe76916ac05ff8eb4a390a871b6aa0cf39.nq.gz
│   ├── a7512c013bb537c420c2f6ab121f8c2248a33d35.nq.gz
│   ├── ae3bf0915790fea6b11128344459ef0421c3ab69.nq.gz
│   ├── b5b0cc25f732ab2a14bb2371837d172c756ff9c5.nq.gz
│   ├── bd5e6985d9b1b2ce6622fb953bcd7902d46d1e5a.nq.gz
│   ├── c595ee48b05b8f3643556798ce2cc60cefcb868a.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   ├── ce2531f703e1380fd02219c42901a1d998089fcd.nq.gz
│   ├── da40667217222dadd0a4575d7dd96d76f6c5d91e.nq.gz
│   ├── e5c4b628012956b58d6365a9575f33ef212fca56.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f3f73c18015dd8d03ee9a6d8da70238e30e6b999.nq.gz
│   └── fdea2096ee9362a65a2ddb3eb8b6638d05efc9ef.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bbc47e2bf4d899cca5a06bea5534f28775b940a4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[coleifer/irc](https://github.com/coleifer/irc)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
