+++
title = "Rebooting Cauliflambda"
description = "I talk about what I've been up to in the last months (coding-wise) and how I want to shift my focus back to my lambda calculus interpreter."
+++

In the last months I put a lot of work into improving the situation around automatic
adaptation to dark/light mode in terminal apps[^dark-light].
I'm at a point where I either have to [wait for my PRs to get merged][bat-pr] or discuss and coordinate
with people on the [color change reporting][reports] front.

Additionally, while I'm really happy with the results so far, working on this is not a passion project for me but
rather a «I need this problem fixed and nobody else has bothered to do it yet».
That said I think it's time to re-start an old passion project of mine: [Cauliflambda][cauliflambda]

## What?

Cauliflambda is an attempt at implementing a friendly, embeddable interpreter for lambda calculus.
My broad goals for this project are:
* **Embeddability**: It should be easy to use as a library and inject custom definitions, customize timeouts, toggle «language features» off.
* **Helpful**: Errors should point to the source code and provide suggestions.
* **Transparent**: The interpreter should explain each step when evaluating your program.

## Why?
This project is first and foremost a playground for myself to play around with
parsing, analysis (lints) and possibly other fun concepts.

I also like lambda calculus to toy around with concepts that I know
from higher-level languages, such as an [Optional][lc-maybe] value.

## What's next?

My first attempt at a reducer/evaluator was based on namefree expressions where
all names are replaced [de Bruijn indexes](https://en.wikipedia.org/wiki/De_Bruijn_index).
Unsurprisingly, this was really bad for debuggability and so I decided to scrap the idea.

I don't recall what the state of the new implementation is,
but it might make sense to scrap it yet again and start with separate data structures–currently the parser and the evaluator share
their data structure.

Let's see how it goes :)

[^dark-light]: See [Tau's Terminal Auto Dark/Light Mode Agenda](https://github.com/bash/terminal-dark-light-agenda)

[bat-pr]: https://github.com/sharkdp/bat/pull/2896
[reports]: https://github.com/bash/terminal-unsolicited-reports
[cauliflambda]: https://github.com/bash/cauliflambda/
[lc-maybe]: https://tau.garden/blog/lc-maybe/
