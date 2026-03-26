---
name: book-project-setup
description: Creates or scaffolds a new book or series project in the ai-story repository using the repository architecture, template layout, and local rules structure. Use when the user asks to start a new book, create a new project, scaffold a standalone book, or set up a multi-book series.
---

# Book Project Setup

Use this skill when creating a new project under `books/`.

## Goal

Create a safe, minimal project scaffold that matches the repository architecture without changing existing canon by accident.

## Default Location

- Create new projects under `books/<project_id>/`.
- Treat `books/_template/` as the structural reference when needed.

## First Decisions

1. Determine whether the project is `standalone` or `series`.
2. Determine the `project_id`.
3. Determine the primary language and intended audience if the user already provided them.
4. If the project is `series`, determine the active volume naming convention before creating volume-specific files.

## Required Clarifications

Ask before proceeding if any of these are unclear:

- `standalone` or `series`
- project id or folder name
- for `series`, the initial active volume id if volume folders should be created now

## Creation Rules

- Follow the workspace architecture in `.cursor/rules/project-architecture.mdc`.
- Do not overwrite or rewrite existing project files unless the user explicitly requests it.
- Prefer creating a minimal valid scaffold over generating too much placeholder prose.
- Create only files that are structurally useful now.
- Keep template content concise and editable.

## Standalone Scaffold

Create these when starting a new standalone book:

- `books/<project_id>/rules/project.mdc`
- `books/<project_id>/rules/style.mdc`
- `books/<project_id>/outline.md`
- `books/<project_id>/characters.md`
- `books/<project_id>/chapters/`
- `books/<project_id>/plans/`
- `books/<project_id>/critique/`
- `books/<project_id>/revisions/`
- `books/<project_id>/memory/events.md`
- `books/<project_id>/memory/relationships.md`
- `books/<project_id>/memory/foreshadowing.md`
- `books/<project_id>/memory/mistakes.md`

Optional if the user wants them now:

- `books/<project_id>/world-rules.md`
- `books/<project_id>/timeline.md`

## Series Scaffold

Create these when starting a new series:

- `books/<project_id>/rules/project.mdc`
- `books/<project_id>/rules/style.mdc`
- `books/<project_id>/outline.md`
- `books/<project_id>/characters.md`
- `books/<project_id>/memory/events.md`
- `books/<project_id>/memory/relationships.md`
- `books/<project_id>/memory/foreshadowing.md`
- `books/<project_id>/memory/unresolved-threads.md`
- `books/<project_id>/memory/book-status.md`
- `books/<project_id>/memory/mistakes.md`
- `books/<project_id>/volumes/<book_id>/outline.md`
- `books/<project_id>/volumes/<book_id>/chapters/`
- `books/<project_id>/volumes/<book_id>/plans/`
- `books/<project_id>/volumes/<book_id>/critique/`
- `books/<project_id>/volumes/<book_id>/revisions/`
- `books/<project_id>/volumes/<book_id>/memory/events.md`
- `books/<project_id>/volumes/<book_id>/memory/relationships.md`
- `books/<project_id>/volumes/<book_id>/memory/foreshadowing.md`
- `books/<project_id>/volumes/<book_id>/memory/mistakes.md`

Optional if the user wants them now:

- `books/<project_id>/world-rules.md`
- `books/<project_id>/timeline.md`
- `books/<project_id>/volumes/<book_id>/characters.md`
- `books/<project_id>/volumes/<book_id>/timeline.md`

## File Guidance

### `rules/project.mdc`

- Set project identity, project type, language, audience, canon priorities, narrative constraints, and workflow notes.
- Match the repository template style.

### `rules/style.mdc`

- Set tone, genre, pacing, voice rules, and avoid-lists.
- Keep it specific enough to guide chapter writing, but not overfit before the story exists.

### Memory Files

- Create concise section-ready files, not long prose.
- Keep them ready for incremental updates.

## Safety

- If there is any ambiguity about canon migration from an older draft or folder, stop and ask.
- Do not silently classify a project as `series` or `standalone`.
- Do not invent major canon just to fill empty scaffold files.

## Example Triggers

- "Создай новый проект книги"
- "Нужен каркас для новой серии"
- "Сделай standalone проект под новую историю"
- "Подготовь структуру для цикла из трех книг"
