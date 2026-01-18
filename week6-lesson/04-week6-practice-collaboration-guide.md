# Team Collaboration Guide

## Purpose

This guide helps teams work together effectively using Git and GitHub. Use this as a reference for establishing team norms and workflows.

---

## Quick Reference

**Daily Workflow:**
1. `git pull` - Start of day
2. `git checkout -b feature/task` - New task
3. Work and commit
4. `git push` - End of day or when ready
5. Create PR, get review, merge

---

## Team Roles and Responsibilities

### Project Lead
- Reviews and approves PRs
- Maintains repository structure
- Resolves conflicts
- Sets workflow guidelines

### Contributors
- Create feature branches
- Make commits
- Open pull requests
- Respond to review feedback
- Keep branches up to date

### Reviewers
- Review PRs within 24 hours
- Provide constructive feedback
- Approve when satisfied
- Request changes when needed

---

## Communication Guidelines

### In Pull Requests

**Use @mentions for:**
- Requesting specific reviewer
- Asking questions
- Following up on feedback

**Example:**
> @sarah Can you review the research methodology section?

### In Commits

**Write clear messages:**
```
Good:
- "Added user personas from Q1 research"
- "Fixed broken link in navigation docs"
- "Updated decision log with scope change"

Bad:
- "updates"
- "changes"
- "fixed stuff"
```

### In Comments

**Be specific:**
```
Good:
- "Line 45: This stat needs a source citation"
- "Consider adding example for this use case"
- "Great point - this aligns with user feedback"

Bad:
- "This doesn't work"
- "Change this"
- "???"
```

---

## Workflow Patterns

### Solo Work

**When you're the only one on a task:**
1. Create branch from main
2. Work independently
3. Self-review before PR
4. Request external review
5. Merge when approved

### Pair Work

**When collaborating with teammate:**
1. Discuss approach first
2. Decide who creates branch
3. Both can commit to same branch
4. Review together before PR
5. One person merges

### Parallel Work

**When working on different features:**
1. Each person creates own branch
2. Work independently
3. Coordinate if touching same files
4. Merge separately
5. Pull after each merge

---

## Conflict Prevention

### Before Starting Work

**Always:**
```bash
git checkout main
git pull
git checkout -b feature/new-task
```

Starts from latest, avoids conflicts.

### During Work

**Regularly:**
```bash
# Pull main into your branch
git checkout feature/your-branch
git pull origin main
```

Keeps branch current, reduces conflicts later.

### Before Submitting PR

**Final check:**
```bash
git pull origin main
# Resolve any conflicts now
git push
```

Clean PR, easier review.

---

## Review Etiquette

### Requesting Reviews

**Good request:**
> "Ready for review! I updated the persona templates based on our discussion. Focus areas: consistency with brand voice, accessibility considerations."

**Bad request:**
> "Please review"

### Giving Feedback

**Constructive:**
> "This section is really clear. One suggestion: could we add an example for the edge case we discussed?"

**Not helpful:**
> "This is confusing"

### Receiving Feedback

**Good response:**
> "Good catch on the typo - fixed in latest commit. Re: the structure suggestion, I tried it and it flows better. Thanks!"

**Bad response:**
> "Done" (for every comment with no explanation)

---

## Handling Disagreements

### When You Disagree with Feedback

**Steps:**
1. Understand their perspective
2. Explain your reasoning
3. Discuss trade-offs
4. Find compromise or escalate
5. Document decision

**Example:**
> "I see your point about moving this section. I originally placed it here because [reason]. What if we [alternative]? Or happy to defer to your judgment on this."

### When Stuck

**Escalation path:**
1. Discuss in PR comments
2. Move to video/voice call
3. Bring in additional perspective
4. Project lead makes final call
5. Document decision in decision-log

---

## Timing and Expectations

### Response Times

**Pull requests:** Review within 24 hours

**Comments:** Respond within 48 hours

**Urgent items:** Flag with "urgent" label

**Blockers:** Notify team immediately

### Work Hours

**Respect boundaries:**
- No expectation of immediate response
- After-hours PRs can wait
- Emergencies are rare
- Async collaboration is okay

---

## Branch Management

### Naming Conventions

**Pattern:** `type/brief-description`

**Types:**
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation
- `update/` - Content updates
- `refactor/` - Restructuring

**Examples:**
- `feature/add-personas`
- `fix/broken-links`
- `docs/update-readme`
- `update/q2-research`

### Lifecycle

**Creation:** Branch from latest main

**Duration:** Days to weeks, not months

**Completion:** Merge and delete

**Abandoned:** Close PR and delete branch

---

## Pull Request Guidelines

### Size

**Small PR (ideal):**
- 1-5 files
- Under 200 lines
- Single purpose
- 15-minute review

**Large PR (avoid):**
- 10+ files
- 500+ lines
- Multiple purposes
- Hour+ review

**Split large PRs into smaller ones.**

### Description Template

```markdown
## Summary
[One sentence: what changed]

## Context
[Why this change was needed]

## Changes
- Change 1
- Change 2

## Testing
- [x] Reviewed locally
- [x] Links work
- [x] No typos

## Questions
[Anything you're unsure about]
```

### Before Creating PR

**Checklist:**
- [ ] Code/content works
- [ ] No sensitive data
- [ ] Description complete
- [ ] Reviewers identified
- [ ] Links updated
- [ ] Self-reviewed

---

