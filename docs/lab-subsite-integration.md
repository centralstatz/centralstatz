# CentralStatz Lab subsite integration

## Why this was not a direct merge

`main` and `feature/centralstatz-lab` represented different homepage strategies. A direct merge would have treated the Lab-first homepage as a replacement for the production advisory site. The integration instead began from local `main` and selectively adopted understood Lab files and patterns on `feature/integrate-lab-subsite`.

## Branch comparison

| Concern | `main` source of truth | Lab branch source of truth | Integrated result |
|---|---|---|---|
| Positioning | Advisory partner, analytical logic, reproducible systems, implementation | Experimental analytical systems Lab | Advisory root with a restrained Lab introduction |
| Contact | Netlify form, email, thank-you behavior | Improved labels, dialog semantics, focus return, Escape handling | One accessible root contact workflow |
| Production | Domain, analytics ID, case studies, legal identity | Tracked Quarto output without the former Leaflet runtime | Production metadata retained; R/Leaflet homepage dependency removed |
| Design | Earlier Lux customization | Typography, tokens, workbench palette, layouts, cards, responsive and accessibility rules | One shared `styles.scss` and global navigation/footer |
| Lab content | None | Lab method, philosophy, project schema, template, three projects | Relocated beneath `/lab/` |

## Content and route decisions

The root homepage preserves the substance of `main`: analytical partnership, Evaluate/Design/Build, analytical leadership, strengthening logic, building structure, healthcare grounding, About, and conversation-first contact. Its presentation uses the Lab branch’s stronger hierarchy and components.

The Lab homepage moved from the site root to `lab/index.qmd` and was shortened to avoid duplicating the full About and contact experiences. It retains active projects, methodology, the acceleration-versus-expanded-possibility distinction, “less compromise for the wrong reasons,” and Structure Before Sophistication.

Projects moved from `projects/<slug>/` to `lab/projects/<slug>/`, producing:

- `/lab/`
- `/lab/projects/readmissions-interface/`
- `/lab/projects/analytics-reporting/`
- `/lab/projects/flux-estimand/`

No redirects were added because these Lab routes had not been established on the production `main` branch. Existing `/case-studies.html`, case-study detail routes, and `/thank-you.html` remain.

## Shared components and styles

One `_quarto.yml` provides global navigation, metadata, analytics, footer, and the stylesheet. `styles.scss` owns shared tokens, widths, typography, buttons, cards, form/dialog behavior, focus styles, breakpoints, and reduced-motion handling. Business service cards and the root Lab introduction are small additions to the same system; stage tracks and project facts remain Lab-specific.

Shared assets remain at the root. Genuine case-study media remains under `case-studies/`; project-only media remains beside its Lab project. The EJS project-card template remains shared infrastructure but is used by the Lab listing only.

## Known limitations and comparison

About and Contact remain root-homepage anchors rather than standalone pages, matching the established information architecture. The older case studies remain sparse and are preserved rather than editorially expanded without evidence.

To compare the integration with either source without switching branches, use `git diff main...feature/integrate-lab-subsite` and `git diff feature/centralstatz-lab...feature/integrate-lab-subsite`, or inspect individual originals with `git show main:<path>` and `git show feature/centralstatz-lab:<path>`.
