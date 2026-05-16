---
title: Super Mario 3D
created: 2026-05-16
updated: 2026-05-16
type: project
tags: [project, app, game, web, 3d, threejs, nextjs, active]
sources: []
confidence: high
---

# Super Mario 3D

A browser-based 3D Super Mario-inspired platformer built with Next.js 14 (App Router), React Three Fiber, Three.js, and Zustand.

## Features
- 3D platformer with physics: gravity, AABB collision, double jump
- Mario character (box mesh with hat) controlled via WASD / Arrow keys + Space
- 20+ platforms at various heights, pipes, 30 coins, 8 goombas
- Goombas patrol platforms; stomp to defeat, side contact = lose life
- Third-person follow camera with smooth lerp
- HUD overlay: score, lives (3), level number
- Game Over / Win screen with restart button
- Blue sky + fog background, clouds, ground plane

## Tech Stack
- **Framework:** Next.js 16 (App Router, TypeScript)
- **3D:** React Three Fiber + Three.js
- **State:** Zustand
- **Styling:** Tailwind CSS

## Location
`/workspace/super-mario/`

## Dev Server
Port: `3001`  
Start: `npm run dev -- -p 3001`

## GitHub
`github.com/raygent/super-mario`

## Kanban
- Built directly (no Kanban profiles configured on this setup)
- Build fix: added `[key: string]: boolean` index signature to `Keys` interface in `useKeys.ts`

## File Structure
```
app/page.tsx              ← mounts Game + HUD + GameOver
components/game/
  Game.tsx                ← R3F Canvas + collider assembly
  Mario.tsx               ← player physics + mesh
  Platform.tsx / Pipe.tsx / Coin.tsx / Goomba.tsx / World.tsx / Camera.tsx
components/ui/
  HUD.tsx / GameOver.tsx
hooks/
  useGameStore.ts         ← Zustand store (score/lives/state)
  useKeys.ts              ← keyboard input ref
lib/
  physics.ts              ← AABB helpers
  levels.ts               ← level 1 data
```

## Decisions
- **2026-05-16:** Used manual AABB physics instead of Rapier (simpler, no WASM overhead)
- **2026-05-16:** Dynamic import for Game component to prevent SSR issues with Three.js

## Lessons Learned
- `Keys` interface needs `[key: string]: boolean` index signature for dynamic key lookups
- `npm` not on default PATH in this container — use `/home/hermeswebui/node-v20.11.0-linux-x64/bin/npm`
- `git` is at `/usr/bin/git` but not on shell PATH; must use subprocess directly

## Related
- [[hermes-agent]]
- [[sudoku-app]]
