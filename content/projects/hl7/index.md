---
title: 'HL7 Parser'
date: 2026-02-22
summary: 'A Go library for parsing HL7 messages using buffered I/O - stdlib only, lazy parsing, and used in production at multiple companies.'
tags:
  - Backend
links:
  - icon: brands/github
    url: https://github.com/mylanconnolly/hl7
---

A Go library for parsing HL7 (Health Level 7) messages. Built as a learning exercise in HL7 parsing and Go buffered I/O, it went on to be used in production at two companies.

## Features

- **`io.Reader` based** - accepts any `io.Reader` (files, TCP streams, buffers), making it easy to integrate with different data sources
- **Lazy parsing** - segments are parsed on access, so you can bail early if a message isn't relevant to your use case
- **Stdlib only** - zero runtime dependencies
- **Cross-platform** - tested on macOS, Windows, and Ubuntu across multiple Go versions

## Example

```go
reader := hl7.NewReader(file)

for {
    msg, err := reader.ReadMessage()
    if err == io.EOF {
        break
    }
    seg, _ := msg.Segment("MSH")
    // Work with segment fields...
}
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Go (stdlib only) |
| I/O | Buffered `io.Reader` |
| CI | GitHub Actions (multi-OS, multi-version) |
