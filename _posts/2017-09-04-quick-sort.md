---
layout: post
title: "Algo #5: Quicksort"
excerpt: "Quicksort, also known as Partition Exchange Sort, is a fast sorting algorithm similar to Merge Sort. It has O(n log(n)) time complexity."
image: ../images/2000px-Quicksort-diagram.svg.png
tags: 
  - 100 algorithms
  - python
comments: true
---

# Quicksort
We have seen in the [previous post](/merge-sort/ "Merge Sort") that we can divide a problem into smaller similar ones, in order to avoid lengthy and confusing code. Quicksort adopts a similar approach. Although it has same performance as Merge Sort, it is very easy to implement. <br />
Despite being so simple, Quicksort has average time performance of `O( n log(n) )`.

## Working
Quicksort uses _recursion_ 