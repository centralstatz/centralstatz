# CentralStatz Lab design audit

The original Lab redesign established the shared charcoal, gold, blue, and neutral visual system now used across the integrated website. Its durable contributions are the navigation and footer treatment, typography, content widths, spacing, buttons, cards, section headings, project metadata patterns, responsive breakpoints, focus states, reduced-motion handling, accessible form/dialog behavior, and Lab ingestion workflow.

The root business site remains the source of truth for advisory positioning, analytical leadership, service substance, healthcare grounding, About content, contact workflow, analytics, canonical domain, legal identity, and existing case studies.

Lab-specific content now lives beneath `/lab/`: its homepage methodology and philosophy, project listing, stage/status semantics, project notebooks, visuals, templates, and ingestion guidance. Ordinary services do not use project stages or provisional-work labels.

The project schema remains sufficient after relocation. `central_question`, `current_hypothesis`, reasoning, limitations, provenance, and participation fields express the project boundary without introducing a new mandatory field. See `lab-subsite-integration.md` for the migration record and route decisions.
