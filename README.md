# ⚙️ Project Template & GitHub Configuration

Welcome to your project repository template! This file documents the baseline repository architecture, automation settings, and security guardrails currently configured for this project.

> 💡 **Note on Customization:** This `README.md` and the configurations documented below represent the **current baseline setup**. As your project evolves, you can completely customize, update, or remove any part of this text and change the repository settings to better suit your development workflow.

---

## 🛠️ Current GitHub Repository Settings

This section describes the intended baseline configuration for this repository template (verify and adjust these settings in GitHub as needed for your project).

### 1. General Settings (Features & Pull Requests)
*Configured under: Settings -> General*

#### Features
*   [x] **Wikis** – Active (Wikis host documentation for your repository).
    *   [x] **Restrict editing to collaborators only** – Active.
*   [x] **Issues** – Active (Issues integrate lightweight task tracking into your repository).
    *   **Issue permissions**: Allowed by `All users`.
*   [ ] **Sponsorships** – Inactive.
*   [ ] **Discussions** – Inactive.
*   [x] **Projects** – Active (Projects are suitable for cross-repository development, feature work, and issue triage).
*   [x] **Pull requests** – Active (Pull requests allow others to suggest changes to your repository).
    *   **Pull request permissions**: Allowed by `All users`.

#### Pull Requests (Merge Behavior)
*   [x] **Allow merge commits** – Active (Adds all commits from the head branch to the base branch with a merge commit).
*   [x] **Allow squash merging** – Active (Combines all commits from the head branch into a single commit in the base branch).
*   [x] **Allow rebase merging** – Active (Adds all commits from the head branch onto the base branch individually).
*   [ ] **Always suggest updating pull request branches** – Inactive.
*   [ ] **Allow auto-merge** – Inactive (Turn on if you want GitHub to automatically merge PRs once status checks pass).
*   [ ] **Automatically delete head branches** – Inactive (Turn on to automatically delete feature branches after merging to keep the repository clean).

#### Commits, Pushes & Issues
*   [ ] **Require contributors to sign off on web-based commits** – Inactive.
*   [x] **Allow comments on individual commits** – Active.
*   [ ] **Include Git LFS objects in archives** – Inactive.
*   [ ] **Limit how many branches and tags can be updated in a single push** – Inactive.
*   [x] **Auto-close issues with merged linked pull requests** – Active (Automatically closes a linked issue whenever a pull request is merged).

---

### 2. Repository Ruleset Configuration
*Configured under: Settings -> Repository Rulesets*

### Ruleset Metadata & Targets
*   **Ruleset Name:** `main/master`
*   **Enforcement Status:** `Active`
*   **Bypass List:** `Empty` (Enforces these rules strictly for everyone, including repository owners/admins).
*   **Target Branches:** Target criteria are configured to match both `main` and `master` branches.

### Branch Rules
*   [ ] **Restrict creations** – Inactive.
*   [ ] **Restrict updates** – Inactive.
*   [x] **Restrict deletions** – Active (Prevents the `main`/`master` branches from being accidentally deleted).
*   [x] **Require linear history** – Active (Prevents merge commits from being pushed to target branches, ensuring a clean commit history). 
    *   *Note: This overrides your General Settings; classic merge commits will be blocked by this rule.*
*   [ ] **Require deployments to succeed** – Inactive / No environments added.
*   [ ] **Require signed commits** – Inactive.
*   [ ] **Require a pull request before merging** – Inactive (Enable this to prevent direct pushes, requiring at least 1 approval and enabling stale approval dismissal).

### Protection & Scanning Rules
*   [x] **Require status checks to pass** – Active.
    *   [x] **Require branches to be up to date before merging** – Active (Ensures code is tested against the latest target branch state).
    *   *Action Item:* Use **+ Add checks** to select your specific CI build pipeline workflow (e.g., `build` or `test`) once it runs for the first time.
*   [x] **Block force pushes** – Active (Prevents anyone from overwriting the Git history on production branches).
*   [x] **Require code scanning results** – Active.
    *   **Tool:** `CodeQL` (Security alerts threshold: `High or higher`, Alerts: `Errors`). Blocks the merge if static analysis finds significant security vulnerabilities.
*   [x] **Require code quality results** – Active.
    *   **Severity:** `Errors` (Blocks the merge if linting or quality scans detect unresolved errors).
*   [ ] **Restrict code coverage** – Inactive.
*   [ ] **Automatically request Copilot code review** – Inactive.

---

### 3. Advanced Security & Dependabot
*Configured under: Settings -> Code security and analysis*

### Dependabot Status
*   [x] **Dependency graph** – Active (Maintains a live manifest of all project dependencies).
*   [x] **Dependabot alerts** – Active (Triggers notifications when vulnerabilities are detected).
*   [ ] **Dependabot malware alerts** – Inactive (Recommended: Click *Enable* to receive alerts when malware is detected in third-party packages).
*   [x] **Dependabot security updates** – Active (Automatically opens Pull Requests to patch critical CVEs immediately).
*   [ ] **Grouped security updates** – Inactive (Recommended: Click *Enable* to combine multiple security patches into a single, clean Pull Request).
*   [ ] **Dependabot version updates** – Inactive (Enable by adding a `.github/dependabot.yml` configuration file and turning on version updates in **Settings -> Code security and analysis**).

### Dependabot Rules Presets (0 Rules Enabled)
*   [ ] **Dismiss low-impact alerts for development-scoped dependencies** – Disabled (Ensures all vulnerability alerts, including test and development dependencies, are visible and tracked).
*   [ ] **Dismiss package malware alerts** – Disabled (Prevents automatic dismissal of malware alerts to maintain maximum security awareness and oversight).
