# Style Guides

This directory contains guide on how to format your code and the style
conventions that we use for different languages.

Many of them will be adaptations for other people's works. Make sure
to give credit.

Apart from the general style guidelines below we also have a bunch of
per-language and per-framework style guides for:

- [JavaScript](javascript)


## General Style Guide

Keeping your codebase clean is very important. By clean we mean free of unused functions,
old image files or documentation. A good read the book Clean Code that we recommend to all
employees. While it can seem a bit tedious to read, it give a lot of very good advice that
everyone should follow.

Apart keeping it clean, a good codebase will also seem like a single person wrote it.
That means it is important to agree on how to program, and even better enforce that style
with an automated style checker, like e.g. CheckStyle for Java, and check for code smells
with a linter where possible, e.g. FindBugs for Java or Eastwood for Clojure.


### Formatting

- Keep your lines below 120 or 80 depending on the language.
- Use Unix `LF` line endings.
- Don't vertically align arguments or map values.
- Use one or two spaces between functions and methods. Keep it consistent.
- Don't put spaces between arguments and parenthesis, i.e. between `(`, `[` and arguments and `)`, `]`.
- Use spaces between operators and their operands, e.g. Bad: `1+1=2`, Good: `1 + 1 = 2`.
- Use 2 spaces for indentation, not 4, and not tabs.
- Keep the style of legacy project, don't enforce your own without good reason.


### Naming

- Avoid abbreviations as they are easily misunderstood.
- Prefer naming classes and objects after their function rather than their pattern.
  (CachedAccount vs. AccountDecoration)


### Comments

Avoid inline comments, keep them on their own line.

Every time you write something (or encounter something) in a codebase where the intend or logic
is not immediately obvious it merits a descriptive comment.

Apart from descriptive comments, we use a convention for comment that call for action.


#### Task Comments

- __TODO__: A comment about something that would be nice, but probably won't happen.

- __FIXME__: Something that MUST be fixed before the code can go into production.

- __HACK__: A workaround, usually for something framework specific.
  Should be refactored during a Tech Debt sprint if possible. Must always be well motivated.
  You can end a HACK with END_OF_HACK to let others know the extend what you consider a hack.

- __STYLE__: Used for code review, to let the author know that the style is no in line with the style guide.
