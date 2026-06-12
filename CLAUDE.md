# CLAUDE.md — AI Writing System

Рабочие правила для Claude в репозитории `ai-story`. **Источник истины — файлы ниже**, подключённые через `@`-импорты: правки в `.cursor/rules/` и `.cursor/skills/` действуют автоматически и для Claude, и для Cursor. Не пересказывай и не дублируй их содержимое в этом файле.

## Правила (.cursor/rules)

@.cursor/rules/base.mdc
@.cursor/rules/project-architecture.mdc
@.cursor/rules/workflow.mdc
@.cursor/rules/source-priority.mdc
@.cursor/rules/memory-format.mdc
@.cursor/rules/missing-info-policy.mdc
@.cursor/rules/subagent-orchestration.mdc

## Процедуры (.cursor/skills)

- **Создание проекта** (новая книга/серия/мир/вселенная) — `book-project-setup`.
- **Работа над главой** (полный конвейер от плана до памяти) — `chapter-workflow`.

@.cursor/skills/book-project-setup/SKILL.md
@.cursor/skills/chapter-workflow/SKILL.md
