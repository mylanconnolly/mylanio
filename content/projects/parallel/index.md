---
title: 'Parallel'
date: 2026-02-22
summary: 'A Go replacement for GNU parallel that runs commands in parallel with configurable workers and Go template support - 10x faster in benchmarks.'
tags:
  - Backend
links:
  - icon: brands/github
    url: https://github.com/mylanconnolly/parallel
---

A replacement for GNU parallel written in Go. Started as a learning exercise in Go parallelism, but became a tool I regularly use. Runs a configurable pool of workers through a list of jobs, using only stdlib packages.

## Features

- **Configurable workers** - defaults to one per CPU, adjustable with `-j`
- **Command templating** - Go templates via `-t` flag with built-in functions (`basename`, `dirname`, `noExt`, `toUpper`, etc.)
- **Stdlib only** - zero external dependencies
- **Fast** - ~10x faster than GNU parallel in benchmarks (2.5s vs 26s running md5sum across the Go source tree)

## Example

```shell
# MD5 sum of every file in /etc
find /etc -type f | parallel md5sum

# Same thing with only 2 workers
find /etc -type f | parallel -j 2 md5sum

# Copy files up a level using templates
parallel -a ./files.txt -t 'cp {{.Input}} {{.Input | dirname | dirname}}'
```

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Go (stdlib only) |
| Concurrency | goroutines + channels |
| Templating | Go `text/template` |
