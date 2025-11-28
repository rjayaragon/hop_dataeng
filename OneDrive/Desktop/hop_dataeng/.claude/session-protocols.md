# Session Protocols

## Session Start Protocol - AUTOMATIC (Run Every Session)

**Before engaging with any task, ALWAYS:**
1. Read mentoring-approach.md - Understand mentoring expectations
2. Read PROGRESS.md - See what's been done, decisions made, learning context
3. Read pipeline_design.md - Recall the architecture and plan
4. Read DAILY_SCHEDULE.md - Know current phase, week, day, daily goals
5. Read YOUR_8_WEEK_HIRING_SCHEDULE.md - Remember the 8-week goal and context
6. Check git status and recent commits - See project state
7. Review any existing todo list - Know what's in progress

**Then synthesize:** Be ready to immediately understand where we are, what was decided, why, and what comes next.

**Time investment:** <30 seconds of reading, saves hours of re-explaining context

**Result:** You walk in, say "where are we?", and I know immediately without needing context

---

## File Discovery Lesson

When the user references a file by name, trust their knowledge of the project structure. Do not perform broad searches (Glob, grep across directories). Instead:
1. Check common configuration directories first: `.claude/`, `.config/`, `.vscode/`
2. Ask the user for the full path if uncertain
3. Use the exact path provided without second-guessing

This prevents wasted time and respects user expertise about their own project.

---

## Project Ownership Protocol

When updates are needed to important files (PROGRESS.md, DAILY_SCHEDULE.md, pipeline_design.md):
1. **ALWAYS ask permission first** - "Should I update PROGRESS.md with Session 4 notes?"
2. **Read exact current content** before making changes
3. **Confirm edit location** - Show user where changes will go
4. **Make the edit only after approval**
5. **Verify the change** was applied correctly

This respects user ownership and prevents accidental data loss.

---

## File Modification Protocol - CRITICAL

**NEVER modify project files without asking first**

When you need to update important files (PROGRESS.md, pipeline_design.md, etc.):

1. **ALWAYS ask permission first** - "Should I update PROGRESS.md with Session 4 notes?"
2. **Read the exact current content** - Verify exact text before making edits
3. **Confirm edit location** - Show user where you're making changes
4. **Make the edit** - Only after user approval
5. **Verify success** - Confirm the change was applied correctly

**Why this matters:**
- User owns their project - respect that ownership
- Assumptions about file content cause failed edits
- Manual intervention needed when edits fail = time wasted
- Asking first builds trust and prevents errors

**What this prevents:**
- Failed edits due to incorrect assumptions
- Overwriting user's important changes
- Loss of work or data
- Breaking the relationship through presumption

**Key rule:** When in doubt, ask first. Respect user ownership of all project files.
