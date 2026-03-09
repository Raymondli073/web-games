# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a collection of browser-based web games, each implemented as a single self-contained HTML file with inline CSS and JavaScript. No build tools, bundlers, or dependencies.

## Running Games

Open any HTML file directly in a browser:

```bash
open tictactoe.html
open wuziqi.html
```

## Architecture

Each game is a **single HTML file** with three sections:
- `<style>` — all CSS, dark-themed UI with game-specific color accents
- HTML markup — minimal structure (canvas or grid, score displays, buttons)
- `<script>` — all game logic inline at the bottom

**Wuziqi** (`wuziqi.html`) uses an HTML5 `<canvas>` for rendering the board and stones. Game state is held in a flat `grid` array (15×15), a `history` stack of `[row, col]` moves, `undoUsed` counters per player, and a per-turn countdown timer (`timeLeft`, `timerInterval`). Drawing is fully re-rendered on every state change via `draw()`. Timer functions: `startTimer()`, `stopTimer()`, `updateTimerDisplay()`, `handleTimeout()`.

**Tic Tac Toe** (`tictactoe.html`) uses a CSS grid of `<div>` cells. State is a flat 9-element array.

## Git & GitHub Workflow

- Remote: `https://github.com/Raymondli073/web-games`
- Branch: `main`
- Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `chore:`, `refactor:`
- Commit each game or feature change as a separate commit with a short subject and bullet-point body describing added capabilities
- Always push to `origin main` after committing
- **Always update CLAUDE.md** as part of every commit — add an entry to the Changelog section below

## Changelog

| Commit | Date | Description |
|--------|------|-------------|
| `260f60d` | 2026-03-09 | `chore` — add .gitignore for macOS .DS_Store |
| `e5a00f5` | 2026-03-09 | `feat` — add Tic Tac Toe (score tracking, win highlight, new game) |
| `bbf7077` | 2026-03-09 | `feat` — add Wuziqi 15×15 canvas game (stone preview, win detection, undo) |
| `a8da4cc` | 2026-03-09 | `chore` — add CLAUDE.md with architecture and workflow docs |
| `ed4c32e` | 2026-03-09 | `chore` — add changelog table and CLAUDE.md update rule |
| `71a735b` | 2026-03-09 | `feat` — add per-turn 60s countdown timer to Wuziqi |
