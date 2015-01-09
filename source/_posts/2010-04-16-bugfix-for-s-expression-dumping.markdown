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

<div class='post'>
<a onblur="try {parent.deselectBloggerImageGracefully();} catch(e) {}" href="http://2.bp.blogspot.com/_TpVt3um4eVw/S8eaX2Txo0I/AAAAAAAAAB0/mQDW9wim9cI/s1600/Screen+shot+2010-04-16+at+12.45.56+AM.png"><img style="display:block; margin:0px auto 10px; text-align:center;cursor:pointer; cursor:hand;width: 264px; height: 400px;" src="http://2.bp.blogspot.com/_TpVt3um4eVw/S8eaX2Txo0I/AAAAAAAAAB0/mQDW9wim9cI/s400/Screen+shot+2010-04-16+at+12.45.56+AM.png" border="0" alt="" id="BLOGGER_PHOTO_ID_5460502807716143938" /></a><br />I've pushed a new version of the code. The code to dump s-expressions did not handle references correctly, but it should now.<div><br /></div><div>Maybe next time, I should prove the correctness using <a href="http://www.lix.polytechnique.fr/coq/">Coq</a>. But then I would not be writing new code, would I?<div><br /></div><div>Ah, what a dilemma between theoretical exactness and practical application. I wonder if Haskell will bridge that gap elegantly. We never really had the time to get aquainted.</div></div></div>
