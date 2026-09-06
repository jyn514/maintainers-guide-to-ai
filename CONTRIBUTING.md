# Contributing

## Purpose

Help readers use AI without transferring investigation, review, or maintenance work to others. Keep advice applicable across tools, models, languages, and repositories.

## Audience

Introduce each part with its audience, assumptions, purpose, and relationship to earlier parts:

- general use: anyone using AI for technical work
- open source contributions: contributors to projects they do not maintain
- AI-authored or AI-maintained projects: people responsible for a project over time

## Chapters

Each chapter must:

- own one clear question
- use a concrete example to show who bears the cost of failure
- leave the reader with an applicable practice
- cross-reference recurring concepts instead of reteaching them

Choose the form that suits the material: explanation, argument, case study, or how-to guide. Use a checklist only for repeatable work.

End-of-part summaries or the final reference may distinguish:

- **AI may do** — safely delegated work
- **You still own** — judgment, verification, and follow-through
- **Do not hand off** — unresolved work others should not have to reconstruct

## Examples

- Include responsible successes and plausible failures.
- Show consequences for reviewers, maintainers, users, and future contributors.
- Distinguish observations, hypotheses, model claims, and verified conclusions.
- Prefer examples that remain useful when tools and models change.
- Remove identifying details unless necessary to understand the case.

## Navigation

- Add a question-based subtitle when a title does not reveal the reader’s task.
- Keep `src/SUMMARY.md` ordered by the reader’s workflow.
- Use end-of-part summaries only to connect chapters.
- Maintain a closing checklist from work selection through long-term ownership.

## Style

- Prefer specific actions and evidence over confidence or exhortation.
- Explain why a rule matters and who pays when it is ignored.
- Distinguish recommendations from requirements.
- State uncertainty and legitimate reasons to abstain.
- Avoid prompt collections, tool tours, and model-specific tricks unless they demonstrate a durable principle.
- Do not treat AI disclosure as a substitute for understanding or responsibility.

## Review

Before submitting a chapter, confirm that:

- its question is not owned by another chapter
- its form suits the reader’s need
- its examples support its claimed costs and practices
- any checklist follows from the chapter rather than introducing policy
- the reader can identify the applicable practice and retained responsibility
- all commands, links, and factual claims have been checked

Build the book with:

```sh
mdbook build
```
