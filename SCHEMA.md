# Wiki Schema

## Domain
A living knowledge base of everything built, researched, and discovered across sessions with Hermes Agent. Covers projects, tools, decisions, workflows, learnings, and experiments.

## Conventions
- File names: lowercase, hyphens, no spaces (e.g., `sudoku-app.md`)
- Every wiki page starts with YAML frontmatter (see below)
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links per page)
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md` under the correct section
- Every action must be appended to `log.md`
- Provenance markers: on pages that synthesize 3+ sources, append `^[raw/...]` at the end of paragraphs

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: project | tool | concept | decision | workflow | experiment | person | query
tags: [from taxonomy below]
sources: []
confidence: high | medium | low
---
```

## Tag Taxonomy
- **Projects:** project, app, game, web, cli, api, backend, frontend
- **Tools:** tool, framework, library, model, llm, devops, infra
- **Workflow:** kanban, automation, cron, agent, skill, workspace
- **Knowledge:** concept, research, decision, learning, pattern, pitfall
- **Status:** active, completed, abandoned, paused, planned
- **Meta:** meta, index, log

## Page Thresholds
- **Create a page** when a project, tool, or concept is actively used or built
- **Add to existing page** when new info relates to something already covered
- **DON'T create a page** for passing one-off mentions
- **Split a page** when it exceeds ~200 lines

## Update Policy
- New info that contradicts existing: note both positions with dates
- Mark contradictions in frontmatter: `contradictions: [page-name]`
- Flag for review in lint report

## Auto-Collection Rules
The agent should proactively update the wiki when:
1. A new project or app is built → create a project page
2. A new tool, skill, or workflow is discovered → create a tool/workflow page
3. A significant decision is made → log it on the relevant project page
4. A kanban task completes → update or create the project page with outcomes
5. A new Hermes feature is configured → update the tools/hermes page
