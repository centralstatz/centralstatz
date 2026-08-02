# CentralStatz website

This repository contains the Quarto source for [CentralStatz Statistical & Data Sciences LLC](https://www.centralstatz.com/).

## Site architecture

The root site presents CentralStatz’s advisory, analytical-leadership, systems-design, and implementation work. Its primary About and contact experiences remain anchored on the homepage.

CentralStatz Lab lives at `/lab/`. It is a complementary space for public analytical frameworks, methods, and prototypes. Lab project sources live at `lab/projects/<slug>/index.qmd` and render to `/lab/projects/<slug>/`.

Both parts use one Quarto configuration, global navigation, footer, and shared `styles.scss`. Shared tokens and components live in that stylesheet; Lab-only components use `lab-` or project-specific classes. Any shared-style change should be checked on the root homepage, Lab homepage, and a project detail page.

Shared company assets such as the logo and portrait live at the repository root. Lab-only visuals should live beside their project in `lab/projects/<slug>/`. Existing case-study assets remain beside their source pages under `case-studies/` and may be referenced by Lab projects when they are the genuine artifact.

## Preview and build

Install Quarto 1.7 or newer, then run:

```sh
quarto preview
```

Create the tracked production output in `_site/` with:

```sh
quarto render
```

The integrated homepage no longer requires the former R/Leaflet map, so the site renders without R packages.

## Lab projects

The Lab homepage listing reads project front matter and uses `_templates/project-card.ejs.md`. To add a project:

1. Run `scripts/new-lab-project project-slug "Project Title"`.
2. Replace all scaffold TODOs with supported content and set `draft: false`.
3. Add a truthful visual and provenance metadata when available.
4. Run `scripts/validate-lab-projects` and `scripts/test-lab-project-tools`.
5. Run `quarto render` and inspect `/lab/` and `/lab/projects/<slug>/`.

Full evidence, privacy, stage, status, visual, and ingestion guidance is in `docs/lab-project-ingestion.md`. Agent skills are under `.agent/skills/` and target the `lab/projects/` structure.

## Routes and checks

Primary routes are `/`, `/lab/`, `/lab/projects/<slug>/`, `/case-studies.html`, and `/thank-you.html`; Services, About, and Contact are root-homepage anchors. After structural changes, confirm generated files exist, inspect internal links and assets, run `git diff --check`, and check that rendered output contains no local filesystem paths.

See `docs/lab-subsite-integration.md` for the branch comparison and integration decisions.
