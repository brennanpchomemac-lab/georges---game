# George's Game — Project Instructions for Claude Code

This file tells Claude Code everything it needs to know about this project.
Read this before doing anything else in this repo.

---

## 🎮 Project Overview

- **What it is:** A browser-based game built with HTML, CSS, and JavaScript
- **Who's building it:** George (beginner coder)
- **Main file:** `index.html` — this is the game. Open it in a browser to play.
- **Goal:** Gradually add features, keep code clean, and save every version to GitHub

---

## 📁 Project Structure

```
georges-game/
├── CLAUDE.md        ← you are here (project instructions)
├── README.md        ← project description on GitHub
├── index.html       ← the game (main file)
├── style.css        ← game styles (create if needed)
└── game.js          ← game logic (create if needed, or keep in index.html for now)
```

Keep the structure simple. Don't add folders or files unless George asks for them.

---

## ⚠️ Worktree Warning

Claude Code sometimes runs in a **git worktree** — a separate folder inside `.claude/worktrees/`. This is NOT the same as the main project folder on the Desktop. Changes made in a worktree are pushed to GitHub but **do not automatically appear in the main folder**.

**After every push, always run this to update the main project folder:**
```bash
git -C /Users/brennanpc/Desktop/georges---game pull
```
This is required so George can refresh `index.html` in the browser and see the changes.

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
git push
git -C /Users/brennanpc/Desktop/georges---game pull
```
The final `git pull` updates George's actual game folder so the browser shows the new version immediately.

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
3. Run `git add . && git commit -m "..." && git push`
4. Tell George what to do to see it: "Refresh your browser and try pressing Space"

### When George reports a bug:
1. Identify the most likely cause
2. Fix only that specific thing (don't refactor unrelated code)
3. Explain what was wrong and why the fix works
4. Commit with a message starting with `Fix:`

---

## 🎨 Code Style Rules

- Use **vanilla JavaScript** only — no external libraries unless George specifically asks
- Keep all game code in `index.html` until the file gets too long (300+ lines), then split into `game.js`
- Use `const` and `let`, never `var`
- Add a blank line between logical sections of code
- Comment every major block: player movement, collision detection, score system, etc.

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

## 🚀 Running the Game Locally

The game runs directly in the browser — no server needed.

To open it:
```bash
open index.html        # Mac
start index.html       # Windows
```

Or just double-click `index.html` in the file explorer.

To see changes: save the file, then refresh the browser (F5 or Cmd+R).

---

## 📋 Feature Backlog

Add features here as George thinks of them. Work through them one at a time.

### Next up:
- [ ] (George fills this in)

### Ideas for later:
- [ ] (George fills this in)

---

## ⚠️ Important Reminders

- **Always pull before starting:** `git pull`
- **Always push after finishing:** `git add . && git commit -m "..." && git push`
- **Never break the game** — test after every change
- **Keep it simple** — George is learning, complexity comes later
- **One feature at a time** — finish and commit before starting the next
