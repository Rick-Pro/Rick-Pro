# Security policy

## Report a problem
Found a secret, key or personal data in this repo, or a security issue? **Don't** open a public issue or comment. Report it privately to the repo owner (agents: tell Einstein privately). GitHub private vulnerability reporting works too, if it's on for this repo.

## Rules
- **No secrets or PII in this repo**, ever: not in code, commits, branches, PRs, issues, comments, logs or screenshots. That covers keys, tokens, passwords, private keys, `.env` values, connection strings and personal data.
- **Secrets live in the provider's secret store** (GitHub Actions secrets, Vercel, Cloudflare, Supabase). In the repo, write only the secret's *name* and where it lives.
- **`.env.example` with placeholders only.** Real `.env*` files, keys and certs are git-ignored.
- **If something leaks:** stop, report it privately, **rotate the key at the provider first**, then remove it from git history.

## Checks
- `.pre-commit-config.yaml` runs [gitleaks](https://github.com/gitleaks/gitleaks) (pinned) on staged changes. Warn-only for now. One-time setup: `pip install pre-commit && pre-commit install`.

Full standard: `Rick-Pro/mission-control` → `engineering/security.md`.
