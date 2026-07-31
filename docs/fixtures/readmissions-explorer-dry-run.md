# Dry-run fixture: Hospital Readmissions Explorer

This fixture demonstrates the ingestion workflow against existing repository-supported material. It is analysis documentation, not a new public project.

## Input

- `projects/readmissions-interface/index.qmd`
- `case-studies/llm-powered-app-for-hospital-readmissions/index.qmd`
- Existing feature image and interface GIF
- Mode: dry-run

## Supported facts

- A custom interface artifact exists and is visible in `readmit_app.gif`.
- The project uses Hospital Readmissions Reduction Program data; both source pages state this.
- Existing project notes describe a deployment pipeline and conversational exploration workflow.
- The current public page explicitly disclaims clinical decision support and validation claims.

## Reasonable inferences

- `Prototype` is an appropriate stage because a visible working interface artifact exists; no repository evidence supports Validation, Pilot, or Production.
- `Active Development` is plausible from the existing page’s explicit status, but maintenance recency should be confirmed before future updates.

## Unknowns

- Public live-app availability
- Formal evaluation or validation results
- Real-world adoption, users, pilots, or production deployment
- Current maintenance activity after the recorded March 2026 update

## Private or unsuitable for publication

No sensitive material was needed or reproduced for this fixture. A future source audit must still inspect configuration and screenshots for secrets or health information.

## Proposed schema result

- Title: Hospital Readmissions Explorer
- Category: Healthcare analytics
- Status: Active Development
- Stage: Prototype
- Visual: real interface screenshot/output (`visual_type: screenshot`, `visual_is_concept: false`)
- Central question: retain the existing question about easier exploration without hiding analytical structure
- Next step: retain the existing guardrail/evaluation question
- Limitations: retain the explicit exploratory/not-clinical-support boundary
- Looking for: questions, usability feedback, and healthcare-data perspectives

## Apply decision

No public content change is recommended. Optional provenance metadata could be added during a future evidence review, but the workflow correctly reproduces the existing interpretation without inventing maturity or validation.
