# Process engineering

First, let's talk about the options you have available to you.

- Plain old documentation
- Agent-specific documentation
- Skills
- Hooks
- Tools (in the CLI)
- Tools (in the harness)

## Plain old documentation

"Plain old documentation" is exactly what it sounds like.
I generally have a `doc/*.md` layout for my repos, but you can write your docs in any form you choose.
LLMs will read your READMEs, CONTRIBUTING, etc.
You just have to write them!

To make agent-specific docs more effective, your *normal* documentation should be well-organized.
Each file should be narrow and targeted, easy to navigate by section headings, and cover most things a contributor might need to think about.

If you're not sure how to get to that state, you can use jyn's [`reorganize-docs`] skill on your existing docs to have an LLM give you suggestions.

## Agent documentation

"Agent-specific documentation" is files like AGENTS.md:
normal markdown files that are the first thing the agent sees, even before it sees your initial prompt.

Put things that an LLM should always think about in your AGENTS.md.
For example, you could add this:
> Use concise and clear language. Avoid jargon.
If jargon is necessary, define it.

The rest of your AGENTS.md should be almost exclusively *routing*.
LLMs are lazy, and if you have a lot of documentation, it won't read it all (and even if it does, that burns a lot of tokens).
By associating *events* or *tasks* to documentation files, you can have it read documentation "on-demand", exactly when it's necessary for the task.

[`reorganize-docs`]: https://github.com/jyn514/dotfiles/blob/55cd803de686f4edfbc78d9879283a66c2c7d641/skills/reorganize-docs/SKILL.md

## Skills

"Skills" are regular markdown files that have a name and description as YAML frontmatter.
The description (or "trigger") acts similarly to the routing in AGENTS.md:
it tells the LLM when to read the skill file.

Skills should not repeat your normal docs.
Link freely to human-facing docs in your skills,
and if a human would benefit from a bit of info, put it in the documentation instead of a skill.

Instead, they should be a *procedural*, like a [runbook].
Usually they will have checklists, phases, or exact command invocations.
Use them when steps need to be done in a certain order, in an exact way, or if they're useful across projects.
For example, jyn has a [`jj-workflow`] skill teaching agents how to use jj, and a [`simplify`] skill telling them to make code less Like That.
The jj skill is useful across repos, and the simplify skill is so procedural that it would be rude to show to a human, but it's fine for an agent.

## Hooks

A "hook" is a command that runs when an LLM does a certain action.
For example, you can configure `rustfmt` to run whenever an LLM edits a Rust file.
These are useful when some problem you want to catch is mechanically checkable.

## CLI tools

LLMs *love* specialized tools.
They can work with general tools, but the more restricted the interface, the better they do.
The nice thing about using LLMs is you can get them to write their own tools.
Consider getting an LLM to write a linter, then attaching the linter to a hook.

## Harness tools

This is a fancy word for an API.
It's just an API.
The LLM is writing TypeScript (or sometimes JSON, or Python, or ...), calls a function, and the function returns some data to it.

Harness tools can sometimes be useful if whatever it's doing is different from the way you would do things.
For example, an LLM has trouble using a web browser, so it makes sense to give it a specialized tool for searching Google.
In general though, CLI tools are preferable because they're more general and can be used by human contributors, not just LLMs.

[runbook]: https://docs.aws.amazon.com/wellarchitected/latest/framework/ops_ready_to_support_use_runbooks.html
[`jj-workflow`]: https://github.com/jyn514/dotfiles/tree/55cd803de686f4edfbc78d9879283a66c2c7d641/skills/jj-workflow
[`simplify`]: https://codeberg.org/jyn514/paracress/src/commit/d4a3a32a3b0bde2d5937a8251edf27cdbd42ff07/.agents/skills/simplify/SKILL.md
