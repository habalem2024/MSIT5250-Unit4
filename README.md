## Branching Strategy (Gitflow)
- **main** – production-ready code
- **develop** – integration branch for completed features
- **feature/*** – short-lived branches for new work (e.g., `feature/login-page`)
- **release/*** – stabilization and versioning before production (e.g., `release/v1.0`)
- **hotfix/*** – urgent fixes from `main` (e.g., `hotfix/checkout-bug`)

**Pull Requests**
- Features: `feature/*` → `develop`
- Releases: `release/*` → `main` (and back-merge to `develop`)
- Hotfixes: `hotfix/*` → `main` (and back-merge to `develop`)
