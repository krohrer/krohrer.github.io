---
layout: post
title: "Bugfix for S-expression dumping"
date: 2010-04-16
comments: false
categories:
 - theory
 - s-expression
 - haskell
 - dumping
 - github
 - practice
 - bugfix
---

{%img center /images/Screen+shot+2010-04-16+at+12.45.56+AM.png %}

I’ve pushed a new version of the code. The code to dump s-expressions
did not handle references correctly, but it should now.

Maybe next time, I should prove the correctness using [Coq]. But then I
would not be writing new code, would I?

Ah, what a dilemma between theoretical exactness and practical
application. I wonder if Haskell will bridge that gap elegantly. We
never really had the time to get aquainted.

[Coq]: http://www.lix.polytechnique.fr/coq/

