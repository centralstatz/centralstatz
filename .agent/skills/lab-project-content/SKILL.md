---
name: lab-project-content
description: Draft concise, schema-valid CentralStatz Lab project-card metadata and a structured Quarto project notebook from analyzed evidence. Use after project analysis, for dry-run proposals, or when updating Lab project prose while preserving accuracy, attribution, limitations, and Alex’s voice.
---

# Lab project content

Read `../../../docs/lab-project-ingestion.md` and the closest existing project page. Use the real schema names: `description`, `image`, and `preview_alt`.

Draft metadata and notebook content only from the evidence matrix. Qualify reasonable inferences; omit unknowns. Keep the project’s problem, reasoning, artifact, limits, and next experiment ahead of its technology stack.

The public notebook should usually contain:

1. title, status, and stage;
2. concise deck/summary;
3. why the project exists;
4. central question and current hypothesis;
5. current visual or interactive artifact;
6. current state and latest meaningful development;
7. known limitations;
8. next experiment;
9. useful participation;
10. accurate ownership/attribution and verified public links.

Do not write a long README, marketing page, generic AI summary, exhaustive chronology, or technology inventory. State that a prototype is a current expression of an idea, not a final or validated product, where relevant.

Preserve Alex’s existing prose during updates. If his personal reasoning is genuinely absent, add at most a few hidden comments such as:

`<!-- TODO(Alex): What experience made this problem worth exploring? -->`

In dry-run mode, output proposed front matter, a concise page outline/draft, evidence classifications behind claims, unresolved questions, and intended files without editing.

In apply mode, prepare content for `lab/projects/<slug>/index.qmd`, but do not overwrite an existing page until it has been compared and the change is authorized. Then invoke/read `../lab-project-visual/SKILL.md`.
