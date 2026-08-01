# CentralStatz Lab project ingestion

## Purpose

The ingestion workflow turns a repository URL, local directory, live site, document, notes, images, or direct description into a cautious first-pass Lab project proposal or implementation. Repository skills live in `.agent/skills/` and are used in this sequence:

1. `lab-project-intake`
2. `lab-project-analysis`
3. `lab-project-content`
4. `lab-project-visual`
5. `lab-project-integration`

Invoke the full workflow with:

```text
Use the Lab project-ingestion skills to add or evaluate this project.

Source:
<URL, local path, files, or description>

Mode:
dry-run | apply

Additional context:
<ownership, privacy, preferred emphasis, visual, or participation notes>
```

Supported sources may be combined. The agent asks follow-up questions only when missing context materially changes accuracy, ownership, privacy, or permission to publish.

## Analytical boundary

Ingestion should identify not only what implementation can be accelerated, but whether lower implementation cost allows the project to consider a meaningfully different analytical form. Use the existing `central_question`, `current_hypothesis`, reasoning narrative, and limitations to explain that distinction when it is supported; a separate schema field is not required.

Do not imply that every project needs more machinery. A simple method remains preferable when it best matches the question, evidence, and decision. Describe alternative formulations, simulation, interactivity, or dynamic systems only when source evidence makes them relevant, and present prototypes as ways to compare and test structures rather than proof that a more elaborate structure is better.

## Modes

### Dry-run

Analyze without modifying the website. Return proposed metadata/content, stage/status rationale, visual recommendation, evidence classifications, missing information, publication risks, and intended files.

Default to dry-run when ownership or attribution is ambiguous, sensitive information may be present, public status is unclear, or an existing project would be substantially rewritten.

### Apply

Create or update the page and assets, validate the schema, render Quarto, inspect the homepage card/detail route, and report exactly what was supported, inferred, omitted, or left provisional. A clear request to add the project authorizes apply mode when no publication risk remains.

## Evidence classification

- **Supported fact:** directly evidenced by supplied material; record its source.
- **Reasonable inference:** likely but unstated; record rationale and confidence, and qualify or confirm before publication when consequential.
- **Unknown:** insufficient evidence; omit the claim or ask Alex.
- **Private or unsuitable for publication:** discovered but excluded; report only its category, never its value.

Do not copy credentials, PHI, client data, private names, internal URLs, local paths, unpublished collaborator details, sensitive screenshots, or confidential logic into source or generated output.

## Project discovery and storage

Each project is `projects/<slug>/index.qmd`. The homepage listing in `index.qmd` discovers `projects/*/index.qmd`; `_templates/project-card.ejs.md` renders its card. A separate registration step is unnecessary.

Keep project-specific screenshots and generated visuals in the project directory when practical. Existing shared historical assets may be referenced relatively. Use a 16:9 landscape preview around 1600×900. Cards use cover cropping, so keep meaningful content near the center. Every image requires accurate alt text.

## Metadata schema

Required homepage-card fields:

| Field | Meaning |
|---|---|
| `title` | Public project name |
| `description` | One-sentence card summary |
| `category` | Short analytical domain/type |
| `status` | Current activity label |
| `stage` | Fixed development stage |
| `order` | Homepage sort position |
| `central_question` | Question the project is testing |
| `current_state` | What demonstrably exists now |
| `latest_update` | Latest meaningful, evidenced development |
| `next_step` | Next experiment or milestone, not a promise |
| `limitations` | Material uncertainty or boundary |
| `looking_for` | Useful participation, or `None currently` |

Required when an image is used:

| Field | Meaning |
|---|---|
| `image` | Path relative to the project source |
| `preview_alt` | Literal, meaningful description |

Recommended provenance fields for new projects:

| Field | Values/purpose |
|---|---|
| `ownership` | Supported ownership/attribution statement |
| `source_type` | `repository`, `local-directory`, `website`, `live-app`, `document`, `description`, `mixed` |
| `visual_type` | `screenshot`, `project-output`, `source-diagram`, `generated-concept`, `placeholder` |
| `visual_is_concept` | Boolean; true only when not a real working artifact/output |
| `visibility` | `public`, `private-approved-summary`, `internal`, `unknown` |

Optional fields include `author`, `date`, `date-modified`, `featured`, `current_hypothesis`, `tags`, `live_url`, `repository_url`, `project_url`, `started_at`, `updated_at`, and `collaborators`. Add verified public links only. YAML may use `description`/`image`; conceptual planning documents may call these summary/preview image, but source pages must use the real names.

## Stages and statuses

Stages are exact, ordered values:

- `Question` — motivating problem and hypothesis are being articulated.
- `Concept` — a framework, design, or analytical approach exists.
- `Prototype` — a working artifact or interactive representation exists.
- `Validation` — assumptions, behavior, usability, or performance are being tested.
- `Pilot` — evidenced limited real-world use.
- `Production` — evidenced active deployment and maintenance for intended users.

Allowed statuses:

- `Exploring`
- `Active Development`
- `Prototype Available`
- `Testing`
- `Seeking Feedback`
- `Pilot Ready`
- `Maintained`
- `Paused`
- `Archived`

Status capitalization is normalized by the validator. Never use percent complete. Never infer Pilot or Production from a demo, deployment configuration, code volume, or polished interface.

## Visual handling

Prefer real screenshots and outputs. Record visual provenance in front matter. A generated concept must be clearly labeled when it could be mistaken for working software and must not imply nonexistent functionality.

When generation is available, write a brief, generate and inspect the image, optimize it, save it in the project directory, and add alt text. When unavailable, copy `.agent/skills/lab-project-visual/assets/visual-brief-template.md` to `projects/<slug>/visual-brief.md`, complete the ready-to-use prompt, and use a restrained placeholder or omit `image`. Replacing it later should require only a new file and `image` path.

## Manual addition and updates

Create a scaffold:

```sh
scripts/new-lab-project project-slug "Project Title"
```

Preview the target without writing with `scripts/new-lab-project --dry-run project-slug "Project Title"`.

The scaffold is intentionally a draft with explicit placeholders, not factual claims. Complete all required fields, set `draft: false`, add supported notebook content, then validate:

```sh
scripts/validate-lab-projects
quarto render
git diff --check
```

Run utility success and failure fixtures with `scripts/test-lab-project-tools`.

To update status/stage, edit the page front matter and its visible project-state copy together. Preserve existing human prose unless a rewrite is requested.

## Worked dry-run example

This fictional example is not a CentralStatz project:

```text
Use the Lab project-ingestion skills.

Source:
/path/to/example-water-quality-notebook

Mode:
dry-run

Additional context:
This is my exploratory public repository. It produces charts but has no interface. Recommend a real output as the preview and identify anything I should confirm before publishing.
```

A good response inspects the repository, classifies claims, likely proposes `Concept` or `Prototype` only if the artifact supports it, recommends a genuine chart before generating art, omits unsupported adoption/performance claims, and lists the files it would create without writing them.

## Existing-project demonstration

`docs/fixtures/readmissions-explorer-dry-run.md` records a safe dry-run evaluation of the existing Hospital Readmissions Explorer. It demonstrates schema reproduction and evidence classification without changing public meaning.
