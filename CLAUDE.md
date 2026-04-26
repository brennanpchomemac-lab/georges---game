# George's Games — Project Instructions for Claude Code

This file tells Claude Code everything it needs to know about this project.
Read this before doing anything else in this repo.

---

## 🎮 Project Overview

- **What it is:** A collection of browser-based games built with HTML, CSS, and JavaScript
- **Who's building it:** George and the kids (beginners)
- **How to play:** Double-click any `.html` file in the project folder to open it in a browser
- **Goal:** Build multiple games, each saved as its own file, all in the same folder so the kids can easily find and launch them

---

## 📁 Project Structure

```
georges-game/
├── CLAUDE.md              ← you are here (project instructions)
├── README.md              ← project description on GitHub
├── snake game.html        ← Star Snake game
└── [new game name].html   ← each new game gets its own named file
```

**Rules:**
- Every game is a single self-contained `.html` file
- Keep all CSS and JavaScript inside that one file (no separate `.css` or `.js` files) until the file exceeds ~300 lines
- Don't add subfolders unless George asks
- Don't name any game `index.html`

---

## 🆕 Creating a New Game

**Always ask for the game name first.** Before writing any code for a new game, say:

> "What would you like to call this game? The file will be saved as `[name].html`."

Once George gives a name:
1. Create a new file named exactly `[game name].html` (e.g., `space shooter.html`, `brick breaker.html`)
2. Build the game self-contained in that file
3. Include a `VERSION` constant starting at `v1.0` and display it somewhere on the screen
4. Commit with: `Add [game name] starter game`

Never reuse or overwrite an existing game file when starting a new one.

---

## ⚠️ Worktree Warning

Claude Code sometimes runs in a **git worktree** — a separate folder inside `.claude/worktrees/`. This is NOT the same as the main project folder on the Desktop. Changes made in a worktree are pushed to GitHub but **do not automatically appear in the main folder**.

**After every push, always run this to update the main project folder:**
```bash
git -C /Users/brennanpc/Desktop/georges---game pull
```
This is required so the kids can refresh the browser and see the latest version.

---

## 🔄 Git & GitHub Workflow

Follow these rules **every single session**, without being asked:

### Before starting any work:
```bash
git -C /Users/brennanpc/Desktop/georges---game pull
```
Always pull first to get the latest code before making changes.

### After completing any feature or fix:
```bash
git add .
git commit -m "<short description of what changed>"
git push origin HEAD:main
git -C /Users/brennanpc/Desktop/georges---game pull
```
The final `git pull` updates the actual game folder so the browser shows the new version immediately.

### Commit message rules:
- Keep it short and descriptive (under 60 characters)
- Use present tense: "Add enemy movement" not "Added enemy movement"
- Be specific: "Fix player going off right edge" not "Bug fix"

### Good commit message examples:
- `Add score counter in top-left corner`
- `Fix player clipping through floor`
- `Add red enemy that bounces around screen`
- `Make player jump with spacebar`
- `Add game over screen when enemy touches player`

### Never:
- Commit broken code that crashes the game
- Use vague messages like "update", "changes", or "fix"
- Push without testing that the game still loads in a browser

---

## 🧠 How to Work With George

George is a beginner. When making changes:

1. **Explain what you're doing** in plain English before writing code
2. **Make one change at a time** — don't add 5 features at once
3. **Add comments** in the code so George can learn from it
4. **Test your logic** — make sure the game still runs after every change
5. **Keep code readable** — use clear variable names, not `x1`, `tmp`, `fn2`

### When George asks for a new feature:
1. Describe the plan in 2-3 sentences
2. Write the code with inline comments
3. Bump the VERSION number (v1.0 → v1.1, etc.) in the game file
4. Run the full git workflow above
5. Tell George what to do to see it: "Refresh your browser and try pressing Space"

### When George reports a bug:
1. Identify the most likely cause
2. Fix only that specific thing (don't refactor unrelated code)
3. Explain what was wrong and why the fix works
4. Commit with a message starting with `Fix:`

---

## 🎨 Code Style Rules

- Use **vanilla JavaScript** only — no external libraries unless George specifically asks
- Keep all game code in the single `.html` file until it exceeds ~300 lines
- Use `const` and `let`, never `var`
- Add a blank line between logical sections of code
- Comment every major block: player movement, collision detection, score system, etc.
- Always include a `VERSION` constant and display it visibly on screen

### Formatting example:
```javascript
// --- Player Movement ---
// Move the player based on which arrow keys are held down
if (keys['ArrowLeft'])  player.x -= player.speed;
if (keys['ArrowRight']) player.x += player.speed;

// Keep player inside the canvas boundaries
player.x = Math.max(0, Math.min(canvas.width - player.size, player.x));
```

---

## 🚀 Running a Game Locally

Each game runs directly in the browser — no server needed.

To open a game, just double-click its `.html` file in the Finder.

To see changes after an update: save the file, then refresh the browser (F5 or Cmd+R).

---

## 📋 Games in This Project

| File | Game | Status |
|------|------|--------|
| `snake game.html` | Star Snake | Active |

Add new rows here as new games are created.

---

## ⚠️ Important Reminders

- **Always ask for the game name** before creating a new game
- **Always pull before starting:** `git -C /Users/brennanpc/Desktop/georges---game pull`
- **Always push after finishing:** full workflow above, including the final pull
- **Never break the game** — test after every change
- **Keep it simple** — George is learning, complexity comes later
- **One feature at a time** — finish and commit before starting the next
