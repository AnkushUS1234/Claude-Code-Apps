# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a collection of self-contained web apps — each app is a single HTML file with embedded CSS and JavaScript. No build step, no dependencies, no server required. Open any `.html` file directly in a browser to run it.

## Adding a New App

Create a new `.html` file in the repo root. Each file should be fully self-contained (all CSS in `<style>`, all JS in `<script>`). No external CDN links or asset files.

---

## First-Time Setup: Claude Code + VS Code + GitHub

### 1. Install Claude Code in VS Code
1. Open VS Code
2. Go to the Extensions panel (`Cmd+Shift+X`)
3. Search for **Claude Code** and install it
4. Reload VS Code when prompted

### 2. Authenticate Claude Code
1. Open the Claude Code panel in VS Code (or open the integrated terminal and run `claude`)
2. Follow the sign-in prompt to log in with your Anthropic / Claude.ai account

### 3. Install GitHub CLI
```bash
brew install gh
```

### 4. Authenticate GitHub CLI
```bash
gh auth login
```
Follow the interactive prompts — choose **GitHub.com**, **HTTPS**, and authenticate via browser.

### 5. Create a Project Folder and Open in VS Code
```bash
mkdir my-project
cd my-project
code .
```

### 6. Use Claude Code to Build Your Project
Open the Claude Code panel in VS Code and describe what you want to build. Claude will create the files directly in the workspace.

### 7. Initialize a Git Repository
```bash
git init
```

### 8. Generate CLAUDE.md (Project Documentation)
In the Claude Code prompt, run:
```
/init
```
This analyzes the codebase and creates a `CLAUDE.md` file with project guidance.

### 9. Make the Initial Commit
```bash
git add .
git commit -m "Initial commit"
```

### 10. Create GitHub Repo and Push
```bash
gh repo create <repo-name> --public --source=. --remote=origin --push
```
Replace `<repo-name>` with your desired repository name. This creates the repo on GitHub and pushes `main` in one step.

---

## Claude Code: Beginner Commands Reference

### Slash Commands (type these in the Claude Code prompt)

| Command | What it does |
|---|---|
| `/help` | Show all available commands and keyboard shortcuts |
| `/init` | Analyze the project and generate a `CLAUDE.md` documentation file |
| `/clear` | Clear the conversation history and start fresh |
| `/config` | Open settings to change theme, model, editor mode, etc. |
| `/model` | Switch the AI model (Sonnet, Opus, Haiku) |
| `/review` | Ask Claude to review the current pull request |
| `/compact` | Summarize the conversation to free up context space |
| `/memory` | View and edit Claude's persistent memory about you and your projects |
| `/cost` | Show how many tokens the current conversation has used |
| `/doctor` | Check that your Claude Code installation is healthy |
| `/update` | Update Claude Code to the latest version |
| `/vim` | Toggle Vim keybindings in the input box |
| `/hooks` | View and manage automation hooks (e.g. run a command after every file edit) |

### Running Shell Commands Directly

Prefix any shell command with `!` to run it without leaving the prompt:

```
! git status
! ls
! npm install
```

### Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Enter` | Send message |
| `Shift+Enter` | New line without sending |
| `↑` | Edit your last message |
| `Esc` | Cancel the current Claude response |
| `Ctrl+C` | Stop Claude mid-response |

### Tips for Beginners

- **Be specific** — instead of "fix this", say "fix the bug in the `resetGame` function where the score resets"
- **Mention file names** — Claude works faster when you reference the exact file
- **Use `/clear` often** — long conversations slow Claude down; start fresh for new tasks
- **Ask Claude to explain** — you can always ask "explain what you just did" after any change
