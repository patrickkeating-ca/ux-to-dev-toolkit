# Pull Request Template

## Purpose

This template helps you write clear, helpful pull request descriptions. Copy this template when creating PRs to ensure you include all necessary information.

---

## PR Description Template

Copy and fill out when creating a pull request:

```markdown
## Summary
[One sentence describing what this PR does]

## What Changed
[Bullet list of changes made]
- 
- 
- 

## Why
[Explain the reason for these changes]

## Type of Change
- [ ] New feature
- [ ] Bug fix
- [ ] Documentation update
- [ ] Refactoring/cleanup
- [ ] Design update
- [ ] Other: [specify]

## Testing Done
[How you verified these changes work]
- [ ] Tested locally
- [ ] Reviewed all files
- [ ] Checked links work
- [ ] Previewed markdown
- [ ] Other: [specify]

## Screenshots
[If applicable - especially for visual/UX changes]
[Attach images or link to Figma]

## Questions/Concerns
[Anything you're unsure about or want specific feedback on]

## Checklist
- [ ] Files are properly named
- [ ] No sensitive data included
- [ ] Documentation is updated
- [ ] Ready for review
```

---

## Good PR Description Examples

### Example 1: Feature Addition

```markdown
## Summary
Added user persona templates to help team create consistent personas.

## What Changed
- Created `personas.md` with template structure
- Added 3 example personas
- Updated README to link to persona guide

## Why
Team members were creating personas in different formats, making them hard to compare and use. This template ensures consistency.

## Type of Change
- [x] New feature
- [ ] Bug fix
- [ ] Documentation update

## Testing Done
- [x] Tested template with real user data
- [x] Reviewed with 2 team members
- [x] Verified markdown renders correctly

## Screenshots
[Link to Figma mockup of how personas should look]

## Questions/Concerns
Should we include demographic data in the template, or keep it flexible?

## Checklist
- [x] Files are properly named
- [x] No sensitive data included
- [x] Documentation is updated
- [x] Ready for review
```

---

### Example 2: Bug Fix

```markdown
## Summary
Fixed broken links in research documentation.

## What Changed
- Updated 5 broken links to point to correct locations
- Fixed typo in header that broke navigation

## Why
Links were pointing to old file structure after reorganization. Users couldn't access referenced documents.

## Type of Change
- [ ] New feature
- [x] Bug fix
- [ ] Documentation update

## Testing Done
- [x] Clicked all updated links
- [x] Verified they open correct files
- [x] Checked on GitHub preview

## Checklist
- [x] Files are properly named
- [x] No sensitive data included
- [x] Documentation is updated
- [x] Ready for review
```

---

### Example 3: Documentation Update

```markdown
## Summary
Updated project README with current team structure and goals.

## What Changed
- Added Q1 2025 objectives
- Updated team member list
- Refreshed project status
- Added links to recent deliverables

## Why
README was 6 months out of date. New team members and stakeholders need current information.

## Type of Change
- [ ] New feature
- [ ] Bug fix
- [x] Documentation update

## Testing Done
- [x] Reviewed all new links
- [x] Confirmed team names are correct
- [x] Previewed markdown

## Checklist
- [x] Files are properly named
- [x] No sensitive data included
- [x] Documentation is updated
- [x] Ready for review
```

---

## What Makes a Good PR Description?

### Clear and Concise

**Good:**
> "Added user flow diagrams for checkout process showing 5 main steps and 2 error states."

**Bad:**
> "Updated files."

**Why:** Specific about what was added and how much.

---

### Provides Context

**Good:**
> "Redesigned navigation based on usability testing that showed 60% of users couldn't find account settings."

**Bad:**
> "Changed navigation."

**Why:** Explains the reasoning backed by data.

---

### Shows Testing

**Good:**
> "Tested with 3 team members, verified all links work, checked mobile view in browser."

**Bad:**
> "Looks good."

**Why:** Shows due diligence and what was verified.

---

## PR Description Best Practices

### Do:

- Write description before creating PR (helps clarify your work)
- Include context about why changes were needed
- List what you tested
- Add screenshots for visual changes
- Ask specific questions if unsure about something
- Link to related issues or documents
- Use checklists to show completeness

### Don't:

- Leave description empty
- Just say "updates" or "changes"
- Assume reviewers know the context
- Skip testing section
- Wait until asked to provide information
- Use jargon without explanation

---

## Tailoring for UX Work

### UX-Specific Additions

**For design changes:**
```markdown
## Design Rationale
[Explain design decisions and principles used]

## User Impact
[How this affects user experience]

## Accessibility Considerations
[Any a11y implications or improvements]

## Design System Alignment
[How this fits with existing patterns]
```

**For research documents:**
```markdown
## Research Methods
[Interviews, surveys, testing, etc.]

## Key Findings
[Main insights - 3-5 bullets max]

## Sample Size
[Number of participants/data points]

## Next Steps
[What should happen based on this research]
```

**For documentation:**
```markdown
## Audience
[Who is this documentation for?]

## Related Documents
[Links to connected materials]

## Format Changes
[Any structural reorganization]
```

---

## PR Size Guidelines

### Small PR (Ideal)

