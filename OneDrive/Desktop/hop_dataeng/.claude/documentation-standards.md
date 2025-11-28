# Documentation Standards

## Documentation Standards

**When creating documents:**
- Clean, professional structure (no emojis, no AI indicators)
- Clear sections with proper hierarchy
- Concise content (no filler)
- Enterprise-ready appearance
- No icons, symbols, or indicators that scream "AI-generated"
- Business-appropriate language and formatting

## File Naming Conventions - STANDARDIZED

Ensure consistency and prevent variation by following these file naming standards.

### Root-Level Critical Files (ALL CAPS)

Use ALL CAPS for files at the project root that are critical to the project:

**Examples:**
- `README.md` - Project overview and setup
- `PROGRESS.md` - Learning journey, decisions, and metrics
- `CONTRIBUTING.md` - Contribution guidelines
- `LICENSE` - Legal information
- `CODE_OF_CONDUCT.md` - Community standards
- `SECURITY.md` - Security policy
- `ENTERPRISE_WORKFLOWS_AND_SOPS.md` - Enterprise standards and procedures
- `CHANGELOG.md` - Version history and changes
- `DAILY_SCHEDULE.md` - Time tracking and milestones
- `YOUR_8_WEEK_HIRING_SCHEDULE.md` - Long-term timeline and goals

### Internal Documentation Files (lowercase-with-hyphens)

Use lowercase with hyphens for internal documentation in subdirectories:

**Examples:**
- `.claude/mentoring-approach.md`
- `.claude/git-workflow-guide.md`
- `.claude/code-quality-standards.md`
- `.claude/documentation-standards.md`
- `.claude/task-execution.md`
- `.claude/session-protocols.md`
- `.claude/USING_DOCUMENTATION.md` (exception: system protocol guide)

### Rationale

**Why this distinction?**
- **Root files in ALL CAPS** create visual prominence for critical project information
- **Internal docs in lowercase-hyphens** follow GitHub convention for non-root documentation
- **Visual hierarchy** prevents confusion about file importance
- **Consistency** eliminates variation and makes the system predictable

**When creating new documentation:**
1. Is it at the project root? → Use ALL CAPS
2. Is it in a subdirectory like `.claude/`? → Use lowercase-with-hyphens
3. Exception: System protocol guides use ALL CAPS even in subdirectories

---

## Documentation as Living System - AUTOMATIC & CONTINUOUS

**Documentation updates are as important as code changes.**

After every session:
- Update PROGRESS.md with session details (mandatory)
- Update DAILY_SCHEDULE.md with actual vs. planned time
- Update YOUR_8_WEEK_HIRING_SCHEDULE.md if milestones shift
- Verify all documents remain consistent with each other

**Why this matters:**
- Users depend on these documents being accurate
- Stale documentation causes confusion and rework
- These are reference documents - they must be reliable
- This is enterprise standard practice

---

## Session Progress Saving - AUTOMATIC & DETAILED
**After each session: Update PROGRESS.md with the following structure:**

### Required Sections for Every Session:
1. **Session Header** - `## Session X (Date) - Brief Title`
2. **What Was Done** - Specific deliverables with ✅ checkmarks
3. **Blockers Encountered & Solutions** - CRITICAL: Include actual error messages, root causes, and code fixes
4. **Key Learning Points** - Concepts, patterns, insights
5. **Data Quality/Metrics** - If applicable, include measurements (rows, nulls, errors filtered, etc.)
6. **Design Decisions Made** - Decision → Reasoning → Impact format
7. **Code Locations** - File paths and cell IDs for easy navigation
8. **Open Decisions** - What still needs to be decided before next steps

### Error Documentation (Must Include):
For EVERY blocker encountered:
- **Error Message:** Exact error text (in code block if long)
- **Root Cause:** Why it happened (not just what happened)
- **Detection Method:** How you found/diagnosed the issue
- **Solution:** Exact code that fixed it
- **Why It Matters:** Production implications
- **Lesson Learned:** What to remember for next time

