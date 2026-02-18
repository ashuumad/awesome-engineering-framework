# CLAUDE.md

This file provides guidance for AI assistants working with the **Awesome Engineering Framework** repository.

## Repository Overview

**Awesome Engineering Framework** is a starter/skeleton project intended to serve as a foundation for building robust engineering solutions. The repository is in early development and currently contains:

- A `README.md` with project description, feature highlights, and placeholder setup instructions
- A GitHub Actions CI workflow (`.github/workflows/blank.yml`) triggered on pushes and pull requests to `main`
- This `CLAUDE.md` guidance file

There is no application source code yet. Contributors (human or AI) are expected to build out the framework incrementally.

## Repository Structure

```
awesome-engineering-framework/
├── .github/
│   └── workflows/
│       └── blank.yml       # CI workflow (runs on push/PR to main)
├── README.md               # Project overview and setup instructions
└── CLAUDE.md               # This file
```

## Branch Conventions

- **`main`**: The primary protected branch. All changes must go through pull requests.
- **`master`**: Legacy local branch; not present on the remote. `main` is the active default branch used by CI.
- **Feature branches**: Use descriptive names, e.g., `feature/<description>` or `fix/<description>`.
- **AI-generated branches**: Must start with `claude/` and end with the session ID, e.g., `claude/add-claude-documentation-NN081`.

## Development Workflow

1. **Create a feature branch** from `main` (or the designated branch for the session).
2. **Make changes** with clear, focused commits.
3. **Push the branch** to origin: `git push -u origin <branch-name>`.
4. **Open a pull request** targeting `main`.
5. **CI runs automatically** via GitHub Actions on every push and PR to `main`.

All merges to `main` have been done via pull requests (PRs #1 through #7 in the existing history). Direct pushes to `main` are not permitted.

### Git Conventions

- Write concise, imperative commit messages (e.g., `Add user authentication module`, not `Added user auth`).
- Keep commits focused: one logical change per commit.
- Never force-push to `main`.
- Never commit secrets, credentials, or environment files.

## CI/CD

The CI pipeline is defined in `.github/workflows/blank.yml`:

- **Trigger**: Push or pull request to `main`; also manually via `workflow_dispatch`.
- **Runner**: `ubuntu-latest`
- **Steps**:
  1. `actions/checkout@v4` — checks out the repository
  2. Echo a single-line message (placeholder)
  3. Echo a multi-line message (placeholder)
- **Current state**: Placeholder echo commands only — no real build, test, or lint steps yet.

When the project gains source code, the workflow should be updated to include:
- Dependency installation
- Linting
- Testing
- Build verification

## Conventions for AI Assistants

### General

- **Read files before modifying them.** Never propose changes to code that hasn't been read first.
- **Avoid over-engineering.** Only add what is explicitly requested or clearly necessary.
- **Do not create unnecessary files.** Prefer editing existing files; avoid creating new documentation unless asked.
- **Do not add comments or docstrings** to code you didn't change.

### Codebase Expansion

When the project grows, update this file to reflect:
- New directory structure and module descriptions
- Language/framework choices and versions
- Test commands and lint commands
- Environment variable requirements
- Dependency management approach

### Working on This Repository

- Always develop on the designated branch (never push directly to `main`).
- Commit and push all changes before finishing a session.
- If a `package.json`, `pyproject.toml`, `go.mod`, or similar file is added, document the corresponding install, test, and run commands here.

## Key Files Reference

| File | Purpose |
|------|---------|
| `README.md` | User-facing project overview and setup guide |
| `.github/workflows/blank.yml` | GitHub Actions CI pipeline |
| `CLAUDE.md` | AI assistant guidance (this file) |

## TODO / Known Gaps

The following are not yet defined and should be documented here once established:

- Language/runtime and version requirements
- Dependency installation command
- Build command
- Test command
- Lint/format command
- Environment variables and configuration
- Deployment process

---

_Last updated: 2026-02-18_
