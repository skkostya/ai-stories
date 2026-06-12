---
name: chapter-workflow
description: Runs the full chapter workflow for the ai-story repository: plan, write, writer cleanup, critique, revise, continuity checks, and memory update. Use when the user asks to write, continue, draft, finish, revise, or process a chapter in a book or series project.
---

# Chapter Workflow

Use this skill for chapter-level work in this repository.

## Goal

Complete the full chapter workflow unless the user explicitly asks for only one stage.

## Source Of Truth

This skill is a procedural entry point. Canonical definitions live in rules and are **not duplicated here**:

- stage order, stage definitions, stage rules: `.cursor/rules/workflow.mdc`
- required context per stage, scope and grouping detection: `.cursor/rules/base.mdc`
- conflict resolution between sources: `.cursor/rules/source-priority.mdc`
- memory file formats and state files: `.cursor/rules/memory-format.mdc`
- subagent roles and limits: `.cursor/rules/subagent-orchestration.mdc`

## Procedure

1. Determine the active project, its grouping (ungrouped / `world` / `universe` + `world`), and its mode (`standalone` / `series`) from `rules/project.mdc`. Never assume them silently.
2. For grouped projects, read shared canon top-down (universe → world → story) before each stage, as required by `base.mdc`.
3. Run the stage sequence from `workflow.mdc`. Before each stage, explicitly read the matching `system/prompts/` file and the matching `system/mistakes/` file when it exists; before any prose, read `system/mistakes/writer-mistakes.md`.
4. Continuity checkpoints:
   - `series` projects: run `series_sync` after revision and before memory updates.
   - long `standalone` projects: run `arc_sync` at the part/zone boundary chapters defined by the project (`outline.md` / `memory/book-status.md`).
5. Update memory only after the chapter is stable enough to treat as canon, following `memory-format.mdc` (including `state.md` and project ledgers when present).

## Stop And Ask

Stop and ask the user if:

- required canon files are missing for canon-safe work
- accepted canon sources conflict
- project type, grouping, or active volume is unclear
- the requested change would retcon established canon (story, world, or universe level)

## Example Triggers

- "Напиши следующую главу"
- "Продолжи книгу"
- "Сделай главу 6"
- "Перепиши и доведи главу до финала"
- "Проведи полный chapter workflow для этой главы"
