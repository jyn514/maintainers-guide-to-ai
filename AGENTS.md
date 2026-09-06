# Repository guidance

This repository is an mdBook project. Treat `src/` as the source; `book/` is generated and ignored.

## Before editing

- Read `CONTRIBUTING.md` for the book's audience, chapter contract, navigation rules, style, and review criteria.
- Ensure the skills in this repo are up-to-date.
  If not, and the required skill is not already installed user-wide, ask your operator to install or refresh the repository's pinned writing skills with `scripts/install-skills`.
  Once skills are installed, use the skill appropriate to the task.
- Check `src/SUMMARY.md` before adding, moving, or renaming chapters.
  Each question should have one owner, and the summary should follow the reader's workflow.

## Writing

- Keep guidance durable across tools, models, languages, and repositories.
- Prefer specific actions and evidence. Distinguish observations, hypotheses, model claims, and verified conclusions.
- Show who bears the cost when advice fails, and leave the reader with an applicable practice and retained responsibility.
- Cross-reference recurring concepts instead of reteaching them. Do not use AI disclosure as a substitute for understanding or responsibility.
- Update related navigation and cross-references in the same change.

## Validation

- Build with `mdbook build`.
- Review rendered navigation and changed chapters for broken links, stale claims, duplicated ownership, and unclear responsibility.
- Do not edit generated files under `book/`.
