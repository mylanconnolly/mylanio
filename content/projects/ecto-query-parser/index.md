---
title: 'EctoQueryParser'
date: 2026-02-22
summary: 'An Elixir library that converts human-readable filter strings into Ecto WHERE clauses - with automatic joins, JSONB access, functions, and field restrictions.'
tags:
  - Backend
links:
  - icon: brands/github
    url: https://github.com/mylanconnolly/ecto-query-parser
  - icon: link
    url: https://hexdocs.pm/ecto_query_parser
---

A query language parser for Ecto that converts human-readable filter strings into Ecto `WHERE` clauses. Designed for building user-facing search and filtering interfaces where filter expressions come from untrusted input.

## Key Features

- **Rich query language** - equality, comparison, LIKE/ILIKE, substring search, array containment, and logical operators with grouping
- **Built-in functions** - string (UPPER, LOWER, TRIM, LENGTH, etc.), math (ABS, FLOOR, CEIL), and date/time (NOW, DATE_TRUNC, interval arithmetic)
- **Automatic joins** - dotted identifiers like `author.company.name` resolve to LEFT JOINs via schema associations, with deduplication
- **JSONB support** - dotted paths on `:map` fields generate `json_extract_path` queries with correct type casting
- **Field restrictions** - control which fields users can filter on, with type annotations for JSON paths
- **Schemaless queries** - define associations inline for dynamic table access without Ecto schemas
- **Integration tested** - all generated SQL verified against a real PostgreSQL database

## Example

```elixir
# Parse a filter string into an Ecto query
{:ok, query} = EctoQueryParser.apply(
  Post,
  ~s{author.name == "alice" AND status == "published"}
)
Repo.all(query)

# With field restrictions and JSONB type casting
{:ok, query} = EctoQueryParser.apply(Post, filter,
  allowed_fields: [
    name: :string,
    metadata: :map,
    "metadata.view_count": :integer
  ]
)
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Elixir |
| Database | PostgreSQL via Ecto |
| Testing | ExUnit + Docker Compose (integration tests) |
