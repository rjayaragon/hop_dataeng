# Git Workflow Guide

## Git Setup & Basics - LEARN FIRST SESSION

**Before any commits, you need:**

### Prerequisites Check (Next Session)
1. **Git installed** - Check with: `git --version`
2. **Git configured** - Set your name and email:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```
3. **Repository initialized** - Check if `.git/` folder exists
4. **Remote set up** - Check with: `git remote -v` (should show origin)

### Step-by-Step Workflow (Learn Session 4)

**Step 1: Check current status**
```bash
git status
```
Shows: Modified files, untracked files, branch name

**Step 2: See what changed**
```bash
git diff                    # Shows changes in tracked files
git log --oneline -5        # Shows last 5 commits
```

**Step 3: Stage your changes**
```bash
git add .                   # Add all changes
# OR
git add filename.py         # Add specific file
```

**Step 4: Write commit message**
Think about: What layer? What did you complete? Why?

Example:
```
Silver layer: Complete data validation and transformation

- Loaded 1270 repositories from bronze layer
- Removed nulls and standardized date formats
- Added quality flags for missing language/description
- Saved cleaned data to parquet format
```

**Step 5: Create the commit**
```bash
git commit -m "Silver layer: Complete data validation and transformation"
```

**Step 6: Verify it worked**
```bash
git log --oneline -3        # See your new commit
git status                  # Should show "nothing to commit"
```

**Common Issues & Fixes:**

| Problem | Solution |
|---------|----------|
| "fatal: not a git repository" | You're not in the repo folder. Navigate to `/hop_dataeng/` |
| "nothing added to commit" | Run `git add .` first |
| "Author identity unknown" | Run git config commands (see Prerequisites) |
| "detached HEAD state" | Run `git checkout main` to return to main branch |

---

## Git Workflow - MANDATORY FOR ALL COMPLETED WORK

**When to commit:**
- After completing each layer (bronze, silver, gold)
- When fixing significant bugs or blockers
- After major refactoring or feature work
- Never commit: incomplete work, intermediate experiments, or debugging code

**Commit message format:**
```
[Layer/Component] Brief description of what was completed

More detailed explanation if needed.

Examples:
- "Silver layer: Complete data validation and transformation"
- "Bronze layer: Fix API rate limiting and error handling"
- "Gold layer: Add business aggregations and save to parquet"
```

**Mentor Reminder Protocol:**
At the end of each session or when a layer is completed, Claude will ask:
"Should I commit this work to git? Here's what would be committed: [summary]"

**Basic git commands you'll use:**
```bash
git status              # See what changed
git add .              # Stage all changes
git commit -m "message" # Create commit
git log --oneline      # See recent commits
```

**Why this matters:**
- Documents your learning journey
- Shows progress for accountability
- Creates safety net (can revert if needed)
- Professional practice for job interviews
- Clear history of decisions made
