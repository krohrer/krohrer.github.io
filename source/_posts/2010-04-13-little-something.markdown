---
layout: post
title: "A little something..."
date: 2010-04-13
comments: false
categories:
 - s-expression
 - repl
 - ocaml
 - graphviz
 - omake
 - ocamlmakefile
 - not c++
 - preview
---

{% img center /images/Screen+shot+2010-04-14+at+12.16.07+AM.png %}

Here is a little preview of what I am working on at the moment. It is
a little library for the beautiful [^ocaml-warts] [OCaml] programming language
that allows one to inspect any OCaml value in the [REPL] by dumping
pretty printed [S-expressions] or producing output for [Graphviz].

Something along the lines of

```ocaml
val dump : ?context:dump_context -> ‘a -> unit
val dot : ?context:dot_context -> ‘a -> unit
```

There will be more.

Oh, and I am trying out the [OCamlMakefile] as a substitute for
[OMake], and I must say I really like it so far. Although OMake has
served me well in the past.

[^ocaml-warts]: Too be fair, she has some warts, especially with regard to her looks (the quirky syntax). Plus, it can be hard to understand the things she throws at you when you do something wrong (the error messages).  After spending some quality time with OCaml, however, I never ever want to go back to the beast that is C++. That was such an abusive relationship. C on the other hand…

[OCaml]: http://caml.inria.fr/ocaml/index.en.html
[REPL]: http://en.wikipedia.org/wiki/Read-eval-print_loop
[S-expressions]: http://en.wikipedia.org/wiki/S-expression
[Graphviz]: http://www.graphviz.org
[OCamlMakefile]: https://github.com/mmottl/ocaml-makefile
[OMake]: http://omake.metaprl.org/index.html

