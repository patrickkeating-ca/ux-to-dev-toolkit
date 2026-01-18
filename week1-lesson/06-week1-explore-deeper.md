# Week 1: Explore Deeper - Advanced Markdown & Terminal

**Optional material for those who want to go beyond the basics**

---

## When to Use This

Come back to this file when:
- You've completed the main Week 1 exercises
- You want to learn more markdown formatting options
- You're creating professional documentation
- You've encountered markdown you don't recognize
- You have extra time and curiosity

**This is NOT required for the course.** The basics are enough.

---

## Advanced Markdown Syntax

### Tables

Create formatted tables:

```markdown
| Feature | Status | Priority |
|---------|--------|----------|
| Search | Complete | High |
| Filters | In Progress | Medium |
| Export | Planned | Low |
```

**Renders as:**

| Feature | Status | Priority |
|---------|--------|----------|
| Search | Complete | High |
| Filters | In Progress | Medium |
| Export | Planned | Low |

---

### Task Lists

Interactive checkboxes (work on GitHub):

```markdown
- [x] Completed task
- [ ] Incomplete task
- [ ] Another task
```

**Renders as:**
- [x] Completed task
- [ ] Incomplete task
- [ ] Another task

---

### Blockquotes

Emphasize quotes or callouts:

```markdown
> "This is a user quote from our research."
>
> — Participant 7
```

**Renders as:**
> "This is a user quote from our research."
>
> — Participant 7

**Nested quotes:**
```markdown
> Main quote
>> Nested quote
>>> Double nested
```

---

### Code Blocks with Syntax Highlighting

For sharing code snippets:

````markdown
```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}
```
````

**Renders with syntax highlighting in most markdown viewers.**

**Common languages:**
- `javascript`, `python`, `html`, `css`, `bash`, `json`

---

### Inline Code

Highlight code within sentences:

```markdown
Use the `git status` command to check your repository.
```

**Renders as:** Use the `git status` command to check your repository.

---

### Horizontal Rules

Create visual separators:

```markdown
---
```

or

```markdown
***
```

or

```markdown
___
```

All create:

---

### Images

Embed images (similar to links, with `!` prefix):

```markdown
![Alt text](path/to/image.png)
```

**For URLs:**
```markdown
![Wireframe](https://example.com/wireframe.png)
```

**Tip:** Use relative paths for images in your repository:
```markdown
![Screenshot](./images/screenshot.png)
```

---

### Links with Titles

Add hover text to links:

```markdown
[Google](https://google.com "Search engine")
```

**Hover over the link to see the title.**

**Reference-style links:**
```markdown
Here's [a link][1] and [another link][2].

[1]: https://example.com "Example site"
[2]: https://github.com "GitHub"
```

Keeps content readable, links at bottom.

---

### Footnotes

Add references (GitHub-flavored markdown):

```markdown
This is a statement that needs citation[^1].

[^1]: Source: Research study, 2025
```

---

### Emoji (GitHub-flavored)

```markdown
:rocket: :sparkles: :fire: :bulb:
```

**Renders as:** 🚀 ✨ 🔥 💡

