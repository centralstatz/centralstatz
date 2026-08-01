# CentralStatz website

CentralStatz Statistical & Data Sciences LLC is a statistical and data science consultancy in Central Wisconsin. This repository contains the [Quarto](https://quarto.org/) source for [centralstatz.com](https://www.centralstatz.com/).

## CentralStatz Lab branch

The `feature/centralstatz-lab` branch is an exploratory redesign that presents CentralStatz as an independent analytical systems lab. It preserves the legal business identity, logo, brand foundation, contact workflow, and “Structure Before Sophistication” philosophy while making active prototypes the center of the experience. The Lab treats faster implementation as an opportunity to reconsider what analytical work can become—not just to produce a predetermined solution sooner—while retaining simple methods whenever they best fit the question.

## Run the site

Install Quarto 1.7 or newer, then run:

```sh
quarto preview
```

Create the production build with:

```sh
quarto render
```

The generated site is written to `_site/` and is tracked in this repository. The homepage previously executed an R/Leaflet map; the Lab redesign removes that runtime requirement, so no R packages are needed to render the new site.

## Project content

Each lab project lives at `projects/<slug>/index.qmd`. Its YAML front matter is the structured source for homepage cards; its Markdown body is the project notebook. `_templates/project-card.ejs.md` controls card presentation.

To add a project:

1. Copy an existing directory under `projects/` and choose a URL-safe slug.
2. Update the front matter. Required card fields are `title`, `description`, `category`, `status`, `stage`, `order`, `central_question`, `current_state`, `latest_update`, `next_step`, and `looking_for`.
3. Set `stage` to one of `Question`, `Concept`, `Prototype`, `Validation`, `Pilot`, or `Production` so the stage track renders correctly.
4. Set `status` with plain, accurate language such as `Exploring`, `Active development`, `Seeking feedback`, `Pilot ready`, `Maintained`, `Paused`, or `Archived`.
5. Add `image` and meaningful `preview_alt` values. Keep the asset beside the project when practical; replace the path to update a preview.
6. Write concise notebook content that distinguishes demonstrated behavior from hypotheses, limits, and future work.
7. Run `quarto render` and inspect the card and detail page at desktop and mobile widths.

Optional schema fields currently include `date-modified`, `current_hypothesis`, `limitations`, `featured`, and `tags`. External `live_url` or `repository_url` fields may be added when truthful public links exist.

## Agent-assisted project ingestion

The reusable ingestion workflow accepts repository URLs, local paths, live applications, websites, documents, notes, images, direct descriptions, or combinations. Durable repository instructions are in `AGENTS.md`; focused skills are under `.agent/skills/`. Full schema, invocation, evidence, privacy, attribution, visual, and manual-editing guidance is in `docs/lab-project-ingestion.md`.

Use the skills in order: intake, analysis, content, visual, then integration. Begin with a dry run when ownership, publication status, privacy, attribution, or a substantial rewrite is uncertain:

```text
Use the Lab project-ingestion skills.

Source:
<URL, local path, files, or description>

Mode:
dry-run

Additional context:
<ownership, privacy, desired emphasis, visual, or participation notes>
```

In dry-run mode the agent proposes content and files without modifying the site. In apply mode it creates or updates the project, validates it, renders Quarto, and reports facts, inferences, unknowns, and excluded private material.

Create a manual draft with:

```sh
scripts/new-lab-project project-slug "Project Title"
```

The draft deliberately fails validation until its TODOs are replaced and `draft` is false or removed. Validate all projects with:

```sh
scripts/validate-lab-projects
```

New projects should record `ownership`, `source_type`, `visibility`, `visual_type`, and `visual_is_concept`. Prefer real screenshots or outputs. Generated concepts must be labeled, must not imply working functionality, and can use the visual brief template at `.agent/skills/lab-project-visual/assets/visual-brief-template.md`. Replacing a concept later requires changing only the project’s `image` path and provenance fields.

## Provisional content

The current repository only substantiates two experiments: a hospital-readmissions exploration interface and an on-demand Google Analytics report. Their maturity, validation, public availability, adoption, and operational use are not documented and are therefore not claimed. Update those fields only when supporting information is available.

No new dependencies were added for the redesign.
