# Git Commands for QA Engineers

> QA engineers need Git to manage test scripts, track changes, and collaborate in CI/CD pipelines.

---

## Essential Git Commands

### Setup
```bash
git config --global user.name "Shivam Rai"
git config --global user.email "shivam@qa.com"
git config --global core.editor "code"    # VS Code as default editor
```

### Repository Setup
```bash
git init                          # Initialize new repo
git clone <url>                   # Clone existing repo
git clone <url> my-folder         # Clone into specific folder
```

### Daily Workflow
```bash
git status                        # Check what's changed
git add .                         # Stage all changes
git add tests/test_login.py       # Stage specific file
git commit -m "Add login test cases"
git push origin main              # Push to remote

git pull                          # Fetch + merge latest changes
git fetch                         # Fetch without merging
```

### Branches (Feature Branch Workflow)
```bash
git branch                        # List local branches
git branch feature/login-tests    # Create new branch
git checkout feature/login-tests  # Switch to branch
git checkout -b feature/api-tests # Create and switch in one command

git merge feature/login-tests     # Merge branch into current
git branch -d feature/login-tests # Delete branch (after merge)

git push origin feature/login-tests  # Push branch to remote
```

### View History
```bash
git log                           # Full history
git log --oneline                 # Compact history
git log --oneline -10             # Last 10 commits
git diff                          # View unstaged changes
git diff HEAD~1                   # Compare with previous commit
```

### Undo Changes
```bash
git restore test_login.py         # Discard unstaged changes
git restore --staged test_login.py # Unstage a file
git revert <commit-hash>          # Undo a commit (safe, creates new commit)
git reset --soft HEAD~1           # Undo last commit, keep changes staged
```

### Stashing (Save work temporarily)
```bash
git stash                         # Save current changes temporarily
git stash pop                     # Restore saved changes
git stash list                    # List all stashes
```

---

## Git Workflow for QA Teams

```bash
# 1. Start new test task
git pull origin main
git checkout -b feature/payment-test-cases

# 2. Write test cases, commit regularly
git add .
git commit -m "Add payment gateway positive test cases"
git commit -m "Add payment gateway negative test cases"

# 3. Push and create PR
git push origin feature/payment-test-cases
# Create Pull Request on GitHub/GitLab for peer review

# 4. After review and merge
git checkout main
git pull
git branch -d feature/payment-test-cases
```

---

## .gitignore for Test Projects

```gitignore
# Python
__pycache__/
*.pyc
.pytest_cache/
.venv/
venv/

# Reports and outputs
reports/
screenshots/
downloads/
*.html
*.xml

# Secrets
.env
config/secrets.py

# IDE
.vscode/
.idea/
```

---

## Git Commit Message Best Practices

```bash
# Good commit messages
git commit -m "Add BVA test cases for password length validation"
git commit -m "Fix: update login page locator after UI change"
git commit -m "Refactor: extract common assertions to base_page"
git commit -m "Add smoke test suite for Sprint 5 release"

# Bad commit messages
git commit -m "fix"
git commit -m "changes"
git commit -m "test"
```

**Format:** `<type>: <what you did>`
Types: `Add`, `Fix`, `Update`, `Refactor`, `Remove`, `Test`, `Docs`

---

## 📌 Key Takeaways

- `git status` before anything else — know your state
- Commit **small and often** with meaningful messages
- **Never commit** `.env` files or secrets
- Use **feature branches** for every task
- `git stash` saves you when you need to switch tasks quickly

---

*Shivam Rai | Software Testing MasterGuide*
