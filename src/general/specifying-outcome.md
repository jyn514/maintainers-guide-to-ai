# Specifications as design work

- A specification settles decisions about the desired outcome; it is not just a more detailed request to generate code.
- State the problem, intended users, observable behavior, and completion criteria. Use the [quality priorities](../prologue/quality.md) to decide which failures matter.
- Declare ownership, protected boundaries, invariants, and non-goals. Distinguish requirements from implementation choices the agent may explore.
- Example to develop: “retry failed requests” leaves open which failures qualify, when to stop, and whether repeating an operation duplicates its effects. Users pay for a plausible implementation that chooses wrong.
  - Contrast with specifying eligible operations, a retry limit, terminal behavior, and tests that detect duplicate effects before selecting an implementation.
- Let an agent surface ambiguities and alternatives, but retain the decisions about acceptable behavior and tradeoffs. An unanswered question is not permission to invent a requirement.
- Practice: pair each important requirement with an example or check that could reject an incorrect implementation. Include failure cases and behavior that must remain unchanged.
- Revise the specification when investigation reveals a mistaken assumption; do not quietly redefine success to match generated output.
- [Verification](verification.md) owns evaluating the resulting evidence. This chapter owns deciding what the evidence must establish.
