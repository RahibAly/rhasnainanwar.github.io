---
layout: post
title: "Algo #1: Tower of Hanoi"
excerpt: "Tower of Hanoi is a mathematical puzzle game. It is famous for being used as a challenge in coding problems."
image: ../images/tower_of_hanoi.gif
tags: 
  - 100 algorithms
  - python
---
# Tower of Hanoi
Tower of Hanoi is widely used as a brain teaser in algorithmic coding problems. It is actually a mathematical puzzle game. Read more about Tower of Hanoi [here](https://en.wikipedia.org/wiki/Tower_of_Hanoi).<br />
The setting of the original puzzle game involves disks and three stands to stack them on. Disks from one stand are to be shifted to the third stand through the second stand. The movement of disks obeys following simple rules:
1. Only one disk can be moved at a time.
2. Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack.
3. No disk may be placed on top of a smaller disk.

In terms of complexity, for $n$ disks, we have to make $2^{n} - 1$ movements. So, if we have 4 disks, we have to make 15 movements to achieve the required formation.<br />
{% capture fig_img %}
![Tower of Hanoi Animated](../images/tower_of_hanoi.gif)
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Animated representation of Tower of Hanoi puzzle.</figcaption>
</figure>
## Code
Now, to solve this problem programmatically, one has to see the operations it involves. Obviously, only disks are moved over and over again, hence, one can say that movement of disk is done _recursively_. The best way to solve a problem this complex, is to use recursion. <br />
The code given below moves the disks recursively and prints out the movement of the top disk: `from` to `to` while the stands are named *right*, *left*, and *middle*.<br />
```python
def hanoi(height, fro='left', to='right', through='middle'):
    if height:
            hanoi(height - 1, fro, through, to )
            print ('%-7s => %s' % (fro, to))
            hanoi(height -1, through, to, fro)
```
See some example runs [here](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Day_01_-_Hanoi_Tower.ipynb).
