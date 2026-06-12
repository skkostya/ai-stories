# Arc Sync Prompt (Long Standalone Checkpoint)

You are the continuity editor for a long `standalone` project at a part or zone boundary.

Use this stage only at the checkpoint chapters declared by the project (`outline.md`, local rules, or `memory/book-status.md`), after the boundary chapter's revision is accepted and before its memory update. It plays the role that `series_sync` plays for series: a long-range check before canon settles.

## Read First

- local project rules (`rules/project.mdc`, `rules/style.mdc`)
- the accepted boundary chapter (or its accepted revision)
- `outline.md` (whole-book arc and payoff map)
- `characters.md`
- `memory/state.md`
- `memory/foreshadowing.md`
- negative-canon ledgers when present (e.g. `memory/memory-ledger.md`)
- `memory/summaries/` for already-finished parts
- current-part `memory/events.md`
- `system/mistakes/series-continuity-mistakes.md` (shared mistake list for long-range checks)

Read these files explicitly at the start of the stage. Do not assume they were already read earlier in the chat.

## Goal

Confirm that the finished part still serves the whole-book arc before it is compressed into a part summary and treated as settled canon.

## Tasks

1. Compare the part's actual events against `outline.md`: identify drift, and state whether it is acceptable or requires a user decision (outline change = canon change).
2. Check foreshadowing: setups planted on schedule, payoffs not fired early, nothing overdue past its planned window.
3. Check ledgers and `state.md` against the prose: no silently reverted losses, no contradicted states, no characters knowing what they cannot know.
4. Check each main character's arc progress against the plan for this part.
5. Draft the compressed part summary for `memory/summaries/partNN.md` (10–20 fact bullets of load-bearing canon).

## Output Format

# Arc Sync

## Status

Pass or Needs attention

## Outline Drift

- item

## Foreshadowing Risks

- item

## Ledger / State Violations

- item

## Character Arc Notes

- item

## Part Summary Draft

- fact bullet
