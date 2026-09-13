# Building a theory

- Before changing a system, build an explanation of its behavior: where inputs enter, which decisions matter, what state changes, and which constraints the design protects.
- Ask an agent to locate code, trace paths, and propose explanations. Treat its account as a hypothesis until you check it against code, tests, history, or observed behavior.
- Keep observations, hypotheses, and verified conclusions separate. Record the evidence that would disprove your current explanation.
- Example to develop: an agent blames stale output on caching and proposes invalidation. A trace shows that an update never reaches the writer; the cache change would leave the defect and add maintenance work.
  - Contrast with tracing one failing input through the relevant boundaries before selecting a fix.
- Practice: explain the failing path, the intended path, and why the proposed change connects them. Investigate contradictions rather than asking for another patch on the same unsupported premise.
- You need enough understanding to judge the change and its failure modes, not encyclopedic knowledge of the repository. If you cannot explain the relevant behavior, narrow the task or ask for help before presenting a fix.
- Carry established constraints into [the specification](specifying-outcome.md), and use [verification](verification.md) to challenge the explanation rather than merely confirm the patch.