**Frequency:** At end of each session (not during - don't interrupt flow)

**Format:**
- Use markdown tables for metrics
- Use code blocks for error messages and solutions
- Use checklist format for next session startup
- Keep professional, no emojis, no AI indicators
- Include percentages and counts for data quality

**Purpose:**
- Error history becomes a troubleshooting reference library
- Metrics show progress quantitatively
- Design decisions explain the "why" behind code
- Code locations enable fast navigation for debugging
- Next session checklist eliminates context ramp-up time

## Workflow Documentation Standards - ENTERPRISE GRADE

**When creating or updating any project documentation:**

### Structure & Organization
- Use clear hierarchical headings (H1 → H2 → H3)
- Create table of contents for documents >500 lines
- Use consistent formatting throughout
- Separate sections with horizontal rules (`---`)

### Content Standards - NO ICONS POLICY
- **No emojis, no checkmarks, no symbols** - Keep professional appearance
- **No AI indicators** - No "generated with...", no casual language
- **Status formatting** - Use enterprise style: `Task Name: Complete` or `Phase X - Complete`
- **No casual language** - Use business-appropriate tone
- **Code blocks for all code** - Use triple backticks with language specification
- **Clear descriptions** - Explain the "why" not just the "what"
- **Practical examples** - Show exactly what code should look like
- **Checkbox lists** - Use `[ ]` for actionable items (markdown checkboxes)
- **Tables for comparisons** - Use when comparing options or patterns

### Status Indicators - STANDARDIZED FORMAT
Use this format EVERYWHERE for consistency:
- **Tasks completed:** `Task Name: Complete`
- **Phases:** `Phase X - Complete`
- **Sections:** `Heading - Complete` or `Heading - In Progress` or `Heading - Pending`
- **In lists:** `- Item name: Complete` or `- Item name: In Progress`

Examples:
```markdown
### Phase 1: Planning - Complete
### What Was Done
1. Fixed silver layer NameError: Complete
2. Verified data validations: Complete

Status: Complete
Status: Pending
Status: In Progress
```

**Never use:**
- Checkmarks (✅, ☑️)
- Stars (⭐, ★)
- Arrows (→, ←, ⇒)
- Badges or special characters
- "Done", "Todo", "WIP", "PENDING", "IN PROGRESS", "COMPLETE" (wrong case)

### Status Keywords - EXACT CAPITALIZATION
Use ONLY these three status words, with exact capitalization:
- `Complete` (not: Done, COMPLETE, completed, Completed)
- `Pending` (not: TODO, PENDING, Pending, pending)
- `In Progress` (not: IN PROGRESS, in progress, WIP, active)

Examples of CORRECT usage:
```markdown
Status: Complete
Status: Pending
Status: In Progress

- [ ] Task one: Complete
- [ ] Task two: Pending
- [ ] Task three: In Progress

### Phase 1: Setup - Complete
### Phase 2: Development - In Progress
### Phase 3: Testing - Pending

| Component | Status |
|-----------|--------|
| Bronze Layer | Complete |
| Silver Layer | Complete |
| Gold Layer | Pending |
```

Examples of INCORRECT usage (DO NOT USE):
```markdown
Status: COMPLETE (wrong case)
Status: Done (wrong word)
Status: IN PROGRESS (wrong case)
Status: PENDING (wrong case)
Status: WIP (acronym not allowed)
Status: Completed (verb form, not accepted)
```

### Standardization Enforcement - APPLIES TO ALL DOCUMENTS
This standard applies across ALL project documents without exception:
- PROGRESS.md
- DAILY_SCHEDULE.md
- PIPELINE_WORKFLOW_OUTLINE.md
- YOUR_8_WEEK_HIRING_SCHEDULE.md
- ENTERPRISE_WORKFLOWS_AND_SOPS.md
- Any new documents created

**Why this matters:**
- Consistency = professionalism
- Mixed standards = confusion and errors
- Enterprise teams enforce standards ruthlessly
- This is how real companies work

**Before submitting any document for review:**
1. Search for: "PENDING", "COMPLETE", "IN PROGRESS" (wrong case)
2. Search for: "Done", "Todo", "WIP", "ACTIVE" (wrong words)
3. Search for: ✅ ☑️ ⭐ → ← ⇒ (icons)
4. Replace ALL with correct: `Complete`, `Pending`, `In Progress` (exact case)

### Formatting Rules
- **Bold for emphasis** - Use `**text**` for important concepts
- **Code for variables/functions** - Use backticks for `variable_name`
- **Numbered lists** - For sequential steps that must follow order
- **Bullet lists** - For non-sequential items or options
- **Indentation** - Shows hierarchy and relationships
- **Line breaks** - Separate concepts with blank lines for readability

### Length & Density
- Keep sections under 50 lines each (except code examples)
- Use subsections to break up long content
- One concept per paragraph
- Maximum 3 bullet points per list item

### Enterprise Requirements
- Remove "fun" elements (avoid colorful language)
- No repetitive explanations (reference earlier sections)
- Include "why this matters" context
- Link concepts to production implications
- Follow company/industry standards
- Make it a reference document (scannable, not a story)

### Example Professional Format
```markdown
## Section Title

### Subsection Title
Introductory sentence explaining the concept.

**Key consideration:** [Important aspect]

**Typical workflow:**
1. Step one
2. Step two
3. Step three

**Code example:**
\`\`\`python
# Implementation
\`\`\`

**Best practices:**
- Practice 1
- Practice 2

**See also:** [Link to related section]
```