## Merge Strategy

### Who Merges

**Author merges after approval** (recommended)

Or

**Reviewer merges after approval** (some teams prefer this)

Choose one and be consistent.

### When to Merge

**After:**
- All reviewers approved
- All comments addressed
- Checks pass (if any)
- No conflicts
- Author confirms ready

**Not before all of these.**

### After Merge

**Immediately:**
```bash
git checkout main
git pull
git branch -d feature/merged-branch
```

Clean up and stay current.

---

## Common Scenarios

### Scenario 1: Emergency Fix Needed

**When production issue requires immediate fix:**
1. Create `hotfix/description` branch
2. Make minimal fix
3. Quick review
4. Merge immediately
5. Update decision log

### Scenario 2: Long-Running Feature

**When feature takes weeks:**
1. Create feature branch
2. Regularly merge main into it
3. Break into smaller PRs if possible
4. Keep team updated on progress
5. Final integration PR when complete

### Scenario 3: Multiple People, Same File

**When two people need to edit same file:**
1. Communicate in advance
2. Work in separate sections if possible
3. Coordinate merge timing
4. First person merges
5. Second person pulls and resolves conflicts

### Scenario 4: Wrong Branch

**When you committed to wrong branch:**
```bash
# Create correct branch from current state
git checkout -b correct-branch

# Reset original branch
git checkout wrong-branch
git reset --hard origin/wrong-branch
```

Work is now on correct branch.

---

## Tools and Automation

### GitHub Features to Use

**Pull Request Templates:**
- Create `.github/pull_request_template.md`
- Auto-fills description
- Ensures consistency

**Branch Protection:**
- Require reviews before merge
- Prevent direct pushes to main
- Require status checks

**Labels:**
- `urgent`
- `needs-review`
- `in-progress`
- `blocked`

### VS Code Integration

**Use source control panel:**
- Visual diff
- Stage changes easily
- Create commits
- Manage branches

---

## Onboarding New Team Members

### New Member Checklist

- [ ] GitHub account created
- [ ] Added as collaborator
- [ ] Cloned repository
- [ ] Read CONTRIBUTING.md
- [ ] Completed practice PR
- [ ] Paired with experienced member
- [ ] Added to team channel

### First Week

**Day 1:** Read documentation, clone repo
**Day 2:** Make small documentation update
**Day 3:** Create first real PR
**Day 4:** Review someone's PR
**Day 5:** Work on assigned task

**Goal:** Comfortable with workflow by end of week.

---

## Troubleshooting Together

### When Someone is Stuck

**Help them by:**
1. Screen share to see actual problem
2. Walk through recent commands
3. Check repository state together
4. Guide to solution
5. Document for future reference

**Don't:**
- Take over their computer
- Just give commands without explaining
- Get frustrated
- Leave them more confused

### Common Issues and Solutions

**"I can't push"**
- Check they're on correct branch
- Verify remote is set
- Check authentication
- Try pulling first

**"I have conflicts"**
- Show them how to resolve
- Explain what conflicts mean
- Work through together
- Make it learning opportunity

**"I merged by accident"**
- Can be undone if caught quickly
- Revert or reset
- Create fix PR
- Document in decision log

---

## Metrics and Health

### Signs of Healthy Workflow

- PRs reviewed within 24 hours
- Most PRs small and focused
- Constructive review comments
- Few merge conflicts
- Regular commits
- Updated documentation
- Team confident with Git

### Red Flags

- PRs sitting for days
- Large, sprawling PRs
- Harsh review comments
- Constant conflicts
- Infrequent commits
- Stale documentation
- Team avoiding Git

**Address red flags in retro.**

---

## Continuous Improvement

### Regular Retros

**Discuss:**
- What's working with Git workflow?
- What's frustrating?
- Where do people get stuck?
- How can we improve?

**Update guidelines based on feedback.**

### Documentation Maintenance

**Keep current:**
- Update this guide as workflow evolves
- Add solutions to common problems
- Remove outdated advice
- Incorporate lessons learned

---

## Advanced Topics (Optional)

### GitHub Actions

Automate tasks:
- Run tests on PR
- Deploy documentation
- Lint markdown
- Check for sensitive data

### Branch Protection Rules

Require:
- Reviews before merge
- Status checks passing
- Up-to-date with main

### Code Owners

Specify who reviews what:
- Design docs → UX lead
- Technical specs → Dev lead
- Research → Research lead

---

## Getting Started

### Week 1 as Team

**Everyone:**
1. Clone repository
2. Read this guide
3. Create practice branch
4. Make small change
5. Open PR
6. Review someone else's PR
7. Merge yours

**Team meeting:**
- Discuss questions
- Clarify workflow
- Establish norms
- Set expectations

---

## Resources

**Learning:**
- These week 1-6 materials
- GitHub documentation
- Team wiki (if you have one)

**Support:**
- Team channel
- Pair programming
- Office hours
- External Git courses

**Tools:**
- VS Code Git integration
- GitHub Desktop (if preferred)
- GitKraken (visual Git client)

---

## Summary

**Core principles:**
1. Communicate clearly
2. Review constructively
3. Merge frequently
4. Document decisions
5. Help each other

**These make collaboration smooth.**

**The workflow matters less than the team.**

Good tools + good communication = great outcomes.

---

## Questions?

Add your team-specific FAQs here as they come up.

**Q: [Common question]**
A: [Team's answer]
