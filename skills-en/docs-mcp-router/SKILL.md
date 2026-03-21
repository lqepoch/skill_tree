---
name: docs-mcp-router
description: Route AWS, Azure, Google, GitHub, Cloudflare, OpenAI, and Anthropic documentation questions to the official MCP or primary-docs source. Use when Codex needs up-to-date API docs, SDK references, examples, troubleshooting, release notes, or product guidance for these ecosystems.
---

# Docs MCP Router

## Purpose

Use this skill when the user asks about official documentation, API behavior, SDK usage, examples, troubleshooting, or release notes for a supported vendor. Prefer primary sources. Do not answer from memory.

## Routing

- AWS: use `mcp__aws_knowledge_mcp__aws__search_documentation`, then `mcp__aws_knowledge_mcp__aws__read_documentation` when full context is needed.
- Azure: use `mcp__microsoft_docs_mcp__microsoft_docs_search`, then `mcp__microsoft_docs_mcp__microsoft_docs_fetch`; use `mcp__microsoft_docs_mcp__microsoft_code_sample_search` for code examples.
- Google: use `mcp__google_developer_knowledge__search_documents`, then `mcp__google_developer_knowledge__get_documents`.
- GitHub: use `mcp__github__search_code` against the official `github/docs` repository for product docs, and `mcp__github__get_file_contents` to read the matched page. Use issue/PR tools only for repo workflow questions.
- Cloudflare: use `mcp__cloudflare_docs_mcp__search_cloudflare_documentation`; use `mcp__cloudflare_docs_mcp__migrate_pages_to_workers_guide` for Pages-to-Workers migrations.
- OpenAI: use `mcp__openaiDeveloperDocs__search_openai_docs`, then `mcp__openaiDeveloperDocs__fetch_openai_doc`; use `mcp__openaiDeveloperDocs__list_openai_docs` and `mcp__openaiDeveloperDocs__get_openapi_spec` when needed.
- Anthropic: if a dedicated Anthropic docs MCP exists in the current environment, use it; otherwise do not guess and use the official Anthropic docs site only when a browsing fallback is explicitly allowed.

## Response Rules

- Identify the vendor before searching if the request is ambiguous.
- Search each vendor separately for cross-vendor comparisons.
- Prefer exact page titles, URLs, or API references in the final answer.
- Note when a source is official but not MCP-backed.
- If no primary source is available, say so plainly.
