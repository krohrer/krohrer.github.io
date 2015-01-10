---
layout: post
title: "Pretty Printing Monoid"
date: 2013-03-27
published: false
comments: false
---

While working on the pretty printer (PP) for an OCaml representation
of the C language syntax [^c-syntax], I realized that pretty printing C types
is kind of hard. Especially deeply nested function-pointers and array
types. Consider, for example, the following abomination of a
declaration:

```c
void (** h[2][1])(void*,
                  void
                    (*)(void*,
                        const
                        int*));
```

Plugging this type into http://cdecl.org gives

> declare h as array 2 of array 1 of pointer to pointer to function
> (pointer to void, pointer to function (pointer to void, pointer to
> const int) returning void) returning void


[^c-syntax]: [OCaml-zimt](http://github.com/krohrer/ocaml-zimt), an OCaml foreign function interface generator for the C language family. Work in progress.

