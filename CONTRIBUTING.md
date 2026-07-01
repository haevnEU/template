# Contributing Guidelines

Thank you for contributing to this project! To maintain high code quality, security, and repository health, please follow these guidelines when working on this codebase.

## 🌿 Branching Strategy
- Always create a separate branch for your changes. Do not commit directly to production branches (`main` or `master`).
- Use descriptive branch names:
    - `feature/short-description` for new features.
    - `bugfix/short-description` for fixing issues.
    - `chore/short-description` for maintenance or CI/CD updates.

## 🚀 Pull Request Process
1. Ensure the code compiles and passes all local formatting/linting rules.
2. Open a Pull Request targeting the default branch.
3. Link the relevant Issue in the PR description (e.g., `Closes #12`).
4. Ensure the GitHub Actions CI pipeline passes successfully.
5. Review the custom checklist in the Pull Request template before merging.

## 🛡️ Code Quality Standards
- **Clean Code:** Write expressive, self-documenting code. Keep methods short and focused.
- **Linear History:** Rebase or squash your commits before merging to keep the Git history clean and flat.
- **Security First:** Never hardcode secrets, API keys, or personal credentials.