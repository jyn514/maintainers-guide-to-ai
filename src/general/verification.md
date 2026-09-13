# Verification as feedback loop

- Verification should change what you do next, not merely certify a finished patch. Run focused checks while the implementation is still cheap to revise.
- Derive checks from the [specified outcome](specifying-outcome.md), not only from the implementation. Code and tests can agree with each other while sharing the same mistaken assumption.
- Choose evidence appropriate to the claim: a reproduction for a reported defect, boundary cases for a parser, an exercised workflow for an integration. Explain what each check leaves untested.
- Example to develop: a retry implementation passes a test that expects three attempts, but duplicates a successful write after a lost response. The test confirms the loop, not the required behavior.
  - Contrast with a test that simulates the lost response and checks the externally visible effects, using the contract from the specification.
- Practice: observe the relevant failure before the fix where feasible, check the corrected behavior, then check nearby invariants. Report what actually ran and its results, including blocked checks.
- Ask agents for counterexamples and adversarial cases. Confirm their claims through observable results; another model's agreement is not a substitute for evidence.
- Preserve useful checks as regression coverage. Turn a demonstrated failure into an enduring constraint where practical; [mechanical governance](../ai-maintained/mechanical-governance.md) covers maintaining those constraints across the project.
- You still judge whether the evidence is sufficient for the stakes. A passing suite does not settle untested behavior, usability, or whether the change should exist.
