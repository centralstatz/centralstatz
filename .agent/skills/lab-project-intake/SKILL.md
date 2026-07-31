---
name: lab-project-intake
description: Gather the minimum safe, publishable context for adding or evaluating a CentralStatz Lab project from a repository URL, local path, website, live app, document, notes, images, or direct description. Use when beginning a Lab project ingestion or when source ownership, visibility, attribution, or publication scope needs clarification.
---

# Lab project intake

Start with one question when no source was supplied:

> What project should be added to the Lab? Provide a GitHub URL, local path, live app, supporting files, screenshots, or a description.

Record the requested mode: `dry-run` or `apply`. Default to dry-run when ownership, privacy, public status, attribution, or an existing substantial page is unclear.

Accept incomplete context. Do not ask Alex to fill every schema field. Ask follow-ups only when answers materially affect accuracy or publication safety:

- Who owns the work: CentralStatz, Alex, collaborators, another project, an employer, or a client?
- Is the source and its interface public? What must remain private?
- Is there a preferred name or canonical public link?
- Is the work actively maintained?
- Is publication safe and authorized?
- What participation is wanted, if any?
- Should the visual be a genuine screenshot/output or a clearly labeled concept?

Create an intake record containing sources, requested mode, ownership, visibility, publication constraints, preferred framing, desired participation, and unresolved blockers. Never echo secrets or sensitive content into the record.

Then invoke/read `../lab-project-analysis/SKILL.md` and pass the sources plus intake record.
