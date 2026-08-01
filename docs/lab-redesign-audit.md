# CentralStatz Lab redesign audit

## Existing architecture

- Quarto 1.7 website using the Lux Bootstrap theme with custom SCSS.
- A single long-form homepage (`index.qmd`) plus a Quarto-generated case-study listing and two detail pages.
- Global website metadata, navigation, Google Analytics, Open Graph, footer, and canonical site URL live in `_quarto.yml`.
- Source images live beside the pages that use them. `_site/` is the tracked production build.
- The homepage contact form uses Netlify Forms with a honeypot. Other contact routes are `mailto:` links.
- Responsive layout and navigation come primarily from Quarto/Bootstrap, with local responsive SCSS.
- There are no repository-specific agent instructions, automated tests, formatter, or linter. The established validation command is `quarto render`.

## Reusable foundations

- The existing CentralStatz logo and dark charcoal/gold/blue palette.
- The “Structure Before Sophistication” philosophy and supporting language about reproducibility, transparency, and statistical clarity.
- The owner biography, Central Wisconsin location, contact details, analytics configuration, and social links.
- Genuine screenshots for the hospital-readmissions interface and Google Analytics reporting workflow.

## Proposed structure

- A concise lab-oriented hero and navigation.
- Active work as the dominant homepage section, powered by Quarto project-page front matter and a reusable custom listing template.
- Lab process, AI’s bounded role, philosophy, engagement, about, and contact sections.
- A polished project-notebook detail page for the best-supported existing project.

## Project content model

Projects live under `projects/<slug>/index.qmd`. Quarto front matter stores card metadata (status, stage, central question, current state, update, next step, limitations, and participation request); the page body stores the fuller notebook narrative. A custom EJS listing template renders cards without duplicating project content in the homepage.

## Refined Lab philosophy

The approved visual structure now carries a sharper distinction between implementation acceleration and expanded analytical possibility. Faster implementation can shorten familiar work, but its more consequential use is making alternative formulations and system shapes affordable to compare before one becomes costly to replace. This does not create a preference for complexity: the question, evidence, and decision still determine whether a simple method or additional machinery is warranted.

The existing project schema is sufficient. `central_question`, `current_hypothesis`, project reasoning, and limitations can express this boundary without adding a field that every project would be forced to populate.

## Expected changes

- `_quarto.yml`, `index.qmd`, and `styles.scss`
- `projects/` content and metadata
- `_templates/project-card.ejs.md`
- `README.md` and this audit
- rendered `_site/` output

## Constraints

- The repository contains no evidence for public CentralStatz Healthcare Decision Engine or Hockey Flux project claims, so they will not be presented as current lab projects.
- Existing project write-ups are sparse. Unknown validation, adoption, ownership, timeline, and maturity details must remain unstated.
- No new framework or runtime dependency is warranted; Quarto’s native content and listing systems are sufficient.
