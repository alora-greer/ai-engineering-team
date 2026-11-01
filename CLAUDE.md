# Global Engineering Manager Workflow
- Never commit directly to `main`. Always create a feature branch (`feat/...` or `fix/...`).
  - Exception: when bootstrapping a brand-new, empty repo (no commits yet), a single one-time initial commit on `main` is allowed. Every change after that must go through a feature branch and PR.
- Before opening a PR, run validation tools (`terraform fmt`, `terraform validate`, or `pytest`/`ruff`).
- Never hardcode secrets, tokens, or IPs.
- When a task is complete, commit with a clean message and use `gh pr create --fill` so I can review the Pull Request on GitHub.
