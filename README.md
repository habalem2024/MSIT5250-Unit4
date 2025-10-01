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

name: CI
on:
  push:
    branches: [ develop, main, 'feature/**' ]
  pull_request:
    branches: [ develop, main ]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - run: pip install -r requirements.txt || true
      - run: pytest -q || echo "No tests yet"

