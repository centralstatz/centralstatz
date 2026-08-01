# CentralStatz Lab agent guide

## Site identity

CentralStatz is presented as an independent analytical systems lab that turns rigorously reasoned ideas into tangible, testable, and often interactive prototypes. The site is not a generic AI demo gallery, software-agency portfolio, collection of randomly prompted tools, conventional SaaS landing page, or claim that displayed work is finished or production-ready.

Preserve the legal identity “CentralStatz Statistical & Data Sciences LLC,” the existing logo, and the “Structure Before Sophistication” philosophy.

## Architecture

- Quarto website; build with `quarto render` and preview with `quarto preview`.
- Global configuration and navigation: `_quarto.yml`.
- Homepage: `index.qmd`.
- Lab project source: `projects/<slug>/index.qmd`.
- Homepage project rendering: `_templates/project-card.ejs.md`, populated from project front matter through the listing in `index.qmd`.
- Visual system: `styles.scss`; generated production output: `_site/`.
- Project schema and vocabulary: `docs/lab-project-ingestion.md`.
- Ingestion skills: `.agent/skills/`.
- Utilities: `scripts/new-lab-project` and `scripts/validate-lab-projects`.

Read this file and any source project’s `AGENTS.md` before analyzing or changing a project.

## Project philosophy

Every project should communicate:

- the observation or real problem motivating it;
- why the project deserves to exist;
- its current hypothesis or design idea;
- the current tangible artifact;
- what is known and what remains uncertain;
- its honest stage and status;
- what might happen next.

Treat the interface, screenshot, output, diagram, or visual as the current visible representation of the project’s underlying reasoning—not proof that the reasoning is correct or the work is complete.

Rapid implementation should expand the analytical possibilities a project can responsibly consider, not merely produce a predetermined solution faster. Let the problem determine whether the useful artifact is a simple method, an alternative formulation, an interactive system, or something else. Added technical capability does not make complexity inherently better; “Structure Before Sophistication” remains the test for where additional machinery earns its place.

## Accuracy and evidence

Inspect source material before writing. Classify consequential statements in working notes as **Supported fact**, **Reasonable inference**, **Unknown**, or **Private or unsuitable for publication**. Publish supported facts and clearly qualified interpretations; never turn unknowns into marketing claims.

Do not invent or imply unsupported maturity, adoption, validation, collaborators, performance, ownership, deployment, public URLs, pilots, or production readiness. A healthcare prototype is not clinically valid merely because it exists. Preserve licenses, attribution, collaboration context, and ownership boundaries. Never imply CentralStatz owns a framework, repository, or contribution without evidence.

Prefer candid terms such as “exploring,” “early framework,” “current hypothesis,” and “prototype.” If accuracy, ownership, or permission to publish is materially unclear, default to a dry run and ask only the questions needed to resolve the risk.

## Privacy and publication safety

Do not publish credentials, secrets, environment variables, local paths, internal URLs, protected health information, proprietary client data, private organization names, confidential logic, unpublished collaborator details, sensitive screenshots, or internal issue content. A private project may be described only at a safe level approved by Alex. Inspect images as well as text.

## Voice

Write precise, thoughtful, technically credible, exploratory prose for a technically literate non-specialist. Be candid about limits. Ground the story in the problem and Alex’s reasoning, not the implementation stack.

Avoid startup hype, generic AI prose, inflated progress, “revolutionary” claims, buzzword lists, and descriptions that could apply to any project. Use hidden HTML comments such as `<!-- TODO(Alex): ... -->` only when Alex’s personal reasoning would materially strengthen the page; never expose TODOs in rendered content.

## Design and visuals

Preserve the charcoal, gold, blue, and neutral palette; workbench aesthetic; typography; spacing; card structure; stage convention; responsive behavior; visible focus states; reduced-motion support; and meaningful alt text. Favor a landscape preview near 16:9 (approximately 1600×900); the card crops with `object-fit: cover`, so keep the subject away from fragile edges.

Visual priority:

1. real interface screenshot;
2. real project output or visualization;
3. real architecture/concept diagram;
4. newly generated explanatory diagram grounded in evidence;
5. branded temporary concept image;
6. restrained placeholder.

Generate a visual only when no meaningful interface exists, a concept needs explanation, or the real artifact is unsuitable. Generated visuals must represent actual concepts, match the Lab system, avoid generic AI imagery and fake controls, contain little text, and never serve as evidence of working functionality. Set `visual_type` and `visual_is_concept`, caption concepts where confusion is possible, provide alt text, and keep replacement to an asset-path change.

## Ingestion workflow

Use the skills in this order:

1. `lab-project-intake`
2. `lab-project-analysis`
3. `lab-project-content`
4. `lab-project-visual`
5. `lab-project-integration`

Support dry-run and apply modes. Dry-run must propose metadata, content, stage/status, visual, evidence classifications, and intended files without writes. Default to dry-run when ownership, privacy, publication status, attribution, or a substantial rewrite is uncertain. Apply only when requested or clearly safe and in scope.

When updating an existing project, compare new evidence with the current page and preserve human-authored text unless a rewrite was requested.

## Validation

Before handoff:

1. Run `scripts/validate-lab-projects`.
2. Run `quarto render`.
3. Check new local assets and generated routes.
4. Inspect the homepage card and detail page visually.
5. Check alt text, heading hierarchy, keyboard access, and responsive layout where practical.
6. Run `git diff --check` on source changes.
7. Report supported facts, inferences, omissions, private findings not copied, provisional content, and any checks that could not be run.

Do not commit or push unless explicitly requested.
