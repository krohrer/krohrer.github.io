---
layout: post
title: "I'm on Github now"
date: 2010-04-15
comments: false
categories:
 - open source
 - library
 - dumping
 - github
 - caml-inspect
---

It is done. I now have an account on Github and my [first open source
repository][repo0] has just been pushed. Feel free to take it for a spin. And
don’t forget to tell me what you think of it.

Anyway, after downloading and unpacking the library, just follow the
installation instructions in the README file. If you have [findlib]
installed, using the library is as simple as typing

```ocaml
#use “topfind”;;
#require “inspect”;;
```

into your OCaml prompt. I suggest you open the Inspect module as well.

```ocaml
open Inspect
```

For starters, both the Dot and the Sexpr library provide a test_data
function to generate some interesting data to dump.

```ocaml
Sexpr.dump (Sexpr.test_data ());;
Dot.dump (Dot.test_data ());;
```

If you are on a Mac, the Inspect.Dot.dump_osx function should be of
interest. It writes the DOT output to a temporary file, uses Graphviz
to generate the graph, and displays the results using the open
command.

```ocaml
Dot.dump_osx (Dot.test_data());;
```

It goes without saying that you should have Graphviz installed for
this last part to work.

Have fun!

[repo0]: http://github.com/krohrer/caml-inspect/
[findlib]: http://projects.camlcity.org/projects/findlib.html
