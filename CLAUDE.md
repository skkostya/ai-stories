# CLAUDE.md — AI Writing System

Этот файл — рабочие правила для Claude в репозитории `ai-story`. Они **дублируют** правила Cursor (`.cursor/rules/`), чтобы Claude работал по тем же канонам, что и Cursor. Источник истины — файлы ниже; они подключены через `@`-импорты, поэтому правки в `.cursor/rules/` автоматически действуют и для Claude.

## Подключённые правила (дублируют .cursor/rules)

@.cursor/rules/base.mdc
@.cursor/rules/project-architecture.mdc
@.cursor/rules/workflow.mdc
@.cursor/rules/source-priority.mdc
@.cursor/rules/memory-format.mdc
@.cursor/rules/missing-info-policy.mdc
@.cursor/rules/subagent-orchestration.mdc

## Рабочие процедуры (дублируют .cursor/skills)

Те же два процесса, что и в Cursor:

- **Создание проекта** (новая книга/серия) — следуй процедуре в `@.cursor/skills/book-project-setup/SKILL.md`.
- **Работа над главой** (план → черновик → writer cleanup → критика → ревизия → series-continuity для серий → обновление памяти) — следуй процедуре в `@.cursor/skills/chapter-workflow/SKILL.md`.

@.cursor/skills/book-project-setup/SKILL.md
@.cursor/skills/chapter-workflow/SKILL.md

## Ключевые напоминания (краткая выжимка)

- Не полагайся на неявную память модели — канон, преемственность и состояние процесса храни в файлах проекта.
- Перед каждой стадией явно читай соответствующий промпт из `system/prompts/` и файл ошибок из `system/mistakes/`.
- Перед прозой writer-стадии обязательно прочитай `system/mistakes/writer-mistakes.md`.
- Определи режим проекта (`standalone` / `series`) и группировку (ungrouped / в составе `world` / в составе `universe`) до начала любой стадии.
- Для сгруппированных проектов читай общий канон сверху вниз (universe → world → story) и не противоречь ему; смена общего канона мира/вселенной — кросс-сюжетный реткон, останавливайся и спрашивай.
- При конфликте источников используй приоритет из `source-priority.mdc`. Если истинность канона неясна — остановись и спроси, не выдумывай.
- Память обновляй точечно и только после стабилизации главы как канона; факты, а не пересказ.
- Один ведущий агент — единственный «привратник» канона; субагентов подключай выборочно.
