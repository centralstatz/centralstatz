# CentralStatz website agent guide

## Identity and architecture

CentralStatz Statistical & Data Sciences LLC is one cohesive website with two complementary purposes:

- `/` presents advisory, analytical leadership, systems design, and implementation work for teams and organizations.
- `/lab/` presents CentralStatz Lab, a public space for rigorously reasoned frameworks, methods, experiments, and prototypes.

The Lab is not a separate company or brand, and the root site is not a prototype gallery. Preserve the CentralStatz logo, legal identity, charcoal/gold/blue palette, and “Structure Before Sophistication” philosophy.

The site is built with Quarto. Global configuration and navigation are in `_quarto.yml`; the advisory homepage is `index.qmd`; the Lab home is `lab/index.qmd`; Lab projects live at `lab/projects/<slug>/index.qmd`; their cards use `_templates/project-card.ejs.md`; shared styling is in `styles.scss`; tracked output is `_site/`.

## Content boundaries

Keep root business content commercially clear and advisory-oriented. It should explain what CentralStatz helps organizations do, what problems it addresses, how it works, why its approach differs, and how to start a conversation. Preserve conversation-first engagement, healthcare grounding, reproducibility, defensible metrics, maintainable systems, and implementation where appropriate.

Keep deeper experimental language, project stages, statuses, limitations, latest updates, and requested feedback within the Lab. Do not apply Lab project metadata or unfinished-work metaphors indiscriminately to services. Client work is not experimental by default, and confidential work must never be presented as Lab content.

Every Lab project should communicate its motivating problem, reason to exist, current hypothesis, tangible artifact, evidence and uncertainty, honest stage/status, and next useful test. A prototype or visual is evidence of an artifact, not proof that its reasoning is correct or its work is complete.

Rapid implementation can expand the analytical forms worth considering, not merely accelerate a predetermined solution. Added capability does not make complexity inherently better; let the problem determine whether the right artifact is simple or elaborate.

## Accuracy and safety

Inspect source material before writing. Distinguish supported facts, reasonable inferences, unknowns, and private or unsuitable material. Do not invent maturity, adoption, validation, collaborators, performance, ownership, deployment, pilots, or production readiness.

Never publish credentials, environment variables, local paths, internal URLs, PHI, proprietary client data, confidential logic, private organization or collaborator names, sensitive screenshots, or internal issues. Preserve licenses, attribution, collaboration context, and ownership boundaries.

## Design and accessibility

Use the Lab-developed design system as the shared visual foundation: typography, navigation, footer, widths, spacing, buttons, cards, headings, backgrounds, forms, focus states, breakpoints, and reduced-motion behavior. The Lab may remain distinct through its workbench and project components, but it must feel part of the same CentralStatz identity.

Avoid duplicating tokens, breakpoints, navigation scripts, or large stylesheets. Shared-style changes must be checked across the root homepage, Lab homepage, and a Lab project page. Preserve semantic headings, meaningful alt text, keyboard access, visible focus, sufficient contrast, accessible dialogs, form labels, responsive navigation, and status information that is not color-only.

For Lab visuals, prefer real interfaces, real outputs, and real diagrams before generated concepts. Generated visuals must be evidence-grounded, clearly conceptual, minimally labeled, and recorded with `visual_type` and `visual_is_concept`.

## Lab ingestion and validation

Use the Lab skills in `.agent/skills/` in this order: intake, analysis, content, visual, integration. Support dry-run and apply modes. Preserve human-authored project text during updates unless a rewrite is requested.

Before handoff:

1. Run `scripts/validate-lab-projects`.
2. Run `scripts/test-lab-project-tools` when ingestion structure or utilities change.
3. Run `quarto render`.
4. Verify `/`, `/lab/`, every `/lab/projects/<slug>/`, case studies, and `/thank-you.html`.
5. Inspect representative root, Lab, and project pages visually at desktop and narrow widths where practical.
6. Check local assets, internal links and anchors, canonical URLs, headings, alt text, form labels, keyboard behavior, focus, and reduced motion.
7. Check rendered files for absolute local paths.
8. Run `git diff --check`.

Do not commit, push, or modify the source branches unless explicitly requested.
