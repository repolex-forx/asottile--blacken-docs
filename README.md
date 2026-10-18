# Repolex Knowledge Graph of asottile/blacken-docs

RDF knowledge graph data for [asottile/blacken-docs](https://github.com/asottile/blacken-docs), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/blacken-docs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e6b021559e1cbe76f47be312088687aac8cc69d7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e6b021559e1cbe76f47be312088687aac8cc69d7
│           └── chunk-001.nq.gz
├── blob
│   ├── 114a6874dc209dfdafcb6a26fee2a9d910d1e6b8.nq.gz
│   ├── 1667131bf5b9c03fe043557ff0a68a8d9ec1e048.nq.gz
│   ├── 205ab9ad9df4ab629d1b7b8d8a72b41f44d8824c.nq.gz
│   ├── 22ddbb118475b52ce8ecba56d9ec45009923da58.nq.gz
│   ├── 2883592708aeda00c4b994558119acacf63b166e.nq.gz
│   ├── 2a7f84f54867d02714727f82eef95d3be939d666.nq.gz
│   ├── 30acc83b6797da94e6f047ba88ccfb5b934894ee.nq.gz
│   ├── 332b4cfc6476e93a8a6204fc7afa80eabe3cf918.nq.gz
│   ├── 3ba13e0cec6cbbfd462e9ebf529dd2093148cd69.nq.gz
│   ├── 40f4ac757715bb1a8c355eda9124141fdda3aeff.nq.gz
│   ├── 438d629c3ce988e3afffa71110b9660853d38549.nq.gz
│   ├── 4fb7faec2960085d0994a23838947e58b6228aa7.nq.gz
│   ├── 5b25737c0d6d0671ed8412d13afab65cdb8dbafa.nq.gz
│   ├── 659f24085b1c999fd998364518da691153a14b63.nq.gz
│   ├── 6834462fa5122b154eb4072e54d24f164faf2d49.nq.gz
│   ├── 7f1d007c01048570d774e58f46203d3e92056c39.nq.gz
│   ├── 93acb639926ccf42e9a2f76f02419eeaf0405c3a.nq.gz
│   ├── b7af5ef213084fe100c5bb755659ef68c14dae5b.nq.gz
│   ├── bbb3fe90c7b3d80430c4ed91debe3be2de2e206c.nq.gz
│   ├── e604d4b72ae2405c4e135db6e96dc29cb44a265e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fff5585dc1f623474080815a33a58a6817624c7c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e6b021559e1cbe76f47be312088687aac8cc69d7.nq.gz
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

[asottile/blacken-docs](https://github.com/asottile/blacken-docs)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
