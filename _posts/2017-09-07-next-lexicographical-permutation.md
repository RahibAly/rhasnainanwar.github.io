---
layout: post
title: "Algo #7: Next Lexicographical Permutation"
excerpt: "Permutation is an important mathematical principle which gives a way to arrange things. This algorithm finds the next permutation in lexicographical order."
image: https://68.media.tumblr.com/7b49d2d3675028ab07aa9ada10140482/tumblr_omnpkkeJWj1w0dccho1_400.gif
tags: 
  - 100 algorithms
  - python
comments: true
---
# Permutation
In Mathematics,
:  the notion of permutation relates to the act of arranging all the members of a set into some sequence or order, or if the set is already ordered, rearranging (reordering) its elements, a process called **permuting**. <cite>--[Wikipedia](https://en.wikipedia.org/wiki/Permutation){:target="_blank"}</cite>

## Next Permutation
Today, I'm taking a trip downstream to introduce you to the amazing world of Mathematics where all that boring Algebra and whatnot is actually useful. The possible arrangements in a permutation are used in assigning telephone numbers, codes, and other amazing things in telecommunication that I don't know about. The importance of this little method of arranging numbers and alphabets can be realized from the fact that C++ has a function `next_permutation` in its standard library.<br />
So, in this post you'll get to know how to get the next permutation in lexicographic order using a bunch of loops and variables. First, understand the rules:
* In the given sequence, find the longest _decreasing sequence_ (left to right)
* Let the value just before the decreasing sequence be the _pivot_
* Now, swap pivot with the largest value from chosen sequence which is _smaller_ than pivot value
* Invert the chosen sequence while keeping its place and other values unchanged

> If the next permutation is not possible, return false OR the sequences unchanged.

### Example
Consider you have `34521` and you need to find its next permutation. <br />
**Step 1**<br />
Find the longest decreasing sequence: `34**521**`<br />