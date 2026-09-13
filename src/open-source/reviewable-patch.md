# The reviewable patch

- A reviewable patch lets another person assess a claim without reconstructing your investigation. Small line count alone does not make a change easy to review.
- Keep one coherent purpose and include the whole behavior change: implementation, regression coverage, affected documentation, and compatibility considerations. Separate unrelated cleanup.
- Explain the problem, why this approach addresses it, and which constraints shaped the choice. Summarize relevant evidence rather than pasting an agent transcript.
- Example to develop: a two-line parser fix arrives without a failing input or explanation of compatibility. The reviewer has to infer the intended behavior and invent the tests.
  - Contrast with a slightly larger patch containing the failing case, the fix, a neighboring valid case, and a short explanation of behavior that remains unchanged.
- Practice: inspect the final diff yourself; remove unrelated churn, check the claims in the description, and report [verification results](../general/verification.md) with their limits.
- Make unresolved decisions explicit. If the patch is exploratory or incomplete, say so and ask whether the reviewer wants that discussion rather than presenting it as ready to merge.
- You own explaining and revising the submitted work, including generated portions. Do not forward review questions to an agent and relay its answers unchecked.
- [Maintainer economics](maintainer-economics.md) establishes whether the work is worth proposing; [accountability](contribution-ownership.md) covers responsibility beyond the initial submission.
