# Sandboxing

Agents are, generally, well-meaning but extremely tunnel-visioned.
Giving them credentials and permissions is dangerous, not because they're malicious, but because they don't know what is and isn't a good idea.

## The confused deputy problem

The post [What Are Capabilities?] introduces the confused-deputy problem like so:

> At heart, the FORTRAN compiler was deputized by two different masters: the customer and the system operators.
To serve the customer, it had been given permission to access the customer’s files.
To serve the operators, it had been given permission to access the accounting file [which recorded usage billing so the customer could be charged].
But it was confused about which master it was serving for which purpose, because it had no way to associate the permissions it had with their intended uses.
It couldn’t specify “use this permission for this file, use that permission for that file”, because the permissions themselves were not distinct things it could wield selectively – the compiler never actually saw or handled them directly.
We call this sort of thing “ambient authority”, because it’s just sitting there in the environment, waiting to be used automatically without regard to intent or context.

We have this problem in spades in modern computing.
For example, when you run `git push --force`, the remote server cannot distinguish between you, a Git GUI acting on your behalf, a confused LLM who messed up which branch is which, and a malicious program that is publishing a worm to NPM.

We can solve this in one of three ways:
1. Distinguish between you and the user agents acting on your behalf.
   For example, give the LLM a separate user account on your computer.
1. Prompt each time you use the credential.
   For example, use the 1password desktop app or macOS' Keychain.
1. Use a capabilities-based model, where programs cannot even access your SSH key unless you as the user explicitly delegate that permission.
   For example, use [Fuschia] on Google Nest Hub [^1].

A true capabilities-based model generally requires redesigning underlying infrastructure and is hard to migrate to incrementally.
We don't discuss it much in this book.

## Alert fatigue

Claude Code used to default to prompting each time an LLM wanted to leave the sandbox.
It recently [changed the default][auto-approve] to having another LLM review the request:

> Data suggests that manual review can become habitual: users approve 97% of permission prompts in Claude Code.
While most prompts are likely for safe, routine commands, an approval rate that high suggests many users are clicking through reflexively rather than reviewing each command.

This is known as [alert fatigue]:
when you get too many alerts, and most alerts are just noise, you start ignoring them.

Therefore, this book discourages alert-based security.

## How secure is secure?

We are used to thinking of security in terms of "patches":
"is your system up-to-date with the latest security fixes?"
As LLMs become more-and-more capable, they increasingly [find security vulnerabilities][A/ 0-days] that are new and have never before been discovered, called "0-days" [^2].
We can no longer assume that running the latest software version is sufficient for your LLM to be sandboxed.
Instead, we have to use defense-in-depth approaches that are [correct-by-construction][illegal-states-unrepresentable].

[What Are Capabilities?]: https://habitat-chronicles.com/2017/05/what-are-capabilities/
[Fuschia]: https://fuchsia.googlesource.com/fuchsia/%2B/main/docs/concepts/kernel/handles.md
[auto-approve]: https://claude.com/blog/auto-mode-default-in-claude-code
[alert fatigue]: https://en.wikipedia.org/wiki/Alarm_fatigue
[A/ 0-days]: https://www.anthropic.com/research/zero-days
[illegal-states-unrepresentable]: https://fsharpforfunandprofit.com/posts/designing-with-types-making-illegal-states-unrepresentable/

## Takeaways

- LLMs should not be trusted not to break anything.
- Repeated approval requests cause alert fatigue.
- Distinguish between an LLM and a human using separate credentials, not approvals.
- Build systems that are correct-by-construction.

[^1]: It might be clear that I had to search pretty hard to find an example where capabilities are really used ...

[^2]: "0-days" means 0 days of time for the software maintainer to respond before it starts being exploited.
