# Making AI do the work

LLMs are very eager to spit out an answer.
Just a like a human, their first answer is often "off-the-top of their head", and not particularly detailed.

By telling them to design, research, and test their work in detail,
we can achieve significantly better results.
A good rule of thumb is this:
forcing an LLM to explain *exactly* how things work helps it catch issues.

We are used to working with other humans who "know what they're doing".
LLMs do not know what they're doing.
In fact, LLMs are probably the *furthest* from "knowing what they're doing" that exists:

![WARNING: THIS MACHINE DOES NOT KNOW THE DIFFERENCE BETWEEN METAL AND FLESH, NOR DOES IT CARE.](../images/this-machine-does-not-know.jpg)

Instead, they ~blindly follow instructions.
They have no memory, do not learn, and every change they make is a drive-by contribution.

This is a curse, but also a blessing.
LLMs can be programmed, just like any other part of the computer.
However, this programming is closer to *process engineering* than to *writing a program*.
The way to get LLMs to do good work is to have really really good contributing documentation, and to a lesser extent to give them good tooling.
As a bonus, this documentation and tooling is generally useful for humans too.

  <!-- - [Agents love consistency]() -->
