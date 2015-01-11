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

Lately, I have come to enjoy programming in C again. The C99 standard
actually brings some nice stuff to the table. Amongst them are
designated initializers for structures and unions.


```c
void print_foo(foo_t *f) {
  printf("struct foo {\n");
  printf("  .bar = %i\n", f->bar);
  printf("  .baz = %i\n", f->baz);
  printf("  .grok = %f\n", f->grok);
  printf("}\n");
}

#define PRINT_FOO(LARGS, ...)   \
  do {      \
    foo_t args = {    \
      .bar = 666, .baz = 666, .grok = 666.f, \
      LARGS, __VA_ARGS__};   \
    print_foo(&args);    \
  } while(0)

int main(int argc, const char *argv[]) {
  struct foo f = { .bar = 1, .bar = 2 };
  PRINT_FOO(.bar = 1, .baz = 2, );
  return 0;
}
```

