---
title: Sudoku App
created: 2026-05-13
updated: 2026-05-13
type: project
tags: [project, app, game, web, completed]
sources: []
confidence: high
---

# Sudoku App

A fully playable browser-based Sudoku game built as the first Kanban task.

## Overview
Single-file HTML/CSS/JS application with puzzle generation, dark-themed UI, and multiple input methods.

## Features
- 3 difficulty levels: Easy, Medium, Hard
- Timer
- Hint, Solve, and Check buttons (with error highlighting)
- Keyboard navigation
- On-screen numpad
- Dark-themed UI

## Location
`/workspace/sudoku/sudoku.html`

## Kanban
- Task ID: `t_bb002282`
- Status: Done
- Ran 2 times (run 1 built it, run 2 confirmed it was already complete)
- Workspace was `scratch` — file manually copied to `/workspace/sudoku/`

## Decisions
- **2026-05-13:** Kanban scratch workspace used (default). Going forward, tasks will use `dir:/workspace/<project>/` so output lands directly in the workspace. See [[hermes-agent#Kanban Conventions]].

## Lessons Learned
- Kanban scratch workspaces are isolated and invisible in the WebUI — always use `dir:/workspace/<project>/` for new tasks
- Files must be manually copied out of scratch workspaces

## Related
- [[hermes-agent]]
