---
name: lab-project-visual
description: Select, prepare, generate, or brief an honest CentralStatz Lab project preview from real screenshots, outputs, diagrams, or evidence-grounded concepts. Use when ingesting a project, choosing card imagery, creating a conceptual visual, documenting visual provenance, or replacing a Lab placeholder.
---

# Lab project visual

Inspect all supplied/source assets before creating anything. Choose in order: real interface screenshot, real project output, real source diagram, generated explanatory diagram, branded temporary concept, restrained placeholder.

For genuine artifacts, select a representative state, remove or mask sensitive data, preserve readability, crop consistently, and write literal alt text. Favor landscape 16:9 around 1600×900; keep important content near the center because cards crop responsively. Do not mock absent features.

For conceptual work, create a diagram only when it explains real relationships better than a screenshot. Use charcoal, restrained gold/blue accents, clean geometry, technical precision, subtle depth, high contrast, and minimal text. Avoid robots, brains, random code, illegible labels, science-fiction decoration, and fake UI controls.

Set provenance metadata:

- `visual_type`: `screenshot`, `project-output`, `source-diagram`, `generated-concept`, or `placeholder`.
- `visual_is_concept`: `true` only for generated concepts/placeholders that are not real outputs.
- `source_type`, `ownership`, and `visibility` as supported.

If generation is available, create a brief first, generate the image, inspect it, save it under `lab/projects/<slug>/`, optimize it, add alt text, and label conceptual status where confusion is possible. Use the image-generation skill/tool when available.

If generation is unavailable, create `lab/projects/<slug>/visual-brief.md` from `assets/visual-brief-template.md`, place a restrained placeholder or omit `image`, and explain the final asset path. Replacement must require only changing `image`.

Never treat a generated visual as evidence that functionality exists. Pass the prepared asset/provenance to `../lab-project-integration/SKILL.md`.
