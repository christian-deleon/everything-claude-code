# Development Workflow

> This file extends [common/git-workflow.md](./git-workflow.md) with the full feature development process that happens before git operations.

The Feature Implementation Workflow describes the development pipeline: research, planning, TDD, code review, and then committing to git.

## MCP Tool Selection (Cost Optimization)

**CRITICAL:** Follow this priority order to minimize API costs:

### Documentation & Research

1. **Context7** (`mcp_context7_*`) - **FIRST CHOICE for docs**
   - Framework/library documentation (Next.js, React, Supabase, Rust, Go, Python, etc.)
   - Live, up-to-date API references
   - Examples: "How to use React hooks", "Supabase RLS", "Next.js app router"

2. **Brave Search** (`mcp_brave-search_*`) - **FREE for web searches**
   - General web searches, tutorials, blog posts
   - Current news, events, and trending topics
   - "How to" guides and best practices
   - When Context7 doesn't have the docs
   - Location-based queries ("near me")

3. **Firecrawl** (`mcp_firecrawl_*`) - **COSTS MONEY - Last resort only**
   - **ONLY when scraping/crawling a specific website**
   - Deep content extraction from non-indexed sites
   - Structured data extraction with schemas
   - **NEVER for documentation or general web searches**

### Cost-Saving Rules

- ❌ **NEVER** use Firecrawl for documentation lookups
- ❌ **NEVER** use Firecrawl for general web searches
- ✅ **ALWAYS** try Context7 first for framework/library docs
- ✅ **ALWAYS** use Brave Search for general information (it's FREE)
- ✅ **ONLY** use Firecrawl when you need to scrape a specific website

## Feature Implementation Workflow

0. **Research & Reuse** _(mandatory before any new implementation)_
   - **GitHub code search first:** Run `gh search repos` and `gh search code` to find existing implementations, templates, and patterns before writing anything new.
   - **Web research (use Brave Search MCP - FREE):** General web searches for tutorials, best practices, and blog posts.
   - **Documentation (use Context7 MCP):** Framework/library docs for technical references.
   - **Check package registries:** Search npm, PyPI, crates.io, and other registries before writing utility code. Prefer battle-tested libraries over hand-rolled solutions.
   - **Search for adaptable implementations:** Look for open-source projects that solve 80%+ of the problem and can be forked, ported, or wrapped.
   - Prefer adopting or porting a proven approach over writing net-new code when it meets the requirement.
   - **See "MCP Tool Selection" above for cost-optimized research workflow.**

1. **Plan First**
   - Use **planner** agent to create implementation plan
   - Generate planning docs before coding: PRD, architecture, system_design, tech_doc, task_list
   - Identify dependencies and risks
   - Break down into phases

2. **TDD Approach**
   - Use **tdd-guide** agent
   - Write tests first (RED)
   - Implement to pass tests (GREEN)
   - Refactor (IMPROVE)
   - Verify 80%+ coverage

3. **Code Review**
   - Use **code-reviewer** agent immediately after writing code
   - Address CRITICAL and HIGH issues
   - Fix MEDIUM issues when possible

4. **Commit & Push**
   - Detailed commit messages
   - Follow conventional commits format
   - See [git-workflow.md](./git-workflow.md) for commit message format and PR process
