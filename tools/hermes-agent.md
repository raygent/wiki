---
title: Hermes Agent
created: 2026-05-13
updated: 2026-05-13
type: tool
tags: [tool, agent, workflow, kanban, workspace, skill]
sources: []
confidence: high
---

# Hermes Agent

The AI assistant environment powering this workspace. Tracks setup, conventions, and discoveries made over time.

## Environment
- Host: Linux (Unraid)
- WebUI workspace panel root: `/workspace` (NOT `/home/hermeswebui/workspace`)
- Hermes CLI invocation: `PYTHONPATH="/home/hermeswebui/.hermes/hermes-agent/.venv/lib/python3.13/site-packages:/home/hermeswebui/.hermes/hermes-agent" python3 /home/hermeswebui/.hermes/hermes-agent/hermes <cmd>`
- Config: `/home/hermeswebui/.hermes/config.yaml`
- Local Qwen model server: `http://10.90.2.21:9223/v1` (provider: `omlx`)
- Home Assistant: `http://10.90.3.169:8123`

## Wiki
- Path: `/workspace/wiki` (set via `WIKI_PATH` in `~/.hermes/.env`)
- Auto-updated as projects are built and discoveries are made

## Kanban Conventions
- Always use `--workspace dir:/workspace/<project>/` when creating tasks
- Infer project name from task title (kebab-case, 1-3 words)
- Workers should write a `README.md` in the project dir
- Skill: `kanban-project-workspace` captures this convention

## Skills Notable
- `kanban-project-workspace` — enforces project-scoped workspaces for kanban tasks
- `llm-wiki` — wiki knowledge base pattern (this wiki!)

## Pitfalls
- `/workspace` ≠ `/home/hermeswebui/workspace` — always use `/workspace` for WebUI-visible files
- `hermes` CLI not in PATH; use the full PYTHONPATH invocation above

## Related
- [[sudoku-app]]
