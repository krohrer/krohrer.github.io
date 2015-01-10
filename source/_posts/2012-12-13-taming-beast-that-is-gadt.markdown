---
layout: post
title: "Taming the beast that is GADT  "
date: 2012-12-13
comments: false
categories:
 - ocaml
 - format
 - camlp4
 - gadt
 - c
 - dsl
 - objective-c
---

For the past few weeks I have been trying to write a little embedded
DSL. The goal is to be able to easily generate bindings between OCaml
and C, and maybe Objective-C, too.

So far, I have written a simplified representation of C
[^cil-reference] using normal algebraic datatypes. This will allow me
to have a loosely-typed intermediate representation, which I can then
pretty print. The pretty printer I have implemented using the Format
module from stdlib. It already supports types, expressions and
statements, but no global definitions and declarations, yet.  To print
OCaml code, I will use Format again for a first draft, and switch to
CamlP4, should the need arise. I briefly considered using CamlP4
quotations for the whole project, but that would necessitate
quotations and parsers for each language to bind. Unfortunately, my
parser-fu is not up-to scratch, and the sparse documentation for
CamlP4 is not helping either. [^camlp4-notes] Maybe it is time to dust
of the dragon books?

The EDSL that I am currently working on uses a feature just recently
introduced with OCaml 4.0: [generalized algebraic datatypes][GADT], or
GADT for short. This will allow me to use OCaml's type-inference and
-checking for the FFI description language. So basically, I’m writing
a strongly-typed code generator in OCaml. When run, this generator
will in turn create the necessary OCaml and C code, constituting a
particular OCaml foreign function interface.

One thing I've come to notice when working with GADTs is that it helps
to have as much type annotations as possible in the beginning. Only
later on, when everything is working, can some annotations be
removed. Otherwise, there will be a lot of strange type errors. Which
for a mere software engineer like me are sometimes hard to
understand. With type annotations, the error messages are usually much
clearer.  I've found that recursive functions help a lot, as they are
probably easiest to annotate and allow me to structure the code a
little better. A concrete example is the following bind function:

```ocaml
let rec bind : type s r. (r,s) fn -> s -> r = fun fs f -> 
  match fs with
  | FVoid _ -> f
  | FLambda (t,n,fs') -> let x = XId (t,n) in bind fs' (f x)
```

With mutually recursive functions and additional type informations,
the above example would look like this:

```ocaml
let rec bind :
  type s r. (r,s) fn -> s -> r =
      fun fs f -> 
        match fs with
        | FVoid _ -> bind0 f
        | FLambda (t,n,fs') -> bind1 t n fs' f
and bind0 :
  type a. a x -> a x =
      fun f -> f
and bind1 :
  type a r s. a t -> string -> (r x, s) fn -> (a x -> s) -> r x = 
      fun t n fs f ->
        let x = XId (t,n) in bind fs (f x)
```

With the following types, interested readers should be able to toy
around with the above functions in OCaml (Version 4.0 is required):

```ocaml
(* Type of a value *)
type _ t =
  | TVoid       : unit t
  | TInt        : int t
  | TFun        : ('r,'a) fn                    -> ('r,'a) fn t 
(* Values / expressions *)
and _ x =
  | XInt        : int                           -> int x
  | XId         : 'a t * id                     -> 'a x
  | XAdd        : int x * int x                 -> int x
  | XApp0       : ('r x,'r x) fn x              -> 'r x 
  | XApp1       : ('r,'a x -> 'b) fn x * 'a x   -> ('r,'b) fn x
(* Function signature *)
and (_,_) fn =
  | FVoid       : 'r t                          -> ('r x,'r x) fn
  | FLambda     : 'a t * id * ('r x,'b) fn      -> ('r x,'a x -> 'b) fn
(* Identifier *)
and id = string
```

[^cil-reference]: I am aware of [CIL](https://github.com/cil-project/cil), but it seems to heavyweight for my purposes, and does not support Objective-C. And I view this whole exercise as a learning experience.

[^camlp4-notes]: There is now at least a wiki for [CamlP4](http://brion.inria.fr/gallium/index.php/Camlp4). And Andrei Formiga has a [nice collection](http://andreiformiga.com/blog/?p=99) of links on the subject.

[GADT]: http://caml.inria.fr/pub/docs/manual-ocaml-4.00/manual021.html#toc85
