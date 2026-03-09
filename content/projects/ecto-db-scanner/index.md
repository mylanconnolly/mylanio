---
title: 'EctoDBScanner'
date: 2026-02-22
summary: 'An Elixir library that scans PostgreSQL databases at runtime to discover schemas, tables, columns, constraints, and enum-like values - with parallel execution via Reactor.'
tags:
  - Backend
links:
  - icon: brands/github
    url: https://github.com/mylanconnolly/ecto-db-scanner
  - icon: link
    url: https://hexdocs.pm/ecto_db_scanner
---

A PostgreSQL database scanner that connects at runtime, discovers the full structure, maps column types to generalized Elixir types, and detects enum-like columns. Useful as a foundation for building dynamic query and reporting systems against configurable databases.

## Key Features

- **Full schema discovery** - schemas, tables, views, and materialized views
- **Type mapping** - PostgreSQL types mapped to Elixir types (`:string`, `:integer`, `:datetime`, arrays, etc.)
- **Constraint detection** - primary keys, foreign keys, nullability, and defaults
- **Enum detection** - discovers PostgreSQL ENUM types and heuristically detects enum-like string columns by cardinality
- **Parallel execution** - scans run concurrently via a Reactor pipeline

## Example

```elixir
{:ok, database} = EctoDBScanner.scan(
  hostname: "localhost",
  username: "postgres",
  database: "my_db"
)

# Returns structured results:
# %Database{schemas: [%Schema{tables: [%Table{columns: [...]}]}]}
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Elixir |
| Database | PostgreSQL |
| Parallelism | Reactor pipeline |
