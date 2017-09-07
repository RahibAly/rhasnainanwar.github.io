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
* Now, swap pivot with the smallest value from chosen sequence which is _larger_ than pivot value
* Invert the chosen sequence while keeping its place and other values unchanged

> If the next permutation is not possible, return false OR the sequence itself, unchanged.

### Example
Consider you have `34521` and you need to find its next permutation. <br />
**Step 1**<br />
Find the longest decreasing sequence: `521`<br />
<br />
**Step 2**<br />
Pivot Value: **4**<br />
<br />
**Step 3**<br />
Swap pivot with the smallest value in the sequence which is larger than pivot: `35421`, `4` swapped with `5`<br />
<br />
**Step 4**<br />
Reverse Sequence: `421` changes to `124`<br />
And put it at its place in the original sequence, we have the next permutation: `35124`<br />
This animation arranges the lines in every possible lexicographical order. It is worth noting that with large sequence, the number of possible permutations can be in multiples of hundred thousand.
{% capture fig_img %}
![Next Permutation Animation](https://68.media.tumblr.com/7b49d2d3675028ab07aa9ada10140482/tumblr_omnpkkeJWj1w0dccho1_400.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Visual arrangement of all possible permutations.</figcaption>
</figure>

### Code
```python
def _next( current ):
    n = len(current) # size
    for i in reversed(range(n-1)):
        if current[i] < current[i+1]: # get pivot value if sequence breaks
        '''Consider this, if we see from right to left, the sub-sequence that we need to find is now increasing sequence.
           But the pivot value is that when the sequence shifts to a decreasing one, this is how I found pivot value'''

            break # here the pivot is at i
    else: # last permutation
        return current

    # working with the sub-sequence
    for j in reversed(range(i, n)):
    '''Now, the sub-sequence is an increasing sequence (from right to left, see the 'reversed' keyword), and
       the pivot is where sequence becomes decreasing. If I scan form right, the first value that is larger than
       pivot is the one I need, because of the order. Numbers do wonders!'''

        if current[i] < current[j]:
            print ("Value to swap: ", current [j])
            # swap
            current[i], current[j] = current[j], current[i]
            # attach the reversed sub-sequence
            current[i + 1:] = reversed(current[i + 1:])
    return current
```

See the results in [this IPython Notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_07_-_Next_Permutation.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new) OR comment below.</small>