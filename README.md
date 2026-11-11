# AI Engineering Team & Claude Code Dotfiles

Version-controlled global configuration (`CLAUDE.md`) and specialist subagents (`agents/`) for orchestrating multi-agent DevOps, Cloud Infrastructure, and Data Engineering workflows via Claude Code.

## Specialist Subagents
- **`iac-architect`**: Designs modular, least-privilege Terraform (AWS/GCP) and Kubernetes (K3s/Helm) manifests.
- **`data-engineer`**: Builds resilient Python ETL pipelines for sanitizing unstructured PDF data into GCP BigQuery.
- **`security-reviewer`**: Performs read-only DevSecOps audits on IAM policies, secrets handling, and syntax prior to opening GitHub PRs.

## Installation (Symlink Setup)
```bash
git clone https://github.com/alora-greer/ai-engineering-team.git ~/workspace/ai-engineering-team
mkdir -p ~/.claude
ln -sf ~/workspace/ai-engineering-team/CLAUDE.md ~/.claude/CLAUDE.md
ln -sfn ~/workspace/ai-engineering-team/agents ~/.claude/agents
```
