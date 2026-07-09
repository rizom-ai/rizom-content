# Rizom Content

The consolidated Rizom brain's content — the writer of record behind
[rizom.ai](https://rizom.ai) and its rooms (`/work`, `/foundation`).

Merged from `rizom-ai-content`, `rizom-work-content`, and
`rizom-foundation-content` with full history (see the Phase 3 collision
pass in the brains monorepo's `docs/plans/rizom-consolidation.md`).
Entities sync bidirectionally with the brain via directory-sync: one
directory per entity type, one markdown file per entity. Site copy
lives in `@brains/site-rizom-ai`'s schema-validated sections; overrides
sync here as `site-content/<page>/<section>.md` when edited through
the brain.
