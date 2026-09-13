# The Maintainer's Guide To AI

Hosted online at <https://ai-maintainers.jyn.dev/>.

This book is a project to document how to use AI *well* in ways that are *maintainable* and *preserve human knowledge*.
The primary principle is to offload work from where it's scarce (maintainer attention, human time) to places where it's cheap (burning more tokens).

Many people online have said how AI encourages carelessness, similar to self-driving cars: they're correct just enough of the time that you're tempted not to review their work, but incorrect just often enough that you can't let them do their own thing.
We agree.
Therefore this book is strongly oriented around *process engineering*, not how to be more careful while using AI.

This book and all its chapters are currently **stubs**.
This project is a work in progress.
If you're interested in contributing, please join [our discord](https://discord.gg/kFTsVpbUWA).

## Building

Build the book with `mdbook build`.
View it locally with `mdbook serve --open`.

The Lima-Docker agent sandbox supplies mdBook and Node.js through [`.agents/sandbox/docker-bake.hcl`](.agents/sandbox/docker-bake.hcl).
The version 2 launcher captures the build context and owns image cache keys.
The repository enables host editing;
it needs no project command proxies, nested containers, or Flower R2 access.
