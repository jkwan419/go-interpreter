# Go Interpreter

A tree-walking interpreter for the Monkey programming language, written in Go.

---

## About

This project implements an interpreter from scratch — no third-party libraries, no parser generators. Everything from the lexer to the evaluator is hand-written in Go, following the book's test-driven approach.

## Features

The interpreter currently supports:

- Integer and boolean literals
- Prefix and infix expressions (`-`, `!`, `+`, `-`, `*`, `/`, `<`, `>`, `==`, `!=`)
- Conditionals (`if` / `else`)
- Return statements
- Variable bindings with `let`
- Functions and closures
- A REPL for interactive use

```
>> let add = fn(a, b) { a + b; };
>> add(5, 10)
15
>> let factorial = fn(n) { if (n == 0) { 1 } else { n * factorial(n - 1) } };
>> factorial(5)
120
```
## Architecture

The interpreter follows a classic pipeline:

```
Source Code → Lexer → Tokens → Parser → AST → Evaluator → Result
```

- **Lexer** — Scans source text into tokens (identifiers, literals, operators, keywords).
- **Parser** — A Pratt parser (top-down operator precedence) that builds an abstract syntax tree.
- **Evaluator** — Tree-walks the AST and evaluates each node, producing Monkey objects.

## Getting Started

### Prerequisites

- Go 1.21+

### Run the REPL

```
go run main.go

```

### Run Tests

```
go test ./...
```
