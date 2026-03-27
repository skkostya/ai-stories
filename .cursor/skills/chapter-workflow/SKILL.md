---
name: chapter-workflow
description: Runs the full chapter workflow for the ai-story repository: plan, write, writer cleanup, critique, revise, series continuity check, and memory update. Use when the user asks to write, continue, draft, finish, revise, or process a chapter in a book or series project.
---

# Chapter Workflow

Use this skill for chapter-level work in this repository.

## Goal

Complete the full chapter workflow unless the user explicitly asks for only one stage.

## Determine Scope

1. Identify the active project under `books/<project_id>/`.
2. Read local rules in `rules/project.mdc` and `rules/style.mdc` when present.
3. Determine project type from local rules:
   - `standalone`: one book scope
   - `series`: series scope plus active volume scope

## Stage Order

1. Plan the chapter.
2. Write the chapter.
3. Run writer cleanup.
4. Critique the result.
5. Revise the chapter.
6. If the project is `series`, run series continuity review before memory updates.
7. Update memory only after the chapter is stable enough to treat as canon.

## Required Reading By Stage

Before each stage, explicitly read:

- the matching file in `system/prompts/`
- the matching file in `system/mistakes/` when it exists
- the required local canon and memory files for the active scope

Do not assume files read for one stage still count for later stages.

## Stage Notes

### Planning

- Read outline, characters, relevant memory, and the previous canon chapter when available.
- In `series` projects, align with both series arc and active-volume arc.
- Save or return the plan in the format required by `system/prompts/planner.md`.

### Writing

- Use the approved chapter plan.
- Respect local rules for language, POV, tone, and chapter scope.
- Return or save the full chapter text only.

### Writer Cleanup

- Read `system/prompts/writer-cleanup.md`.
- Enforce `system/mistakes/writer-mistakes.md` on the actual prose after drafting.
- Fix paragraphing, local flow, repetition, and sentence-level execution issues without changing plot or canon.

### Critique

- Focus on structure, character logic, canon consistency, pacing, and missed opportunities.
- Prefer actionable findings over vague praise.

### Revision

- Fix the highest-impact problems first.
- Strengthen the chapter without flattening voice or creating accidental retcons.

### Series Continuity

- Use only for `series` projects.
- Run after revision and before memory updates.
- Separate series-level consequences from active-volume consequences.

### Memory Update

- Update only the relevant memory sections.
- Add facts, not prose summaries.
- In `series` projects, keep series memory and volume memory distinct.

## Subagent Use

- Default to the lead agent only for small standalone tasks.
- Use subagents selectively when they reduce context load or provide an independent check.
- Best default roles:
  - `critic`
  - `series-continuity`
  - `memory-updater`
- The lead agent remains the final canon gatekeeper.

## Stop And Ask

Stop and ask the user if:

- required canon files are missing for canon-safe work
- accepted canon sources conflict
- project type or active volume is unclear
- the requested change would retcon established canon

## Example Triggers

- "Напиши следующую главу"
- "Продолжи книгу"
- "Сделай главу 6"
- "Перепиши и доведи главу до финала"
- "Проведи полный chapter workflow для этой главы"
