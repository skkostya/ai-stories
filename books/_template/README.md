# Book Project Template

Use this directory as the starting point for a new book or series project.

## Recommended Setup

1. Copy `_template/` to `books/<project_id>/`
2. Fill in `rules/project.mdc`
3. Set `Project type` to `standalone` or `series`
4. Fill in `rules/style.mdc`
5. Fill in root `outline.md` and `characters.md`
6. Add optional `world-rules.md` and `timeline.md` if needed
7. Keep the appropriate `memory/` files updated as canon grows

## Standalone Use

- Treat the project root as one book.
- Use root `outline.md`, `characters.md`, `timeline.md`, and `memory/` as the active canon files.
- You can ignore `volumes/` unless you later convert the project into a series.

## Series Use

- Treat the project root as series-level canon.
- Use root `outline.md`, `characters.md`, `timeline.md`, and root `memory/` only for long-range series facts.
- Use `volumes/book01/` for the first book's outline, chapter work, and book-local memory.
- Add `volumes/book02/`, `volumes/book03/`, and so on as the series grows.

## Notes

- `project.mdc` defines project-level canon and workflow expectations.
- `style.mdc` defines voice and presentation rules for this specific project.
- Global rules in `.cursor/rules/` still apply.
- In `series` projects, root files describe the series and `volumes/<book_id>/` describes the active book.
