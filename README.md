# Repolex Knowledge Graph of intake/python-snappy

RDF knowledge graph data for [intake/python-snappy](https://github.com/intake/python-snappy), parsed by [repolex](https://repolex.ai).

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
rlex download intake/python-snappy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ff09d429fca0e34a6450c8c789f26e1c3386405a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ff09d429fca0e34a6450c8c789f26e1c3386405a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0447ee4f2a1ba26f5fc90d8f6bc5819e8f0259bb.nq.gz
│   ├── 08e6a6487fe34df964b50156fc0a765bd41293b5.nq.gz
│   ├── 1272004ccc01e715b27a48864d621ce6e72a7ebe.nq.gz
│   ├── 2c0b6f290a10a6a5cd3f51509f60e23fc71a13ef.nq.gz
│   ├── 2cf7eff25750bfa3f5cbf07ce25cda5a26107f33.nq.gz
│   ├── 3e65a38bb54267f410f2eb9f5e753b07bbf357ff.nq.gz
│   ├── 42b20a8ba632c4831074403c5e4d33fa1ae8c395.nq.gz
│   ├── 507da487c9bfd5a3ffec4253114294f1461b1fde.nq.gz
│   ├── 973d7c7aa51f901ecd41ae116b13b22ad0b668d3.nq.gz
│   ├── a2e0bc5c9cb0814dacb8028a95f4cdb18c0ec471.nq.gz
│   ├── a9c0c4867b2f71c47cc8e80440cb0693bb89863e.nq.gz
│   ├── d359d6f4a2a6b1a577eef646ad49d4d0053939e1.nq.gz
│   ├── e230e0b9e5f9006a42103f23f79c17c6b55e6a07.nq.gz
│   ├── e7e83e34b37e551eed675ad1797352c90b22ea8c.nq.gz
│   └── f5639eac24f1ab5e6383d011148e85801e7302ce.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ff09d429fca0e34a6450c8c789f26e1c3386405a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[intake/python-snappy](https://github.com/intake/python-snappy)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