**Find emoji codes:** [Emoji Cheat Sheet](https://github.com/ikatyang/emoji-cheat-sheet)

---

### Strikethrough

```markdown
~~This text is crossed out~~
```

**Renders as:** ~~This text is crossed out~~

---

### Escaping Markdown Characters

Use backslash to show literal characters:

```markdown
\*Not italic\*
\# Not a heading
\[Not a link\]
```

**Renders as:** \*Not italic\* instead of *Not italic*

---

### HTML in Markdown

Most markdown parsers allow HTML:

```markdown
<details>
<summary>Click to expand</summary>

Hidden content here!

</details>
```

**Creates collapsible sections** (works on GitHub).

---

## Advanced Terminal Commands

### File Content Preview

**View file contents:**
```bash
cat filename.md
```

**View first 10 lines:**
```bash
head filename.md
```

**View last 10 lines:**
```bash
tail filename.md
```

**Custom line count:**
```bash
head -n 20 filename.md  # First 20 lines
tail -n 5 filename.md   # Last 5 lines
```

---

### File Searching

**Find files by name:**
```bash
find . -name "*.md"
```

Finds all markdown files in current directory and subdirectories.

**Search file contents:**
```bash
grep "search term" filename.md
```

**Search all files:**
```bash
grep -r "search term" .
```

---

### File Manipulation

**Copy files:**
```bash
cp source.md destination.md
```

**Move/rename files:**
```bash
mv oldname.md newname.md
```

**Delete files:**
```bash
rm filename.md
```

**⚠️ Warning:** `rm` is permanent - no trash/undo!

**Delete folder and contents:**
```bash
rm -r foldername
```

---

### Wildcards

**Select multiple files:**
```bash
ls *.md           # All markdown files
ls week*          # All files starting with "week"
ls *.{md,txt}     # All .md and .txt files
```

---

### Command History

**View recent commands:**
```bash
history
```

**Rerun last command:**
```bash
!!
```

**Search command history:**
Press `Ctrl + R`, then type search term

---

### Shortcuts

**Auto-complete:**
- Type partial filename
- Press `Tab`
- Terminal completes it

**Clear screen:**
```bash
clear
```
or press `Ctrl + L`

**Cancel command:**
Press `Ctrl + C`

**Go to start of line:**
Press `Ctrl + A`

**Go to end of line:**
Press `Ctrl + E`

---

## Markdown Best Practices

### Headings

**Use hierarchy properly:**
```markdown
# Document Title (only one H1 per document)
## Major Section (H2)
### Subsection (H3)
#### Detail (H4)
```

**Don't skip levels:** Go from H2 to H3, not H2 to H4.

---

### Lists

**Consistent markers:**
```markdown
- Use dashes
- Throughout the document
- For consistency
```

**Or:**
```markdown
* Use asterisks
* If you prefer
* But be consistent
```

**Nested lists:**
```markdown
- Main item
  - Sub item (2 spaces indent)
  - Another sub item
    - Deep sub item (4 spaces)
```

---

### Line Breaks

**Single line break:** Usually ignored

**Double line break:** Creates new paragraph

**Force line break:** End line with two spaces
Like this.

Or use `<br>` tag.

---

### Emphasis

**When to use:**
- **Bold** for strong emphasis, headings, labels
- *Italic* for subtle emphasis, terms, titles
- `Code` for commands, filenames, technical terms

**Avoid overuse:** Not every other word needs formatting.

---

## Markdown Flavors

Different platforms support different markdown features:

**GitHub Flavored Markdown (GFM):**
- Task lists
- Tables
- Emoji codes
- Strikethrough
- Automatic linking

**CommonMark:**
- Standard specification
- More portable
- Fewer features

**For UX work:** Assume GitHub flavor since you'll use GitHub.

---

## Troubleshooting

### Preview Looks Wrong

**Check:**
1. Proper markdown syntax (spaces, punctuation)
2. Blank lines between sections
3. File saved with .md extension
4. Correct number of # symbols
5. List items have space after marker: `- Item` not `-Item`

---

### Links Not Working

**Common issues:**
- Missing closing parenthesis: `[text](url)`
- Space in URL not encoded
- Relative path incorrect
- File doesn't exist at that path

**Test links:** Click them in preview or on GitHub

---

### Images Not Showing

**Check:**
1. Path is correct (case-sensitive!)
2. Image file exists
3. Image format supported (jpg, png, gif, svg)
4. For GitHub: image pushed to repository
5. Image not too large (>10MB may fail)

---

### Formatting Not Rendering

**Possible causes:**
- Missing blank lines around blocks
- Incorrect number of backticks for code blocks
- Spaces interfering with syntax
- Preview tool doesn't support that feature

**Solution:** View on GitHub to see how it really renders

---

## Useful Resources

**Markdown Guides:**
- [Markdown Guide](https://www.markdownguide.org/) - Comprehensive reference
- [GitHub Markdown Docs](https://docs.github.com/en/get-started/writing-on-github) - Official GitHub guide
- [CommonMark Spec](https://commonmark.org/) - Standard specification

**Cheat Sheets:**
- [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)

**Practice:**
- [Markdown Tutorial](https://www.markdowntutorial.com/) - Interactive lessons
- [Dillinger](https://dillinger.io/) - Online markdown editor

**VS Code Extensions:**
- Markdown All in One
- Markdown Preview Enhanced
- markdownlint (style checker)

---

## Practice Exercises

### Exercise 1: Complex Document

Create a markdown document with:
1. Multiple heading levels
2. At least one table
3. Task list with 5 items
4. A blockquote
5. Both bulleted and numbered lists
6. Multiple links
7. Bold and italic text
8. A code block

---

### Exercise 2: UX Document Templates

Create templates for:
- Research findings (with tables for metrics)
- User persona (with images)
- Meeting notes (with task lists)
- Design decision log (with dates and stakeholders)

---

### Exercise 3: Terminal Efficiency

Practice until you can do these without looking:
1. Navigate to Desktop
2. Create a project folder
3. Create 3 files with one command
4. List all files
5. View content of one file
6. Remove one file
7. Go up one directory
8. Confirm where you are

**Speed goal:** Under 2 minutes

---

## When You're Comfortable

**You'll know you've mastered this when:**
- You write markdown without constantly checking syntax
- Terminal navigation feels natural
- You use keyboard shortcuts instinctively
- You choose the right formatting for each situation
- You troubleshoot formatting issues quickly
- You create documentation without friction

**At that point:** You're ready for professional documentation work.

---

## Going Even Deeper

**If you want MORE:**

**Markdown:**
- Pandoc (convert markdown to PDF, Word, etc.)
- Jekyll/Hugo (static site generators)
- MDX (markdown with React components)

**Terminal:**
- Shell scripting (automate tasks)
- Aliases (custom shortcuts)
- Dotfiles (customize your terminal)

**Tools:**
- tmux (terminal multiplexer)
- vim/emacs (terminal text editors)
- Advanced Git commands

**But these are way beyond what you need for UX workflows!**

---

## Return to Main Course

When you're done exploring:
- Proceed to Week 2
- You now have deep markdown knowledge
- Use this as a reference when needed
- Don't feel you need to memorize everything

**The basics are 90% of what you'll use daily.**
