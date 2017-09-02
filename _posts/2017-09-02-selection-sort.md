---
layout: post
title: "Algo #3: Selection Sort"
excerpt: "Selection Sort is a simple sorting algorithm which iterates over a subset of list."
image: https://d2lm6fxwu08ot6.cloudfront.net/img-thumbs/960w/IMZP3JUC0G.jpg
tags: 
  - 100 algorithms
  - python
comments: true
---

# Selection Sort
Sorting the data is very important for indexing and [searching](/binary-search-insertion-sort/ "As discussed in previous post"). A lot of sorting algorithms have been developed so far to meet the current needs of speed. One such algorithm that appeared initially for addressing the sorting problem is **Selection Sort**. <br />
Like [Insertion Sort](/binary-search-insertion-sort/#sorting), Selection Sort tends to be very slow. Both have time _Big-O_ of `O(n`<sup>`2`</sup>`)`, where `n` is the number of entries to be sorted. Both of these algorithms require a lot of computation in comparisons, and in swapping. <br />

## Working
Selection Sort works on the principle of _comparing and swapping_ for arranging the elements. Unlike Insertion Sort, which compares adjacent entries, this algorithm _selects_ the smallest or largest values (depending on sorting order) in a subset of the list and moves it to the front of the subset. This shifting is done by swapping the smallest or largest value with that at the front. After one element is placed at the front spot, we can say that this element is `sort`ed. So, this element is _ignored_ for next iteration. In a nutshell, during each iteration the subset is of size `N - n`, where `n` is the number of sorted elements in the list of `N` elements. <br />

{% capture fig_img %}
![Selection Sort Animation](https://68.media.tumblr.com/331e7265003575cb04f06b3f20346e0c/tumblr_oj7gjfhBsr1w0dccho1_500.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual representation of Selection Sort.</figcaption>
</figure>

### Example
In this example, I'll be sorting data in ascending order. For this, I'll select the smallest value and move it to the front of the subset. <br />
Alternatively, one can select the largest value and move it to the **back** of the subset. In this case, the list will be sorted from right. Ultimately, both methods yield the same result. <br />

"|"
: Separates the sorted part (on left) and unsorted part (on right)

Say we have a list of 5 values: `[8, 2, 3, 9, 4]`; `N = 5` <br />
**Step 1:** <br />
n = 0 <br />
Subset = (8, 2, 3, 9, 4) <br />
Smallest = 2 <br />
Front = 8, hence 2 and 8 are swapped <br />
<br />
`[2, | 8, 3, 9, 4]`
<br />

**Step 2:** <br />
n = 1 <br />
Subset = (8, 3, 9, 4) <br />
Smallest = 3 <br />
Front = 8, hence 3 and 8 are swapped <br />
<br />
`[2, 3, | 8, 9, 4]`
<br />

**Step 3:** <br />
n = 2 <br />
Subset = (8, 9, 4) <br />
Smallest = 4 <br />
Front = 8, hence 4 and 8 are swapped <br />
<br />
`[2, 3, 4, | 8, 9]`
<br />

**Step 4:** <br />
n = 3 <br />
Subset = (8, 9) <br />
Smallest = 8 <br />

Front = 8, no swap <br />
<br />
`[2, 3, 4, 8, | 9]`
<br />
n = 4 <br />
Now that only one element is left, we can assume it to be sorted automatically.
<br />
`[2, 3, 4, 8, 9]`
<br />

## Code
This function takes a list of values and `return`s a sorted list.
```python
def select_sort( values ):
    n = len( values ) # no of elements
    index = 0 # location of smallest value
    for i in range( n - 1): # as the last element will already be sorted
        smallest = values[i]
        for j in range(i, n):
            if values[j] < smallest:
                index = j # index of current smallest value
        # move the smallest to the front of subset i.e., swap
        values[index], values[i] = values[i], values[index]
    return values
```
To see the results of this function, open [link](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_03_-_Selection_Sort.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new).</small>