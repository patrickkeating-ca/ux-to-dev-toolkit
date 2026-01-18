# Merge Conflict Practice

## What This File Is For

This file is specifically designed to help you practice resolving merge conflicts in a safe environment. Don't worry - conflicts are normal and easy to fix once you understand them.

---

## Understanding Merge Conflicts

**A conflict happens when:**
1. You change a file locally
2. Someone else changes the same lines in the same file on GitHub
3. Git doesn't know which version to keep
4. You have to decide

**Think of it like two people editing a Google Doc:**
- If you both edit different paragraphs: No problem, automatically merges
- If you both edit the same sentence: Conflict - someone needs to decide the final version

---

## What Conflicts Look Like

**When you pull and get a conflict, Git adds markers to show both versions:**

```
<<<<<<< HEAD
Your local version of the text
=======
The version from GitHub
>>>>>>> branch-name
```

**Translation:**
- `<<<<<<< HEAD` = Start of your local changes
- `=======` = Divider between versions
- `>>>>>>> branch-name` = End of GitHub's changes

**Your job:**
1. Read both versions
2. Decide what to keep
3. Remove the conflict markers
4. Keep only the final version you want

---

## Practice Section - Simple Conflict

### Team Member Bio

**Name:** Sarah Chen

**Role:** UX Researcher

**Favorite Tool:** [This will create a conflict]

**Years of Experience:** 5 years

**Current Project:** Mobile app redesign

---

## Practice Section - List Conflict

### Project Priorities

1. User research completion
2. Wireframe creation
3. [This will create a conflict]
4. Developer handoff
5. Usability testing

---

## How to Create a Practice Conflict

**Follow these steps to safely practice:**

