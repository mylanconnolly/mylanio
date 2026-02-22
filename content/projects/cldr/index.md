---
title: 'CLDR for Typst'
date: 2026-02-22
summary: 'A Typst package providing locale-aware number, date, and time formatting using Unicode CLDR data  - supporting 11 locales with currency, percent, and scientific notation.'
tags:
  - Backend
links:
  - icon: brands/github
    url: https://github.com/mylanconnolly/cldr
---

A [Typst](https://typst.app) package that brings Unicode CLDR (Common Locale Data Repository) formatting to your documents. Provides locale-aware number and date/time formatting across 11 locales.

## Features

- **Number formatting**  - decimal, percent, scientific, and currency formats with locale-specific grouping and symbols
- **Date formatting**  - short, medium, long, and full date formats
- **Time formatting**  - 12-hour and 24-hour formats per locale
- **DateTime formatting**  - combined date and time with independent format control
- **11 locales**  - English, Chinese, Hindi, Spanish, French, Arabic, Bengali, Portuguese, Russian, Japanese, German

## Example

```typst
#import "@preview/cldr:0.1.0": number, date

#number.format(1234.56)                    // "1,234.56"
#number.format(1234.56, locale: "de")      // "1.234,56"
#number.format(99.99, format: "currency", currency: "EUR")  // "€99.99"

#date.format(datetime.today(), locale: "ja")  // "2025/12/19"
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Typst |
| Data Source | Unicode CLDR v48.0.0 |
| Code Generation | Python |
| Distribution | Typst Package Registry (@preview) |
