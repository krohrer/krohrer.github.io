---
layout: post
title: "Emulating labeled arguments with default values in C99"
date: 2013-03-27
comments: false
published: false
categories:
 - macro hack
 - ocaml
 - struct initializer
 - labeled arguments
 - c99
 - c
 - default arguments
---

<div class='post'>
Lately, I have come to enjoy programming in C again. The C99 standard actually brings some nice stuff to the table. Amongst them are  designated initializers for structures and unions.<br /><br /><pre style="background-color: #eeeeee; border: 1px dashed #999999; color: black; font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; overflow: auto; padding: 5px;"><code style="color: black; word-wrap: normal;"><br />void print_foo(foo_t *f) {<br />  printf("struct foo {\n");<br />  printf("  .bar = %i\n", f->bar);<br />  printf("  .baz = %i\n", f->baz);<br />  printf("  .grok = %f\n", f->grok);<br />  printf("}\n");<br />}<br />asdfasjdf asdfasjkfljkasf asdfhjasf jasdfas fljasdfksf aslasdflasdlkjfasdjfas asflasdfaslfjl haklasfdlkaskldfasdf kasdfasf sadfjh asjdfghas fasjdfasldgf<br />#define PRINT_FOO(LARGS, ...)   \<br />  do {      \<br />    foo_t args = {    \<br />      .bar = 666, .baz = 666, .grok = 666.f, \<br />      LARGS, __VA_ARGS__};   \<br />    print_foo(&args);    \<br />  } while(0)<br /><br />int main(int argc, const char *argv[]) {<br />  struct foo f = { .bar = 1, .bar = 2 };<br />  PRINT_FOO(.bar = 1, .baz = 2, );<br />  return 0;<br />}<br /></code><br /> </pre></div>