**Step 1: Edit locally (DON'T commit yet)**
- Change "Favorite Tool" to "Figma"
- Change priority #3 to "Prototype development"
- Save the file

**Step 2: Edit on GitHub**
- Go to this file on GitHub
- Click Edit (pencil icon)
- Change "Favorite Tool" to "Sketch"
- Change priority #3 to "Design system documentation"
- Commit: "Updated bio and priorities"

**Step 3: Commit your local changes**
```bash
git add 04-week4-practice-conflict.md
git commit -m "Updated bio and priorities locally"
```

**Step 4: Try to push**
```bash
git push
```

**You'll get rejected!** GitHub has commits you don't have.

**Step 5: Pull to get GitHub's changes**
```bash
git pull
```

**Now you have a conflict!**

---

## Resolving the Conflict

**Open this file in VS Code:**

**You'll see conflict markers like:**

```markdown
**Favorite Tool:** <<<<<<< HEAD
Figma
=======
Sketch
>>>>>>> abc123
```

**VS Code shows buttons:**
- Accept Current Change (Figma - your local)
- Accept Incoming Change (Sketch - from GitHub)
- Accept Both Changes (Figma and Sketch)
- Compare Changes

**For this practice:**
1. Click "Accept Current Change" for Favorite Tool (keep Figma)
2. Or manually edit to choose Sketch
3. Or manually edit to say "Figma and Sketch"
4. Whatever you choose, remove the conflict markers

**Same for the priorities conflict.**

**After resolving, the file should have NO:**
- `<<<<<<<` markers
- `=======` markers
- `>>>>>>>` markers

**Just clean text.**

---

## Mark as Resolved

**After editing:**

```bash
git add 04-week4-practice-conflict.md
git commit -m "Resolved merge conflict in practice file"
git push
```

**Conflict resolved!**

---

## Understanding What Happened

**The timeline:**
1. Both you and GitHub had same file version
2. You changed it locally → Version A
3. GitHub changed it (you edited there) → Version B
4. When you pulled, Git found both versions
5. Git asked you to pick
6. You picked and committed the resolution
7. Now everyone has the resolved version

**This is collaboration in action.**

---

## Tips for Real Conflicts

**Stay calm:**
- Conflicts are normal, not errors
- They mean people are actively working
- They're usually simple to resolve

**Read carefully:**
- Look at both versions
- Understand what each person intended
- Sometimes both changes should be kept
- Sometimes one is clearly better

**Communicate:**
- If unsure, ask the other person
- "Hey, I see we both edited X. Which version should we keep?"
- Better to ask than guess wrong

**Test after resolving:**
- Make sure the file still makes sense
- Check that you didn't accidentally break something
- Preview markdown to ensure it renders correctly

---

## Common Conflict Patterns

### Pattern 1: Same Change, Different Wording

**You wrote:** "Complete user testing by Friday"
**They wrote:** "Finish usability tests by end of week"

**Resolution:** Pick one or combine: "Complete user testing by Friday (end of week)"

---

### Pattern 2: One Adds, One Deletes

**You:** Added new section
**They:** Deleted old section

**Resolution:** Usually keep both changes (add new, remove old)

---

### Pattern 3: Formatting Changes

**You:** Made text bold
**They:** Made text italic

**Resolution:** Choose one style or combine (bold italic)

---

### Pattern 4: Conflicting Requirements

**You:** "Feature must launch next week"
**They:** "Feature postponed to next month"

**Resolution:** This needs discussion! Don't just pick one - talk to your team.

---

## Advanced Conflict Tools

**See just the conflicts:**
```bash
git diff --name-only --diff-filter=U
```

Lists files with unresolved conflicts.

**Abort the merge (start over):**
```bash
git merge --abort
```

Goes back to before you pulled. Use if things get too messy.

**Use a merge tool:**
```bash
git mergetool
```

Opens a visual diff tool (if configured).

---

## Practice Variations

**After doing the basic conflict, try these:**

**Variation 1: Multiple conflicts in one file**
- Create conflicts in several sections
- Resolve them all at once

**Variation 2: Choose different versions**
- For one conflict, keep yours
- For another conflict, keep theirs
- For another, combine both

**Variation 3: Complete rewrite**
- For a conflict, use neither version
- Write something completely new
- This is valid! You're not limited to the two options.

---

## Self-Check Questions

After resolving conflicts, can you answer:

1. What causes a merge conflict?
2. What do the conflict markers mean?
3. How do you know when a conflict is fully resolved?
4. Can you commit a file that still has conflict markers?
5. What should you do if you're unsure which version to keep?

**Answers:**
1. Same lines changed in two different commits
2. Show the two different versions that conflict
3. No conflict markers remain, file makes sense
4. Yes (but don't! It'll break things)
5. Talk to the other person / team

---

## When Conflicts Get Hairy

**Most conflicts are simple like this practice.**

**Occasionally, you'll get complex ones:**
- Many files affected
- Hundreds of lines changed
- Can't tell what happened

**When that happens:**
1. Don't panic
2. Take a deep breath
3. Review what you've learned
4. You can do this
5. Use VS Code's visual diff
6. Ask for help if truly stuck
7. Worst case: `git merge --abort` and start over

**Deep breath. Review what you've learned. You can do it.**

---

## Conflict Resolution Checklist

When you encounter a conflict:

- [ ] Read the error message
- [ ] Open the conflicted file
- [ ] Find the conflict markers
- [ ] Understand both versions
- [ ] Decide what to keep
- [ ] Edit to keep only final version
- [ ] Remove ALL conflict markers
- [ ] Save the file
- [ ] git add (mark as resolved)
- [ ] git commit (complete the resolution)
- [ ] git push (share the resolution)

---

## Completion Status

Mark when you've completed these:

- [ ] Created a practice conflict
- [ ] Saw conflict markers in the file
- [ ] Used VS Code buttons to resolve
- [ ] Manually edited to resolve another conflict
- [ ] Removed all conflict markers
- [ ] Committed the resolution
- [ ] Pushed successfully
- [ ] Understand the conflict workflow

---

## Reflection

**How did resolving the conflict feel?**
[Add your thoughts]

**What was harder than expected?**
[Add notes]

**What was easier than expected?**
[Add notes]

**Confidence level with conflicts (1-10):**
[Rate yourself]

---

## Remember

**Conflicts are not failures.**

They're Git saying: "Hey, there are two different ideas here. Which one do we want?"

You're the human who makes that decision. Git just highlights where the decision is needed.

**With practice, conflicts take 30 seconds to resolve.**

You've got this.
