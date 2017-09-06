---
layout: post
title: "Algo #6: Pigeonhole Sort"
excerpt: "This sorting algorithms uses the Pigeonhole Principle to sort items. Its performance on input size and the input range. Hence, not a good choice."
image: https://d2lm6fxwu08ot6.cloudfront.net/img-thumbs/960w/D0E4FVKUA8.jpg
tags: 
  - 100 algorithms
  - python
comments: true
---
# Pigeonhole Sort
As the name implies, this algorithm uses the Pigeonhole Principle to sort items. Although this algorithm is not practically preffered, it strongly demonstrates the wonders of maths. <br />
Pigeonhole Principle
: In mathematics, the pigeonhole principle states that if n items are put into m containers, with n > m, then at least one container must contain more than one item. <cite>[Wikipedia](https://en.wikipedia.org/wiki/Pigeonhole_principle){:target="_blank"}</cite>

The strange thing about Pigeonhole Sort is that its performace not only depends on the input size (normal for all other algorithms), but on the input range as well. This means that Pigeonhole Sort will face a hard time sorting data that is spread over a large range. The average performance with respect to time is `O(n + r)`, where `n` is the input size and `r` is the range of input i.e., `max - min`.

## Working
The algorithms starts with `r + 1` empty holes, and then continues to populate them. Holes are numbered such that the minimum value will be in hole `0` while the largest one will be placed in hole `r`. Each hole is marked with the number of items it contains which shows how many times a specific value is repeated. The algorithm then contines by placing the values in correct order based on their hole number.
### Example
Consider a list: `[1, 6, 9, 5, 4, 6]` <br />
We have: <br />
n = 6 <br />
r = `9 - 1` = 8 <br />
Hence, we have **9 empty holes**, or say holes = `[0, 0, 0, 0, 0, 0, 0, 0, 0]` <br />
<br />
The algorithm will now iterate over all the values and mark the index `x - min` of the list `holes`, where `x` is a value from list and `min` is the smallest value.<br />
For Example
: If x = 6, we'll have 2 at index 5 in holes i.e., `[_, _, _, _, _, 2, _, _, _]`. This means that we have **2 6's** in our list.

After iterating over all the items, we have:<br />
Indices:`[0, 1, 2, 3, 4, 5, 6, 7, 8]` <br />
Holes = `[1, 0, 0, 1, 1, 2, 0, 0, 1]` <br />
Now, Pigeonhole Sort will visit each hole, and copy the values there to another list. This list will now be sorted. <br />
Sorted = `[1, 4, 5, 6, 6, 9]` <br />
**Note**<br />
> As you can see a lot of holes are empty, this algorithm requires a lot of space even for a small but widely spread data.

See the animation to understand who it really works.
{% capture fig_img %}
![Pigeonhole Sort Animation](https://68.media.tumblr.com/c1b705f22bbd5ebf72a029e7b8a42630/tumblr_ojd9yhKsuS1w0dccho1_1280.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual demonstration of Pigeonhole Sort.</figcaption>
</figure>

### Code
I have two methods for implementing Pigeonhole Sort in Python: one is a special case.
#### General
```python
def pigeonsort(values):
    # size of range of values in the list (ie, number of pigeonholes we need)
    _min = min(values)
    _max = max(values)
    _range = _max - _min + 1

    # pigeonholes
    '''holes = [0 for i in range(_range)]'''
    holes = [0] * _range

    # populate the holes
    for x in values:
		holes[x - _min] += 1

    # new sorted list, putting elements back to save space
    i = 0
    for count in range(_range):
        while holes[count] > 0:
        #copy all elements from each hole
            holes[count] -= 1
            values[i] = count + _min
            i += 1
```
#### Special
This method works **iff** the list has continuous and not-repeating values.
```python
def pigeonsort( values ):
    _min = min(values)
    _max = max(values)
    _range = _max - _min
    
    # holes = [0 for i in range(_range + 1)]
    holes = [0] * _range
    
    # filling holes
    for value in values:
        holes[ value - _min ] = value
        
    #moving back to original; in order
    values = [value for value in holes]
    
    return values
```

See the result in [this IPython Notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_06_-_Pigeonhole_Sort.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new) OR comment below.</small>
