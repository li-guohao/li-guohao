# Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Refresh the public GitHub profile README repository for `li-guohao/li-guohao`.

**Architecture:** Update the existing remote repository history rather than replacing it with an unrelated local root commit. Use one Markdown profile README plus one static SVG asset, with support documentation under `docs/superpowers/` for traceability.

**Tech Stack:** Git, GitHub CLI, GitHub profile README conventions, GitHub-flavored Markdown, static SVG, Shields.io badges.

---

### Task 1: Repository Alignment

**Files:**
- Modify: `.git/config`

- [x] **Step 1: Verify authenticated account**

Run: `$env:GH_TOKEN = [Environment]::GetEnvironmentVariable('GITHUB_TOKEN','User'); gh auth status`

Expected: authenticated account is `li-guohao`.

- [x] **Step 2: Check profile README repository**

Run: `gh repo view li-guohao/li-guohao --json nameWithOwner,defaultBranchRef,isPrivate,url`

Expected: repository exists, is public, and default branch is `main`.

- [x] **Step 3: Align local worktree with remote history**

Run: `git fetch origin main; git branch codex/local-draft HEAD; git switch -c codex/profile-readme-refresh origin/main`

Expected: local work continues from `origin/main`, preserving existing remote history.

### Task 2: README Refresh

**Files:**
- Modify: `README.md`

- [x] **Step 1: Replace template-heavy README with compact profile**

Create a README containing:

```markdown
Now
Selected Original Work
Operating Notes
Stack Signals
Contact
```

Expected: the README removes placeholder social links, oversized widget sections, trophy walls, quote cards, and excessive badge grids.

- [x] **Step 2: Verify Markdown links**

Run: `Select-String -Path README.md -Pattern 'https://github.com/li-guohao'`

Expected: GitHub profile and selected repository links are present.

- [x] **Step 3: Correct the project-selection rule**

Run: `Invoke-RestMethod -Uri 'https://api.github.com/users/li-guohao/repos?per_page=100&sort=pushed&direction=desc'`

Expected: every repository in `Selected Original Work` is selected from records where `fork=false`; `worldmonitor` and `agentguard` are excluded because they are forks.

### Task 3: Static Visual Asset

**Files:**
- Create: `assets/profile-banner.svg`

- [x] **Step 1: Create SVG banner**

Create `assets/profile-banner.svg` with:

```txt
Guohao Li
li-guohao
agents / applied AI / small products
```

Expected: the banner is static, self-contained, and renderable by GitHub.

- [x] **Step 2: Verify SVG structure**

Run: `[xml](Get-Content -Raw assets/profile-banner.svg) | Out-Null`

Expected: PowerShell parses the SVG as XML without errors.

### Task 4: Commit And Push

**Files:**
- Modify: repository history

- [x] **Step 1: Review changed files**

Run: `git status --short`

Expected: `README.md`, `assets/profile-banner.svg`, and `docs/superpowers/` are the only intended changed paths.

- [x] **Step 2: Commit refresh**

Run: `git add README.md assets/profile-banner.svg docs/superpowers/specs/2026-05-18-profile-readme-design.md docs/superpowers/plans/2026-05-18-profile-readme.md; git commit -m "feat: refresh profile README"`

Expected: a new commit is created on top of `origin/main`.

- [x] **Step 3: Push to profile README repository**

Run: `$env:GH_TOKEN = [Environment]::GetEnvironmentVariable('GITHUB_TOKEN','User'); git push origin HEAD:main`

Expected: remote `main` updates successfully.

- [ ] **Step 4: Commit and push no-fork correction**

Run: `git add README.md docs/superpowers/specs/2026-05-18-profile-readme-design.md docs/superpowers/plans/2026-05-18-profile-readme.md; git commit -m "fix: exclude forked repos from profile README"; git push origin HEAD:main`

Expected: remote `main` contains the corrected no-fork profile README.

### Task 5: Final Verification

**Files:**
- Read: `README.md`
- Read: `assets/profile-banner.svg`

- [ ] **Step 1: Check repository status**

Run: `git status --short --branch`

Expected: branch is clean after push.

- [ ] **Step 2: Verify remote README is updated**

Run: `gh api repos/li-guohao/li-guohao/readme --header 'Accept: application/vnd.github.raw'`

Expected: returned README includes `Selected Original Work`, `asam-attention`, `causal-finance`, and `Profile design note`; it does not include `worldmonitor` or `agentguard`.

## Plan Self-Review

- Spec coverage: all approved README structure and constraints are covered.
- Placeholder scan: no unfinished markers or placeholder social links remain.
- Type consistency: file paths and commands are consistent with the Windows workspace and GitHub profile repository target.
- Ownership check: main showcase entries must be selected from `fork=false` repositories only.
