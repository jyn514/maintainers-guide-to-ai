# Skill Mappings

## Chapter content

| Skill | Chapters | Contribution |
| --- | --- | --- |
| `double-check` | Verifying the Result; Finishing and Handoff | Requirement-to-evidence completion audit |
| `architecture-design` | Comprehensible Architecture | Responsibilities, boundaries, and maintenance gain versus churn |
| `cleanup-triage` | Choosing Work; Project Fit; Change Governance | Evidence thresholds and stopping rules for speculative work |
| `boundary-declaration` | Specifying the Outcome; Capability Security | Ownership, effects, representation, lifecycle, and API boundaries |
| `second-user` | The Reviewable Patch; Comprehensible Architecture | Evidence required before introducing reusable machinery |
| `dependency-review` | Project Fit; Change Governance | Security, compatibility, upgrade, and abandonment costs |
| `opportunity-scan` | Choosing Work | Project-wide opportunity discovery without recency bias |
| `pain-axis` | Choosing Work | Historical evidence of recurring maintenance pain |
| `ratchet` | Verifying the Result; Mechanical Governance | Converting demonstrated failures into durable checks |
| `commit-quality` | Contribution Ownership | Decision-relevant change records for reviewers and maintainers |

## Writing workflow

| Skill | Use while writing |
| --- | --- |
| `technical-docs` | Choose explanation, how-to, tutorial, or reference form from the reader’s need |
| `reorganize-docs` | Maintain chapter ownership, navigation, progression, and canonical homes for repeated concepts |
| `tighten-docs` | Remove duplication and improve density without deleting rationale or failure cases |
| `double-check` | Audit a draft against its outline, examples, claims, and `CONTRIBUTING.md` requirements |
| `design-deliberation` | Resolve genuine structural or argumentative forks without prematurely collapsing alternatives |
| `second-user` | Challenge frameworks, taxonomies, and terminology that have only one convenient example |
| `ratchet` | Turn repeated editorial failures into review checks or repository automation |
| `commit-quality` | Preserve the reason for structural and editorial decisions in history |

## Suggested chapter cycle

1. Select the chapter’s reader question with `technical-docs`.
2. Use the mapped content skills as research lenses, not authorities.
3. Draft in the form best suited to the material.
4. Apply `second-user` to new abstractions or taxonomies.
5. Run `double-check` against the outline and `CONTRIBUTING.md`.
6. Apply `tighten-docs` after the argument and examples are complete.
7. Use `reorganize-docs` only when the draft exposes a book-level structural problem.
8. Record durable editorial decisions with `commit-quality`.
