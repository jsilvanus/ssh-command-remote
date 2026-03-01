# CLAUDE.md

This file provides guidance for AI assistants (e.g., Claude Code) working in this repository.

## Project Overview

**Repository:** `jsilvanus/ssh-command-remote`
**Purpose:** This project is in its initial state. Based on the repository name, it is intended to implement SSH-based remote command execution functionality.

> This CLAUDE.md should be updated as the codebase evolves to reflect the actual structure, stack, and conventions in use.

## Repository Structure

The repository is currently empty (just initialized). As files are added, update this section to reflect the actual layout, for example:

```
ssh-command-remote/
├── CLAUDE.md          # This file
├── README.md          # User-facing documentation (add when ready)
├── src/               # Source code
├── tests/             # Test suite
└── ...
```

## Git Conventions

### Branch Naming

- AI-developed feature branches use the prefix `claude/` followed by a short descriptor and a session ID suffix, e.g.:
  ```
  claude/init-git-repo-KGoB2
  ```
- Human feature branches should follow the project's chosen convention (e.g., `feature/`, `fix/`, `chore/`).
- **Never push directly to `main` or `master`.**

### Commit Messages

- Write short, imperative-mood subject lines (50 chars or fewer).
- Include a blank line before the body when more context is needed.
- Append the Claude Code session URL at the end of AI-authored commits:
  ```
  Short description of change

  https://claude.ai/code/session_<id>
  ```

### Push Rules

- Always push with tracking: `git push -u origin <branch-name>`
- Branches must start with `claude/` for AI-authored work (otherwise push returns HTTP 403).
- On network failure, retry up to 4 times with exponential back-off (2 s, 4 s, 8 s, 16 s).

## Development Workflow

1. **Branch** — Create or check out the designated `claude/` branch before making changes.
2. **Implement** — Make focused, minimal changes that address the task at hand.
3. **Test** — Run the project's test suite before committing (update this section once tests exist).
4. **Commit** — Stage specific files (avoid `git add -A` on first pass); write a clear commit message.
5. **Push** — Push to the feature branch; do **not** merge or create a PR unless explicitly asked.

## AI Assistant Guidelines

### General Principles

- **Read before editing.** Always read a file before modifying it.
- **Minimal changes.** Only change what is directly required by the task. Do not refactor unrelated code, add docstrings unprompted, or introduce new abstractions speculatively.
- **No unnecessary files.** Do not create README.md, documentation files, or helper utilities unless explicitly requested.
- **Security first.** Avoid introducing command injection, SQL injection, XSS, or other OWASP Top 10 vulnerabilities. Validate only at system boundaries.
- **No time estimates.** Do not predict how long tasks will take.

### Irreversible / Risky Actions

Always confirm with the user before:
- Deleting files or branches
- Force-pushing (`--force`)
- Resetting hard (`git reset --hard`)
- Modifying CI/CD pipelines or shared infrastructure
- Sending messages or posting to external services

### Codebase Searches

- Use `Glob` for file pattern searches.
- Use `Grep` for content searches.
- Use `Read` to inspect specific files.
- For broad, multi-step exploration delegate to the `Explore` subagent.

## Testing

_No test framework has been configured yet. Update this section once tests are set up._

## Environment Notes

- **Platform:** Linux
- **Shell:** bash/zsh
- **Working directory:** `/home/user/ssh-command-remote`
- **Remote:** `http://127.0.0.1:34221/git/jsilvanus/ssh-command-remote`

---

_Last updated: 2026-03-01. Keep this file current as the project grows._
