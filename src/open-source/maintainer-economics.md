# Maintainer economics

- A contribution consumes review, triage, and support capacity even when its author produces it cheaply. Apply the [remaining-work accounting](../prologue/burden.md) from the maintainer's side.
- Review time has an opportunity cost: investigating your patch can delay a release, a reported regression, or work the project already prioritized.
- A backlog is not free storage. Duplicate reports, speculative patches, and unanswered review questions leave maintainers with sorting and follow-up work.
- Example to develop: a contributor sends ten generated cleanups without checking project priorities. Maintainers must assess compatibility and explain rejected changes instead of finishing a release.
  - Contrast with asking about one observed problem, checking prior discussion, and submitting a scoped fix with evidence once its usefulness is established.
- Practice: check contribution rules, duplicates, prior attempts, and project priorities before investing in a patch. Ask before broad changes; accept that useful work may still be unwanted or unaffordable now.
- Reduce reconstruction work: provide a concrete reproduction, explain the decision the maintainer needs to make, and resolve questions you can investigate yourself.
- You own follow-through and an honest account of remaining work, not an entitlement to review or acceptance. Maintainers still decide where their attention goes.
- [The reviewable patch](reviewable-patch.md) covers packaging an accepted scope for review; this chapter establishes why scope and project demand come first.
