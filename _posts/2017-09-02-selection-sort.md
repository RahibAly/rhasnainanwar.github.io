---
layout: post
title: "Algo #3: Selection Sort"
excerpt: "Selection Sort is a simple sorting algorithm which iterates over a subset of list."
image: https://68.media.tumblr.com/331e7265003575cb04f06b3f20346e0c/tumblr_oj7gjfhBsr1w0dccho1_500.gif
tags: 
  - 100 algorithms
  - python
comments: true
---

# Selection Sort
Sorting the data is very import for its indexing and [searching](/binary-search-insertion-sort/ "As discussed in previous post"). A lot of sorting algorithms have been developed so far to meet the current needs of speed. One such algorithm that appeared initially for addressing the sorting problem is **Selection Sort**. <br />
Like [Insertion Sort](/binary-search-insertion-sort/#sorting), Selection Sort tends to be very slow. Both have time _Big-O_ of `O(n`<sup>2</sup>`)`, where `n` is the number of entries to be sorted. Both of these algorithms require a lot of computation in comparisons, and in swapping. <br />

## Working
Selection Sort works on the principle of _comparing and swapping_ for arranging the elements. Unlike Insertion Sort, which compares adjacent entries, this algorithm _selects_ the smallest or largest values (depending on sorting order) in a subset of the list and moves it to the front of the list. This shifting is done by swapping that smallest or largest value with that at the front. After one element is placed at the front spot, we can say that this element is `sort`ed. So, this element is _ignored_ for next iteration. In a nutshell, during each iteration the subset is of size `N - n`, where `n` is the number of sorted elements in the list of `N` elements. <br />

{% capture fig_img %}
![Selection Sort Animation](https://68.media.tumblr.com/331e7265003575cb04f06b3f20346e0c/tumblr_oj7gjfhBsr1w0dccho1_500.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual representation of Selection Sort.</figcaption>
</figure>

### Example
"|"
> Separates the sorted part and the yet to be sorted

Say we have a list of 5 values: `[8, 2, 3, 9, 4]`; `N = 5`
**Step 1:** <br />
`n` = 0 <br />
Subset = (8, 2, 3, 9, 4) <br />
Smallest = 2 <br />
`[8, 2, 3, 9, 4]` <br />
     ^
Front = 8, hence 2 and 8 are swapped <br />
<br />
`[2, | 8, 3, 9, 4]`
<br />