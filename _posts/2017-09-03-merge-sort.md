---
layout: post
title: "Algo #4: Merge Sort"
excerpt: "Merge Sort works by splitting the data continuously, and sorting only two terms at a time. It has O(n log(n)) time complexity."
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
Merge Sort goes by making groups of data, and then splitting those groups into further groups half their size. This goes on until the number of groups match the number of origin data elements, each group consisting of one distinct value. <br />
Once we hit the ground, merge sort start sorting each group, and combining groups such that they form a sorted group. This is done be comparing the _heads_ of both groups which are to be combined, and deciding which group must be placed at the front. Just like the splitting part, this goes on until there is only one group left, which is in fact our list of sorted data. <br />

{% capture fig_img %}
![Merge Sort Animation](https://68.media.tumblr.com/7229e988edf3eb8ce5c45d8aa3a2d979/tumblr_oj9l2ypNwL1w0dccho1_1280.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual demonstration of Selection Sort.</figcaption>
</figure>

# Code
Merge Sort algorithm has two parts. One part deals with splitting data and calling on them the second part, sort and merge.<br />
The function given below merges any two given groups by comparing the heads of both groups and merging them by keeping order. <br />

Important!!!
: It should be noted that this function does not actually sort the data, it merges two groups by looking at their heads only. The data is sorted by _recursion_ on this part. The smaller groups are already sorted when they are given for merging, and this goes on. It is better understood by an example given in this [notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_04_-_Merge_Sort.ipynb).

```python
def merge(first, second):
    temp = [] # temporary list to help merging
    
    while( first and second ): #while non-empty, when they are empty it means there is nothing to compare
        if first[0] > second[0]:
            temp.append( second.pop(0) ) # removing and adding to temp
        else:
            temp.append( first.pop(0) ) # removing and adding to temp
    '''when one group is empty, we the copy the other one as is'''
    # copying to temp
    while( first ):
        temp.append( first.pop(0) ) # removing and adding to temp
    while( second ):
        temp.append( second.pop(0) ) # removing and adding to temp
    return temp # return a merged sorted list
```
The `merge` is called from the main function where the data is split into to parts. The splitting is carried out recursively.
```python
def merge_sort( myList ):
    n = len(myList) # size
    
    if n is 1:
        return myList
    
    # splitting from middle
    first = myList[:n//2]
    second = myList[n//2:]
    
    # recursive magic
    first = merge_sort( first )
    second = merge_sort( second )
    
    return merge(first, second)
```
To see the results of this function, open [link](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_04_-_Merge_Sort.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new) OR comment below..</small>