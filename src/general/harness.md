# What is a harness?

Humans interact with the world through their eyes and ears and hands.
AI interacts with the world through writing text and receiving text back.

A harness is a model's body.
It turns text into actions in the world.
For example, a model might call a tool that runs a bash command, or reads or writes a file, or sends a message to discord.

## What makes a harness good or bad?

A model is a kind of "tabula rasa".
It has background knowledge of the world, and it's shaped by its training and reinforcement-learning to provide helpful and coherent answers [^2],
but by itself it's closer to a Broca's area that knows every language in the world than to a whole brain.

To make a model an "agent", it needs two main things:
- A way to act in the world (tools).
- A way to respond to those actions ("agent loop"). Harnesses react to events and re-prompt the model with the results.

We call this an agent because it can act by itself without a human constantly prompting it to continue.

Most harnesses will have additional features:
- Peripheral awareness ("context management"). Files such as AGENTS.md and SKILL.md tell the agent what to pay attention to before it ever runs a tool.
- Pause and resume ("session persistence"). Most harnesses let you stop, start, branch, and undo conversations with an agent.
- Interaction with the human operator (interruptions, "steering", questions, tool output).
- Mid-term memory ("compaction"). Models have a limited short-term memory ("context-window"), and every so often it needs to be summarized so the model only remembers what's important.
- Physical constraints (sandbox). Sandboxes prevent agents from taking dangerous actions, kinda, sorta. We'll talk more about sandboxes in upcoming chapters. [^1]
- Unconscious reflexes (hooks).
- Delegating to a colleague ("subagent"). These are new agents created and controlled by the "root" agent, rather than directly by a human. The root agent doesn't automatically know what a subagent does except in the reports they exchange with each other.

Some advanced harnesses have even more features:
- Long-term memory ("memory store"). Compaction summaries only last for the current "session" (conversation, roughly); memory stores persist them between sessions.
- Configurability, allowing you to change the harness itself.
- Persistent undo: Claude Code allows you to undo not just the conversation itself, but also the files the agent changed on disk.

[^1]: "flinch reaction" might sound weird if you're already familiar with sandboxes. My reasoning here is that most sandboxes are not actually very effective at preventing agents from doing things they really want to do. See <https://www.frogandtoad.ai/> for more discussion.

[^2]: for more on this, see https://www.anthropic.com/research/persona-selection-model
