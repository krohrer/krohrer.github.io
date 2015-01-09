---
layout: page
title: "about"
date: 2015-01-09 22:11
comments: true
sharing: true
footer: true
---

#  About Me


I am a Software-Engineer with a knack for closures, algebraic data-types, pattern-matching, static typing, and a good module system. I use mostly OCaml for my personal project nowadays, because other languages are a little too verbose for my taste. Although lately, I have found that sometimes Objective-C or C (sometimes even C++) is still the right tool for the job.

_I am a Swiss citizen currently located in Zürich and **available for hire**. <a href="&#109;&#097;&#105;&#108;&#116;&#111;:&#107;&#097;&#115;&#112;&#097;&#114;&#046;&#114;&#111;&#104;&#114;&#101;&#114;&#064;&#103;&#109;&#097;&#105;&#108;&#046;&#099;&#111;&#109;">Contact me</a> or download the [English version of my CV][cv-download]._

## Projects

I have a few projects I am working on during my spare time. All of them are available on GitHub, but apart from [aisss06] and [caml-inspect] none of them are quite ready yet for public consumption.

* **[AISSS06]** - A semester project I did during my years at ETH Zürich for the "Advanced Image Syntheis" course. In my youth, I dabbled in designing levels for Doom and Quake (when I was not just playing the games). However, none of my levels ever made it to fruition, but the idea that I should be able to generate the geometry using code rather than by hand stuck.

* **[Caml-Inspect]** - Having worked with OCaml for a while and being somewhat baffled by the limitation of integers to _(N-1)_ bits on _N_-bit platforms, I became curious about how the OCaml runtime represents values internally. So I wrote this small library to dump the object graph as either S-expressions (using the pretty-printing facilities provided by the `Format` module) or as [Graphviz] _.dot_ files.

* **[Caml-Aesq]** - A text formatting library for ansi terminals. Supports text attributes, justification and alignment, multiple columns and indentations/margins. This library has been on ice for quite some time, although I still plan on adding hyphenation and maybe a Markdown parser as well.

* **[OCaml-Zimt]** - Annoyed by the fact that writing C bindings for OCaml is a tedious undertaking, I decided to write an foreign-function interface generator for OCaml. Currently, the project contains an abstract syntax tree for C and a corresponding pretty printer. There is also the basic definitions of the Zimt language, an embedded DSL. The Zimt language is a somewhat simplified version of C, based on the idea that it should be easy to manipulate fragments of Zimt code using OCaml. This project is my playground for all the new and fancy features in OCaml like GADTs and first class modules.


## Personal

In my spare time I cruise around Zürich on my longboard and take photos of structures I find intriguing. On rainy weekends I very much enjoy having a few friends over for dinner and a round of boardgames.

I also have a [blog], although I rarely update it.

[aisss06]: http://krohrer.github.com/aisss06
[graphviz]: http://graphviz.org
[caml-inspect]: http://krohrer.github.com/caml-inspect/
[caml-aesq]: http://github.com/krohrer/caml-aesq/
[ocaml-zimt]: http://github.com/krohrer/ocaml-zimt
[blog]: http://lambdamuesli.blogspot.com
[cv-download]: downloads/CV-KasparRohrer.pdf