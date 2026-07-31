# CentralStatz website

CentralStatz Statistical & Data Sciences LLC is a statistical and data science consultancy in Central Wisconsin. This repository contains the [Quarto](https://quarto.org/) source for [centralstatz.com](https://www.centralstatz.com/).

## CentralStatz Lab branch

The `feature/centralstatz-lab` branch is an exploratory redesign that presents CentralStatz as an independent analytical systems lab. It preserves the legal business identity, logo, brand foundation, contact workflow, and “Structure Before Sophistication” philosophy while making active prototypes the center of the experience.

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

## Provisional content

The current repository only substantiates two experiments: a hospital-readmissions exploration interface and an on-demand Google Analytics report. Their maturity, validation, public availability, adoption, and operational use are not documented and are therefore not claimed. Update those fields only when supporting information is available.

No new dependencies were added for the redesign.
