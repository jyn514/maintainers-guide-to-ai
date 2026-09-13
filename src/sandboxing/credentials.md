# Scoped credentials

In the main sandboxing page, we talk about the [confused deputy problem].
Here, we expand more on distinguishing between you and the LLM acting on your behalf.

Our primary suggestion is to use *scoped credentials*,
as described in [this blog post][fullmakt].

If you are talking to a web service, this is often supported natively.
for example Github will let you [fine-grained personal access tokens][scoped PATs]
to talk to its REST API rather than using a single token that allows any access to your account.

But now you have a follow-up problem:
how do you give the LLM access to that fine-grained token without also removing your ability to run `gh` yourself?
You can give the LLM a separate account, but this is annoying to set up and maintain.
We suggest instead sandboxing the LLM: running it either in a Docker container or in a full virtual machine.
This ensures that the only thing in the LLM is what you've given it access to.

Some providers do not support fine-grained tokens at all.
For example, if you want your LLM to be able to use JJ, it needs write-access to the `.jj` directory so that JJ can snapshot the current working directory.
But that in turn allows the LLM to run `rm -rf .jj`, either intentionally or accidentally.

In this case we suggest *brokers*:
introduce an isolation boundary [^1] between the LLM and the credential.
For example, jyn has set up a [`jj-proxy`] which:

1. Runs the LLM and the broker in separate docker containers
2. Mounts the `.jj` directory read-only for the LLM and read-write for the broker
3. Adds a `jj` wrapper command in the LLM's container which proxies to the broker.
   The broker disallows destructive commands such as `--ignore-working-copy` or `jj abandon`.

This allows the LLM to use `jj` like normal (from its perspective) while not being able to break anything.

[`jj-proxy`]: https://github.com/jyn514/dotfiles/blob/55cd803de686f4edfbc78d9879283a66c2c7d641/tools/jj-proxy/design.typ

## Takeaways

- Use narrow-scoped credentials, preferring read-only tokens whenever possible.
- Use virtual machines or containerization to avoid giving LLMs access to your own wide-scoped tokens.
- If your provider does not support narrow-scoped credentials, use "brokers" across an isolation boundary to limit what the LLM can do with a credential.

[confused deputy problem]: ./index.md#the-confused-deputy-problem
[fullmakt]: https://fullmakt.ai/blog/scoped-credentials-for-ai-agents
[scoped PATs]: https://github.blog/security/application-security/introducing-fine-grained-personal-access-tokens-for-github/

[^1]: usually a network boundary
