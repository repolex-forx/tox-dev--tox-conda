# Repolex Knowledge Graph of tox-dev/tox-conda

RDF knowledge graph data for [tox-dev/tox-conda](https://github.com/tox-dev/tox-conda), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-conda
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1bebdc94f3f183437ed8e90c57e30f960495da53
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1bebdc94f3f183437ed8e90c57e30f960495da53
│           └── chunk-001.nq.gz
├── blob
│   ├── 01f6c1675f9d2d09e37e9e8dee95423665699e93.nq.gz
│   ├── 069f46e9fde502fffbe3a696bbd10726ae2625e7.nq.gz
│   ├── 0f9e29ba8c2dadd452306034fef7602da9e07023.nq.gz
│   ├── 123014908bebbfb7ecfa1d15daaceb272fabe05b.nq.gz
│   ├── 16db4ba1a64ee079acaff86fee5f86f9742a5eeb.nq.gz
│   ├── 1756846ff428e6f246080e9c642cb2c82b0cf07b.nq.gz
│   ├── 1ebe855e09aca722657643350dba2a5f454225e3.nq.gz
│   ├── 1f39f21b56992316ca749c52ebaa807acf206bd4.nq.gz
│   ├── 4592cf45d4eb5135cb9fde5e0dd62c891ef5d23d.nq.gz
│   ├── 4c06e77384166a322eeb2cde2445c75bdef17a84.nq.gz
│   ├── 53209f78714907b441507b469c40ac8dbc0c73c8.nq.gz
│   ├── 58706bed8c8bee9bf480637c41fa163d93cdc6db.nq.gz
│   ├── 606849326a4002007fd42060b51e69a19c18675c.nq.gz
│   ├── 73445667c73eb408ab5ef47035436650bf5621d0.nq.gz
│   ├── 79a5926b4c47e1e5103015c49e5e8adc2a344128.nq.gz
│   ├── 8b36b3b626840f87281aabd564a57c70ad69f655.nq.gz
│   ├── 97f03190012a904bf7d78151c0364d351e808cfc.nq.gz
│   ├── b3164410fdeb05f3bbbbe0d29c71e9eec4525132.nq.gz
│   ├── b40b505174fd84df0d74337e280a024121a3180f.nq.gz
│   ├── c889d0e8dbc92ab26af3e6f45949f0ec287f3160.nq.gz
│   ├── c8fa45cb7040a86e173614628909673513dcbff9.nq.gz
│   └── fd3a842980578b836b3e5d70676fe27c43a1f07b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1bebdc94f3f183437ed8e90c57e30f960495da53.nq.gz
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

[tox-dev/tox-conda](https://github.com/tox-dev/tox-conda)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
