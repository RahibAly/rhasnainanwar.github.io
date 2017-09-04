---
layout: post
title: "Algo #5: Quicksort"
excerpt: "Quicksort, also known as Partition Exchange Sort, is a fast sorting algorithm similar to Merge Sort. It has O(n log(n)) time complexity."
image: https://68.media.tumblr.com/9f04603a723f69c06eb8cd2314082b39/tumblr_ojbee5qM381w0dccho1_1280.gif
tags: 
  - 100 algorithms
  - python
comments: true
---

# Quicksort
We have seen in the [previous post](/merge-sort/ "Merge Sort") that we can divide a problem into smaller similar ones, in order to avoid lengthy and confusing code. Quicksort adopts a similar approach. Although it has same performance as Merge Sort, it is very easy to implement. <br />
Despite being so simple, Quicksort has average time performance of `O( n log(n) )`.

## Working
Quicksort uses _recursion_ to repeatedly sort subsets of the original data list. Quicksort, first, chooses a _key_ or a _pivot_ value. Then, it compares all the values with the key, and decide which values will go to the right and which to the left. The values smaller than the key are placed no the right and other no left half. As the _left_ and _right_ groups are made up in the order they are fed into the algorithm, they are not sorted. The algorithm then goes about sorting the left and the right group, this requires a recursive call to Quicksort. This goes on until there's one value left in each group. After that, the `right - key - left` are combined while moving up the hierarchy of recursive calls.

Key
: The key or pivot is selected using [Lomuto Partition scheme](https://en.wikipedia.org/wiki/Quicksort#Lomuto_partition_scheme) in which the last element is chosen as pivot. <br />
However, I've decided to consider the mid term as pivot, as it is easier to understand.<br />

The following animation is using [Hoare Partition scheme](https://en.wikipedia.org/wiki/Quicksort#Hoare_partition_scheme), in which a pair of values is used to sort the list.
{% capture fig_img %}
![Quicksort Animation](https://68.media.tumblr.com/9f04603a723f69c06eb8cd2314082b39/tumblr_ojbee5qM381w0dccho1_1280.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual demonstration of Quicksort.</figcaption>
</figure>

## Code
The implement of Quicksort is pretty straightforward and easy to understand. There's point to note that `equal` is a list because the key may be repeated multiple times in given data.
```python
def quick_sort( values ):
    n = len( values ) #s ize
    
    if n is 1 or not values: # c'mon, who sorts no or one value!
        return values
    pivot = values[ n//2 ] # choosing middle one as true pivot
    right = []
    left = []
    equal = [] # handy for list appending
    
    for i in values:
        if i is pivot:
            equal.append(i)
        elif i > pivot:
            right.append(i)
        elif i < pivot:
            left.append(i)
    '''recursive call sorts the left and right groups. This goes on and on,
       and the groups get smaller down the hierarchy.
       Recursion automatically sorts the group without having to compare
       each value with the rest.'''
    return quick_sort(left) + equal + quick_sort(right) 
```
See the result in [this IPython Notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_05_-_Quick_Sort.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new) OR comment below.</small>