- 1-3 files changed
- Under 200 lines
- Single purpose
- 10-15 minute review

**Example:** "Fixed typos in user research document"

---

### Medium PR

- 3-10 files changed
- 200-500 lines
- Related changes
- 30-45 minute review

**Example:** "Updated all persona documents with Q4 research insights"

---

### Large PR (Try to Avoid)

- 10+ files changed
- 500+ lines
- Multiple purposes
- Hours to review

**Better approach:** Break into smaller PRs

---

## Common PR Questions

### "How much detail should I include?"

**Enough that a reviewer can:**
- Understand what changed
- Know why it changed
- Verify it works
- Give informed feedback

**Not so much that:**
- Description is longer than the changes
- Reviewer gets lost in detail

**Balance:** Clear but concise

---

### "Should I include Figma links?"

**Yes, if:**
- PR involves design changes
- Visual context helps review
- Changes implement a design

**Include:**
- Link to Figma file or frame
- Screenshot of key screens
- Before/after comparisons

---

### "What if I'm not sure about something?"

**Absolutely mention it in the PR description!**

```markdown
## Questions/Concerns
- Not sure if this approach aligns with design system
- Would appreciate feedback on navigation structure
- Open to suggestions on content organization
```

**Reviewers can help answer questions.**

---

## Review Request Etiquette

### Requesting Reviews

**Do:**
- @ mention specific reviewers if needed
- Explain why you're requesting their review
- Give reasonable time for review (24-48 hours)
- Follow up politely if no response

**Example:**
> "@sarah Could you review the research methodology section? Your expertise would be valuable here."

**Don't:**
- Demand immediate review
- Tag everyone on the team
- Spam with notifications
- Get frustrated with delays

---

### Responding to Reviews

**When someone reviews:**

```markdown
Thanks for the feedback @reviewer!

- Fixed the typo in line 45
- Updated the navigation structure per your suggestion
- Re: the color scheme question - I'll follow up in our next sync

Let me know if the updates address your concerns.
```

**Shows:**
- You read the feedback
- You took action
- You're collaborative

---

## GitHub PR Features

### Tabs You'll Use

**Conversation:**
- Main discussion
- Comments and feedback
- Approval/rejection
- Merge button

**Commits:**
- All commits in this PR
- Chronological history
- Click to see specific changes

**Files Changed:**
- Diff view of all changes
- Line-by-line comparison
- Add comments on specific lines
- Most important for review

---

### Commenting on PRs

**Types of comments:**

**General comment:**
- Overall feedback
- Broad suggestions
- Appears in Conversation tab

**Inline comment:**
- Specific to a line of code
- Click + next to line number
- Appears in Files Changed tab

**Review comment:**
- Bundled feedback
- Approve/Request Changes/Comment
- Green "Review changes" button

---

## PR Lifecycle States

### Draft PR

**What:** Work in progress, not ready for review
**Use:** Share progress, get early feedback
**Status:** Can't be merged yet

---

### Open PR

**What:** Ready for review
**Use:** Requesting team feedback
**Status:** Can be reviewed and merged

---

### Approved PR

**What:** Reviewed and accepted
**Use:** Ready to merge
**Status:** Waiting for author to merge

---

### Merged PR

**What:** Changes integrated into main
**Use:** Complete, branch can be deleted
**Status:** Closed, archived

---

### Closed PR

**What:** Not merged, rejected or abandoned
**Use:** Work not proceeding
**Status:** Archived, can be reopened

---

## Template Variations

### Quick Fix Template

For small, obvious fixes:

```markdown
## What
Fixed broken link in README

## Why
Link was pointing to old URL after domain change

## Testing
Clicked link, verified it works

Ready to merge.
```

---

### Major Feature Template

For significant additions:

```markdown
## Summary
[Detailed explanation]

## Background
[Context and history]

## Changes
[Comprehensive list]

## Design Decisions
[Why chose this approach]

## User Impact
[How this affects users]

## Testing
[Extensive testing details]

## Migration Notes
[If applicable]

## Documentation
[What docs were updated]

## Questions
[Specific feedback needed]

## Next Steps
[Follow-up work planned]
```

---

## Completion Checklist

Practice creating PRs with:

- [ ] Clear summary
- [ ] Detailed what changed section
- [ ] Explanation of why
- [ ] Testing checklist
- [ ] Screenshots (if applicable)
- [ ] Questions noted
- [ ] Proper type selected
- [ ] All checklists completed

---

## Resources

**Good PR examples to study:**
- Look at PRs in popular open-source projects
- Note how they structure descriptions
- See how reviewers interact
- Learn from real examples

**GitHub documentation:**
- [About Pull Requests](https://docs.github.com/en/pull-requests)
- [Reviewing Changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests)

---

## Final Tips

**Before clicking "Create pull request":**
1. Read your description as if you're the reviewer
2. Is everything clear?
3. Did you answer the obvious questions?
4. Would you feel confident reviewing this?

**If yes to all: Create the PR!**

**If no: Add more detail**

**Good PR descriptions:**
- Get faster reviews
- Get better feedback
- Show professionalism
- Help your future self understand what happened

**Invest 2 minutes in a good description. It pays off.**
