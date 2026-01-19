# Curriculum Update Recommendations

Based on pedagogical review. Target audience: UX professionals with zero technical experience who actively avoid these tools.

---

## High Priority

### 1. Refocus Week 6: LLM-Assisted Documentation

**Current state:** Heavy documentation templates (PLATFORM.md, PRD structure, etc.) that are developer-centric.

**Recommendation:** Reframe as "Using AI to Create and Manage Documentation"

**New Week 6 content:**
- Why Git + AI is powerful (version control for generated content)
- Prompting for documentation drafts:
  - README sections
  - Research summaries
  - Decision logs
  - Handoff documentation
- The workflow: prompt → review → edit in VS Code → commit → iterate
- Prompt templates for common UX documentation needs
- When to regenerate vs. manually edit
- Tracking AI iterations with commits ("Draft 1 from Claude" → "Revised with stakeholder feedback")

**Rationale:** This is the payoff. "Learn Git so you can professionally manage AI-generated docs" is compelling. Current Week 6 asks them to manually create templates they may never use.

---

### 2. Trim Week 2 (VS Code)

**Current state:** 15+ shortcuts, 4 extensions, settings customization. 1-1.5 hours standard, plus 2-3 hours optional.

**Recommendation:** Cut to essentials only.

**Keep:**
- Open folder (not file)
- Command+P (quick open)
- Command+S (save)
- Split view for markdown preview
- Integrated terminal (brief)

**Move to reference/optional:**
- Most keyboard shortcuts
- Extensions beyond Markdown Preview
- Settings customization
- Multi-cursor, regex search, etc.

**Rationale:** VS Code is a vehicle, not the destination. For an audience avoiding technical tools, extensive editor training adds friction without proportional value. They can learn shortcuts as needed.

---

### 3. Add GitHub Issues Coverage

**Current state:** Not covered.

**Recommendation:** Add to Week 4 or Week 5.

**Content needed:**
- Creating issues (bug reports, feature requests)
- Issue templates for UX feedback
- Linking issues to PRs
- Using issues for design review requests
- Basic issue triage/labels

**Rationale:** Many UX professionals interact with GitHub primarily through Issues, not PRs. This is how design feedback flows in cross-functional teams.

---

### 4. Simplify Week 6 Project Structure

**Current state:** Extensive folder hierarchy and multiple documentation templates.

**Recommendation:** Reduce to essentials, make templates optional references.

**Keep:**
- README.md (simplified)
- Basic folder structure (docs/, assets/)
- Decision log concept
- .gitignore

**Make optional/reference:**
- PLATFORM.md (developer concern)
- Detailed PRD structure
- CONTRIBUTING.md (team lead concern)
- Complex folder hierarchies

**Frame as:** "Set up YOUR project" not "create all these templates."

**Rationale:** Current Week 6 feels like homework. Reframe as applying skills to their actual work.

---

## Medium Priority

### 5. Rename "Explore Deeper" to "Reference Guide"

**Current state:** "Explore Deeper" implies expected curriculum.

**Recommendation:** Rename to "Reference" or "Troubleshooting Guide"

**Rationale:** For anxious learners, optional content that seems expected creates stress. "Reference" clearly signals "use when needed, not required."

---

### 6. Add "Your First Day" Consolidated Workflow

**Location:** End of Week 4 or beginning of Week 5

**Content:**
- The daily loop: pull → edit → commit → push
- When to branch vs. commit to main
- What to do when you're stuck (reset, ask for help)
- Common "oh no" moments and solutions

**Rationale:** The full workflow is scattered across weeks. One consolidated "here's what you'll actually do daily" reference is valuable.

---

### 7. Add Failure Recovery Section

**Location:** Week 3 or Week 4

**Content:**
- `git status` as your friend (always check first)
- Undoing uncommitted changes
- Undoing a commit (soft reset)
- "I broke something" decision tree
- When to ask a developer for help

**Rationale:** Fear of breaking things is a major barrier for this audience. Explicit "how to recover" reduces anxiety.

