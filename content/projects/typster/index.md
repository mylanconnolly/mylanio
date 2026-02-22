---
title: 'Typster'
date: 2026-02-22
summary: 'An Elixir wrapper for the Typst document preparation system  - render templates to PDF, SVG, and PNG with variable binding, package support, and Rust-powered NIF performance.'
tags:
  - Backend
links:
  - icon: brands/github
    url: https://github.com/mylanconnolly/typster
  - icon: link
    url: https://hexdocs.pm/typster
---

Typster is an Elixir wrapper for [Typst](https://typst.app), providing ergonomic functions for rendering Typst templates to PDF, SVG, and PNG formats. Powered by Rust via NIFs for high performance.

## Key Features

- **Multiple output formats**  - render to PDF, SVG, or PNG
- **Variable binding**  - inject Elixir data into templates with deep nesting support (maps, lists, nested structures)
- **Package support**  - use Typst packages from the official registry with automatic download and local caching
- **PDF metadata**  - embed title, author, keywords, and more
- **Fast**  - Rust-powered NIFs; typical invoice rendering in under 50ms
- **Fully thread-safe**  - designed for concurrent use in Phoenix applications, tested with 100 concurrent renders

## Example

```elixir
template = """
= Invoice for #customer_name

*Date:* #invoice_date
*Amount:* \\$#amount
"""

variables = %{
  customer_name: "Acme Corp",
  invoice_date: "2025-10-03",
  amount: 1234.56
}

{:ok, pdf} = Typster.render_pdf(template, variables: variables)
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Elixir |
| Native Code | Rust via Rustler NIFs |
| Typesetting | Typst |
| Testing | ExUnit + StreamData (property-based) |
| Distribution | Hex.pm with precompiled binaries |
