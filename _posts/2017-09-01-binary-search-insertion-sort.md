---
layout: post
title: "Algo #2: Binary Search with Insertion Sort"
excerpt: "Binary Search is one of the most popular searching algorithms. It is used with array data structure and has best case time complexity of O(log n)."
image: https://static.pexels.com/photos/210607/pexels-photo-210607.jpeg
tags: 
  - 100 algorithms
  - python
comments: true
---

# Binary Search
In the world of technology and Internet, searching is everywhere. Either you are searching a query on Google or looking for a friend on Facebook, searching is your friend. In order to make this search robust, website and software development companies tend to look for algorithms that can search for something fast. <br />
Binary Search is an important algorithm in this regard. But it is not practically used, as there have been developed much better solutions. Still, it is a good to understand it if one is new to algorithms. Dive into more theoretical details [here](https://en.wikipedia.org/wiki/Binary_search_algorithm){:target="_blank"}.<br />

## Complexity
Binary Search is used on Array (or List in Python) data structure. It has average time complexity of <em>`O(log n)`</em>. Hence, it is better choice over Linear Search which has <em>`O(n)`</em>. <br />

## Working
For it to work correctly, Binary Search needs the data to be `sort`ed. Sorting the data, like searching, is an important problem, but I'll get back to it later. For now, I'll be using the simplest of sorting algorithms, Insertion Sort.

## Code
### Sorting
The first code snippet contains `function` to sort the data. Insertion Sort is used in this function.
```python
def sort( values ):
    n = len(values) # size of list
    for i in range(n - 1):
        for j in range(n - i - 1):
    	```move the smallest digit to the front, one step at a time```
            if values[j] > values[j + 1]:
                # swapping
                temp = values[j]
                values[j] = values[j + 1]
                values[j + 1] = temp
    return values
```
{% capture fig_img %}
![Insertion Sort Animation](https://68.media.tumblr.com/74a17b1a19965b260e039bd37524f48e/tumblr_oj7gnqorRl1w0dccho1_1280.gif)
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual representation of Insertion Sort.</figcaption>
</figure>

### Searching
Once the data is sorted, binary search algorithm starts searching for the required data. The reason for it being faster than Linear Search is that in each step it **discards the half of the data** present at that time. It does so by comparing the required data to the middle of sorted data list. As the data is sorted, the algorithm knows which part of the list is likely to contain the data of interest, so it discards the other half. This goes on and on until the concern element is found or all the data is discarded i.e., search query not found.
```python
def search( values, key ):
    values = sort(values) # sorted array to be fed into binary search
    n = len(values) # size
    start = 0
    end  = n - 1
    middle = (start + end)//2
    while start <= end:
        if values[middle] is key:
            print ("Found!")
            break
        elif values[middle] < key:
            start = middle + 1
        else:
            end = middle - 1
        middle = (start + end)//2
    else: # means there is nothing left to be searched in
        print ("Not found!")
```
Here, `key` is what we are asking Binary Search to look in `values`. `start` and `end` are the indices that show which part of the array is our Region of Interest, if you will.
{% capture fig_img %}
![Binary Search Animation](https://68.media.tumblr.com/edf6d977d2adde26c862048b89c2fec8/tumblr_oj3zgcNTRP1w0dccho1_1280.gif)
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual representation of Binary Search.</figcaption>
</figure>

See the result in [this IPython Notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_02_-_Binary_Search.ipynb).

<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new).</small>