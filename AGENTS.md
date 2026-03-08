# ECC — Personal AI Development Plugin

Dotfiles submodule at `~/.dotfiles/ecc/`. Provides agents, skills, hooks, commands, rules, and MCP configurations for Python, Go, and TypeScript/JS development.

## Architecture

- **agents/** - Specialized subagents (planner, code-reviewer, tdd-guide, etc.)
- **skills/** - Workflow definitions and domain knowledge (coding standards, patterns, testing)
- **commands/** - Slash commands (/tdd, /plan, /e2e, /code-review, etc.)
- **hooks/** - Trigger-based automations (session persistence, pre/post-tool hooks)
- **rules/** - Always-follow guidelines (common, golang, python, typescript)
- **mcp-configs/** - MCP server configurations
- **scripts/** - Node.js utilities for hooks and setup
- **contexts/** - Reusable context files

## Key Commands

- `/tdd` - Test-driven development workflow
- `/plan` - Implementation planning
- `/e2e` - Generate and run E2E tests
- `/code-review` - Quality review
- `/build-fix` - Fix build errors
- `/learn` - Extract patterns from sessions
- `/skill-create` - Generate skills from git history

## Development Notes

- Package manager detection: npm, pnpm, yarn, bun (configurable via `CLAUDE_PACKAGE_MANAGER` env var or project config)
- Agent format: Markdown with YAML frontmatter (name, description, tools, model)
- Skill format: Markdown with clear sections for when to use, how it works, examples
- Hook format: JSON with matcher conditions and command/notification hooks
