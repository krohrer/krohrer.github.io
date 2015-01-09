---
layout: post
title: "Pretty Printing Monoid"
date: 2013-03-27
comments: false
published: false
---

<div class='post'>
<style type="text/css">.c-code {   background: #E0F0FF;   color:#222222" } </style> While working on the pretty printer (PP) for an OCaml representation of the C language syntax <i>[1]</i>, I realized that pretty printing C types is kind of hard. Especially deeply nested function-pointers and array types. Consider, for example, the following abomination of a declaration <i>[2]</i>:<br /><pre class="c-code">void (** h[2][1])(void*,<br />                  void<br />                    (*)(void*,<br />                        const<br />                        int*));<br /></pre>Not that this given example makes much sense, considering that most sane C programmers would at least use one or more intermediate typedefs to make such a type more readable. But it also nicely illustrates the constructs that a pretty printer has to handle, if it wants to be fully general.  <br /><h4>Footnotes &amp; References</h4><br /><ol><li><a href="http://github.com/krohrer/ocaml-zimt" target="_blank">OCaml-zimt</a>, a OCaml foreign function interface generator for the C language family. Work in progress.</li><li>Plugging this type into <a href="http://cdecl.org/">http://cdecl.org</a> gives <blockquote>declare h as array 2 of array 1 of pointer to pointer to function (pointer to void, pointer to function (pointer to void, pointer to const int) returning void) returning void</blockquote></li></ol></div>
