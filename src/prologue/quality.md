# What makes software high-quality?

- Quality is fitness for an intended use, not how convincing the implementation looks. Identify whose needs count and under what conditions the software must work.
- Correctness is necessary but not sufficient: consider failure behavior, comprehensibility, compatibility, operability, and the cost of changing the system.
- Make tradeoffs explicit. A disposable experiment and a maintained service need different evidence and different investment; neither benefits from accidental complexity.
- Example to develop: a generated importer handles valid files but silently drops malformed records. A demo succeeds while users inherit missing data and operators inherit an investigation.
  - Contrast with explicit rejection, actionable diagnostics, and tests for malformed input. Decide with the intended users whether partial import is acceptable.
- Practice: name the qualities that matter for this change, the unacceptable failures, and how each will be assessed. Include the future maintainer, not just the immediate requester.
- Passing checks establishes only what those checks cover. You still own deciding whether the chosen standard is adequate.
- [Specifications](../general/specifying-outcome.md) turn these priorities into a contract; [verification](../general/verification.md) tests it; [architecture](../ai-maintained/comprehensible-architecture.md) preserves the ability to understand and change the result.
