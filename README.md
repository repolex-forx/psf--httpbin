# Repolex Knowledge Graph of psf/httpbin

RDF knowledge graph data for [psf/httpbin](https://github.com/psf/httpbin), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download psf/httpbin
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 888754822b81c9d8f1202a079c207ce8d9b8c037
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 888754822b81c9d8f1202a079c207ce8d9b8c037.nq.gz
│   └── repolex
│       └── 888754822b81c9d8f1202a079c207ce8d9b8c037
│           └── chunk-001.nq.gz
├── blob
│   ├── 048ecf1c402217d49603cc9265a534333a5a2298.nq.gz
│   ├── 0c1515ce5123fbdc123d5c7c14a63689f521a017.nq.gz
│   ├── 265c7ab68515347755e59a2ded779353e14ecf81.nq.gz
│   ├── 26fd17fc0801972d6a89540d09be53ea3a702f27.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 37f5392d54cea2bda1c4bb97a5cd31f5ad93ad10.nq.gz
│   ├── 3ebc4f62e8e294339ad0d1037cd238ed737dfb4f.nq.gz
│   ├── 43b6bfa4f6cd56a2069f7f5ff644542ac366ccf1.nq.gz
│   ├── 44da70f04a2b82ffa7471411e4315248a913d06d.nq.gz
│   ├── 4b5675da17b0d86550b7b27152ca280302bf6bfb.nq.gz
│   ├── 4deeaaadfec9aef48f90fcb50fbaab8f15a39269.nq.gz
│   ├── 519d325e429c449bd5428fc0768321174dc908a6.nq.gz
│   ├── 5272d05ed8eed99404e707643f842bb476e8f31b.nq.gz
│   ├── 5ab46ac6f69cda9b3cc0d4fdc2172b206be83492.nq.gz
│   ├── 5eef0f10e8cd5cac36342fc9b6dc9855e024361f.nq.gz
│   ├── 5ff09579e3842100aad840366b3a3031b05bef62.nq.gz
│   ├── 63e0d2b9567890ab9b8131407bc62eda50282fa3.nq.gz
│   ├── 6b75124547adb9a7d39c7e26cb9edcb21eb7fe7f.nq.gz
│   ├── 6e2e0591b33b8ebdb87c7a8eabb0d50ee35ad177.nq.gz
│   ├── 726dd626b0ba6e1d947b702a91f075b0bfa52fa4.nq.gz
│   ├── 7dc09efa37da5d16b730665c5c904f18a2e68843.nq.gz
│   ├── 80361ceab5c0f1bdc6f967a39e9b7cd762e46819.nq.gz
│   ├── 836c80264078681fd766b513ae50afb46016ecc0.nq.gz
│   ├── 885f52d8de8220b4aa0430061054cd2230611656.nq.gz
│   ├── 89aa5f99a4f6ef8ee7cb8a59a12a8d139b975803.nq.gz
│   ├── 91f42bebda94a6f664e33af3dc4ede796428f13c.nq.gz
│   ├── 96f81bce745e779e85f578c769ff11707ba6eb0d.nq.gz
│   ├── a4e824c247f97b4f524b885a358c0d0008e4e161.nq.gz
│   ├── a609ede26b4c66d4077d8fcbea19fc74120af6cd.nq.gz
│   ├── a82c1b88441c541b2ad719f929c8fef3135d8514.nq.gz
│   ├── cc0c128257cace9da1d84bb92bbcc4f3a7ed9257.nq.gz
│   ├── d01ec46c957693c8f2343c5d8f6f06d3c026b65d.nq.gz
│   ├── e4b7e589a0e2e96626a14cdbdc990731fe75ec40.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9ee1520a31a6f3ebdf5f24eb82057891cbba118.nq.gz
│   ├── eaa10419c230968fbcfb16967377040b07a44d32.nq.gz
│   └── f75d9509a6ef9d8d1a21e966d0ec78d1a3c20d6e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 888754822b81c9d8f1202a079c207ce8d9b8c037.nq.gz
├── filetree
│   └── 888754822b81c9d8f1202a079c207ce8d9b8c037.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 47 files
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

## Source repository

[psf/httpbin](https://github.com/psf/httpbin)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
