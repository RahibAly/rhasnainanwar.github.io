---
layout: post
title: "Sorting Algorithms: Revisited"
excerpt: "Sorting the data is very important for indexing and searching. A lot of sorting algorithms have been developed so far to meet the current needs of speed."
image: ../images/cube-2031511_1280.jpg
tags: 
  - 100 algorithms
  - algorithms
  - python
comments: true
---
# Sorting
In the world full of data, maintaining the data is a one hectic task. To be able to get the meaning out of this data and search it, data needs to be sorted. The problem to maintain the data is hard to tackle and requires serious solution. Algorithms play an important role in solving such problems.<br />
In order to facilitate the students new to Algorithms, I started [100 Algorithms in Python](/100-algorithms){:target="_blank"} series. Till now, I have posted about 6 algorithms out of which **five** are sorting algorithms. This post is about those algorithms, as I will pivot to some other interesting algorithms. The ones I have post in my blog are:
* [Insertion Sort][1]
* [Selection Sort][2]
* [Merge Sort][3]
* [Quick Sort][4]
* [Pigeonhole Sort][5]

[1]: /binary-search-insertion-sort/#sorting
[2]: /selection-sort
[3]: /merge-sort
[4]: /quick-sort
[5]: /pigeonhole-sort

## Which one to use?
**Insertion and Insertion Sort** are pretty straightforward. They iterate over all the items multiple times and moving some items back and forth to get them in order. For this reason, their performance is `O( n`<sup>2</sup>` )`, where `n` is the number of items to sort.<br />
With `O( n log(n) )` complexity, **Merge and Quick Sort** are clearly the winners here. They both are relatively faster than their siblings. This is all about performance, but I still like _Quick Sort_ more. The reason is that it is easier to implement as compared to its competitor, Merge Sort. With recursion, Merge Sort becomes complex to understand.<br />
I believe **Pigeonhole Sort** is an overkill with its tricky time and space complexity. Although it gives a hint how mathematical principles can be used in such a way, a better similar solution is still at large. <br />
<br />
<small>Featured Image: [Pixabay](https://pixabay.com){:target="_blank"}</small>