---

### 8. Clarify Design Asset Strategy

**Location:** Week 4 or Week 6

**Content:**
- What goes IN the repo: markdown, small images, text files
- What gets LINKED: Figma files, large assets, video
- How to reference external design files in documentation
- Image sizing/optimization basics

**Rationale:** Real daily question for UX. "Do I put my Figma file in Git?" needs a clear answer.

---

## Lower Priority / Consider

### 9. Consolidate File Count

**Current state:** 42 files across 6 weeks (6-7 per week)

**Options:**
- Embed practice exercises in main instruction files
- Combine prerequisites + instructions
- Reduce to 3-4 files per week: express, main lesson, practice, solution

**Rationale:** File count can intimidate. Fewer files = less overwhelming. Trade-off: current structure is very navigable.

---

### 10. Add Week 3 Intermediate Practice

**Current state:** Instructions → "do 10 steps independently" is a steep jump.

**Recommendation:** Add guided practice between instruction and independent exercise.

**Example:**
- Guided: "Let's make a commit together" with explicit steps
- Semi-guided: "Make two more commits, here are hints"
- Independent: "Complete 10 steps on your own"

**Rationale:** Week 3 is correctly identified as hardest. More scaffolding in the practice helps.

---

## Content to Remove

### 11. Cut Developer-Centric Content

**Remove or make clearly optional:**
- PLATFORM.md template (tech stack, dependencies, env variables)
- Detailed PRD sections that are PM/dev responsibilities
- Advanced Git concepts unlikely to be used (rebase, cherry-pick, etc.)
- VS Code power-user features (regex search, multi-cursor, etc.)

**Rationale:** Every piece of content that feels "not my job" reinforces avoidance. Keep it ruthlessly UX-focused.

---

## Suggested Updated Week Structure

| Week | Current Focus | Recommended Adjustment |
|------|---------------|----------------------|
| 1 | Terminal & Markdown | Keep as-is (works well) |
| 2 | VS Code Setup | Trim significantly (essentials only) |
| 3 | Git Basics | Add intermediate practice step |
| 4 | GitHub & Remote | Add Issues coverage, design asset guidance |
| 5 | Collaboration | Keep mostly as-is, add "daily workflow" summary |
| 6 | Real Project | Refocus on LLM-assisted documentation |

---

## New Week 6 Outline (Draft)

### Week 6: AI-Assisted Documentation Workflow

**Learning Objectives:**
- Use AI to draft professional documentation
- Apply Git workflow to manage AI-generated content
- Build prompt templates for common UX documentation needs

**Content:**

1. Why Git + AI work together
   - Version control for generated content
   - Tracking iterations professionally
   - The review/edit/commit cycle

2. Prompting for documentation
   - README sections
   - Research summaries
   - Decision logs
   - Handoff notes

3. The workflow in practice
   - Generate draft with AI
   - Review and edit in VS Code
   - Commit with meaningful message
   - Iterate (regenerate sections vs. manual edit)

4. Prompt templates
   - Project README generator
   - Research findings summarizer
   - Decision log entry creator
   - Meeting notes to documentation converter

5. Managing AI output professionally
   - Commit messages that track AI involvement
   - When to attribute AI assistance
   - Quality control and fact-checking
   - Maintaining your voice in generated content

6. Practice: Create a complete project README using AI + Git workflow

**Outcome:** Students can use AI to accelerate documentation work while maintaining professional version control and quality standards.

---

## Summary

**Must do:**
1. Refocus Week 6 on LLM-assisted documentation (the payoff)
2. Trim Week 2 to essentials
3. Add GitHub Issues
4. Simplify Week 6 project structure

**Should do:**
5. Rename "Explore Deeper" to "Reference"
6. Add consolidated daily workflow
7. Add failure recovery guidance
8. Clarify design asset strategy

**Consider:**
9. Consolidate file count
10. Add Week 3 intermediate practice
11. Remove developer-centric content

---

*Review these recommendations and let me know which to implement.*
