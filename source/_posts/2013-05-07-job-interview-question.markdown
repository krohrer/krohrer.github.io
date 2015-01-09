<!--
---
layout: post
title: "Job interview question"
date: 2013-05-07
comments: false
published: false
---
-->

So I had a job interview with a trading firm. They posed the following
question:
	
> Given a series of stock prices, what is the best time to buy
	and then sell?

The naive way to find an answer to this problem would be to iterate
over all pairs of possible buying and selling points. However, this
will have a complexity of {O(n*n)}. Which is, to put it mildly,
suboptimal. So naturally, after getting stuck on the suboptimal
solution during the phone interview and being told that there exists a
solution in {O(n)}, I could not let go of this problem.

So let's formulate the problem directly in OCaml:

```ocaml
let _ = _
```

On a side note, I am not a
big fan of phone interviews.</div>
