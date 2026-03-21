---
name: bilingual-programming
description: "Multi-language bilingual (EN/CN) programming skill with interleaved comment format, performance optimization, and comprehensive logging best practices."
---

# Bilingual Programming Skill

## Purpose

Provides standardized bilingual (English/Chinese) code comments across multiple programming languages. Each language-specific reference covers idiomatic patterns, best practices, and common pitfalls.

## Core Principles

1. **Interleaved EN/CN Comments**: EN line followed by CN line, never mixed
2. **No Single-Line Mixed**: `/** EN: xxx / CN: xxx */` is forbidden
3. **UTF-8 Encoding**: All Chinese text files UTF-8 without BOM
4. **Comprehensive @params**: Every parameter documented
5. **Language Idiomatic**: Follow each language's native style
6. **Performance Aware**: Avoid anti-patterns per language

## Directory Structure

```
bilingual-programming/
├── SKILL.md
├── references/
│   ├── 01-cpp.md              # C++ core patterns
│   ├── 01a-unreal-engine.md    # UE C++ extension (separate reference)
│   ├── 02-nodejs.md           # Node.js / TypeScript
│   ├── 03-python.md           # Python
│   ├── 04-go.md               # Go
│   ├── 05-java.md             # Java
│   └── 06-rust.md             # Rust
└── scripts/
    └── validate-encoding.py   # UTF-8 BOM checker
```

## Quality Checklist

- [ ] EN/CN interleaved on separate lines
- [ ] All parameters documented with `@param`
- [ ] Return value documented with `@return`
- [ ] Exception cases documented with `@throws`
- [ ] Usage examples provided
- [ ] Performance implications noted
- [ ] UTF-8 encoding verified
- [ ] Language idiomatic patterns followed
