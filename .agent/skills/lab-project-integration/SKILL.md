---
name: lab-project-integration
description: Safely add or update a CentralStatz Lab Quarto project, assets, homepage-card discovery, ordering, documentation, and validation. Use for apply-mode ingestion, project updates, scaffolding, schema checks, route/asset checks, or final verification after project content or imagery changes.
---

# Lab project integration

Read `../../../AGENTS.md` and `../../../docs/lab-project-ingestion.md`.

For dry-run, report proposed files and stop without writes.

For apply mode:

1. Confirm the repository branch and inspect the worktree.
2. Check `lab/projects/<slug>/` and titles for duplicates.
3. If updating, compare source evidence with current content; preserve human-authored text unless rewrite was requested.
4. Create the folder with `scripts/new-lab-project <slug> "Title"` when useful, then replace scaffold placeholders with supported content.
5. Store local visuals in the project folder when practical and use paths relative to `index.qmd`.
6. Keep `order` unique and verify `lab/index.qmd` discovers `lab/projects/*/index.qmd` automatically.
7. Do not change the card template, styles, or schema unless ingestion genuinely requires it; document durable schema changes.
8. Run `scripts/validate-lab-projects`.
9. Run `quarto render`.
10. Verify `_site/lab/projects/<slug>/index.html`, Lab homepage card text/image/link, alt text, local assets, headings, and responsive behavior where practical.
11. Run `git diff --check` on source changes.

Report files changed, supported facts, qualified inferences, unknowns omitted, private material excluded, status/stage rationale, visual provenance, provisional content, and every validation result. Do not commit or push unless requested.
