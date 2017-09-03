---
layout: post
title: "Algo #4: Merge Sort"
excerpt: "Merge Sort works by splitting the data continuously, and sorting only two terms at a time. It has O(n log(n)) time complexity."
image: https://cdn.pixabay.com/photo/2012/04/24/11/21/merging-39400_960_720.png
tags: 
  - 100 algorithms
  - python
comments: true
---

# Merge Sort
My quest for sorting algorithms has introduced me to an interesting algorithm, Merge Sort. This one actually works better than [other sorting algorithms](https://rhasnainanwar.github.io//tags#100 algorithms) (discussed so far). Someone really gave it some thought, that is obvious from the working of this algorithm. Despite appearing more complicated, Merge Sort has average time performance of `O( n log(n) )`.

## Idea
Unlike those we have seen so far, this one doesn't require iteration over all the values followed by a series of comparisons and swaps. Merge Sort divides a sorting problem into small sorting problems and then deals with them one-by-one. As all these smaller problems are sorting problems, we can have them solved by following steps over and again. Here, _recursion_ comes in handy.

## Working
