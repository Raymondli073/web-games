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

**Wuziqi** (`wuziqi.html`) uses an HTML5 `<canvas>` for rendering the board and stones. Game state is held in a flat `grid` array (15×15), a `history` stack of `[row, col]` moves, and `undoUsed` counters per player. Drawing is fully re-rendered on every state change via `draw()`.

**Tic Tac Toe** (`tictactoe.html`) uses a CSS grid of `<div>` cells. State is a flat 9-element array.

## Git & GitHub Workflow

- Remote: `https://github.com/Raymondli073/web-games`
- Branch: `main`
- Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `chore:`, `refactor:`
- Commit each game or feature change as a separate commit with a short subject and bullet-point body describing added capabilities
- Always push to `origin main` after committing
