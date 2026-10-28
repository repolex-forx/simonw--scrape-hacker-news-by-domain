# Repolex Knowledge Graph of simonw/scrape-hacker-news-by-domain

RDF knowledge graph data for [simonw/scrape-hacker-news-by-domain](https://github.com/simonw/scrape-hacker-news-by-domain), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/scrape-hacker-news-by-domain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9ee51d78f71d076a1ab49847b7ce873e00f1eed4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9ee51d78f71d076a1ab49847b7ce873e00f1eed4
│           └── chunk-001.nq.gz
├── blob
│   ├── 16390e7cab729b10c36c7b5167e54c433e91c28b.nq.gz
│   ├── 234464fd4f9cca212e5422a6c9cdaa634a8e5704.nq.gz
│   ├── 289162e22769acde2e3de98e320038a592d97602.nq.gz
│   ├── 36b0dce6bf093b1c1ffcf7723f6b4774886059a2.nq.gz
│   ├── 4c2990daf964dde5391eb4461abf645476e93f05.nq.gz
│   ├── df64b6397139e287d1435d01173417a4364f5459.nq.gz
│   └── ebc024ea7b4ce72d266feb04fc52d4e171968919.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9ee51d78f71d076a1ab49847b7ce873e00f1eed4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[simonw/scrape-hacker-news-by-domain](https://github.com/simonw/scrape-hacker-news-by-domain)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
