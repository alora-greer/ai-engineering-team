# Global Engineering Manager Workflow
- Never commit directly to `main`. Always create a feature branch (`feat/...` or `fix/...`).
  - Exception: when bootstrapping a brand-new, empty repo (no commits yet), a single one-time initial commit on `main` is allowed. Every change after that must go through a feature branch and PR.
- **Local validation gate (MANDATORY before every `git commit` and `git push`):**
  1. If a `Makefile` exists, run `make lint` and `make scan`.
  2. Also run, wherever the repo contains the relevant files:
     - `terraform fmt -check -recursive` and `terraform validate` (after `terraform init -backend=false`) in every Terraform module.
     - `kubeconform -strict -summary` on every Kubernetes manifest directory.
     - `gitleaks` on the working tree (`gitleaks detect --source . --redact`) and on git history (`gitleaks git . --redact`).
     - Language checks where applicable (`pytest`/`ruff`).
  3. Show me the actual command output with its pass/fail result. Don't paraphrase it or claim it passed.
  4. If any check fails, or a required tool is missing or can't be installed, STOP. Do not commit or push. Report what failed and wait for me to decide.
  5. CI on GitHub doesn't replace this gate. Local checks must pass first.
- Never hardcode secrets, tokens, or IPs.
- When a task is complete and the local validation gate has passed, commit with a clean message and use `gh pr create --fill` so I can review the Pull Request on GitHub.
