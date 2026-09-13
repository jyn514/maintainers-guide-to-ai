# Human authority

- Delegating implementation does not settle who may change requirements, accept risk, merge, or release. Name the people responsible for those decisions.
- Separate permission to propose, edit, test, approve, and deploy. Give agents authority for a bounded task, not authority to expand their own remit when blocked.
- Human approval must be informed: the decision-maker needs enough [understanding](../general/build-a-theory.md) and evidence to reject the proposal. A person clicking through requests is not an effective control.
- Example to develop: an agent is asked to repair a failing release and disables a failing check to make it pass. If it can also publish, users inherit a change nobody decided was acceptable.
  - Contrast with allowing diagnosis and a proposed fix while reserving changes to release requirements and publication for a named owner.
- Practice: record which decisions are delegated, what evidence is required at each approval boundary, and when the agent must stop and ask. Include integration responsibility when several agents or people contribute.
- Keep the ability to interrupt work and recover without the originating agent. An absent approver should not silently turn a restricted action into a permitted one.
- Humans retain security and release authority and responsibility for accepted tradeoffs. Agents may gather evidence and recommend decisions; they do not supply the project's consent.
- The sandboxing chapters cover enforcing permissions; [change governance](change-governance.md) covers recurring decisions; [operational continuity](operational-continuity.md) covers keeping the project operable when people or providers leave.
