---
layout: post
title: "Tower of Hanoi"
excerpt: "Tower of Hanoi is a mathematical puzzle game. It is famous for being used as a challenge in coding problems."
tags: 
  - 100 algorithms
  - python
---
## Tower of Hanoi
Tower of Hanoi is widely used as a brain teaser in algorithmic coding problems. It is actually a mathematical puzzle game. Read more about Tower of Hanoi [here](https://en.wikipedia.org/wiki/Tower_of_Hanoi).<br />
The setting of the original puzzle game involves disks and three stands to stack them on. Disks from one stand are to be shifted to the third stand through the second stand. The movement of disks obeys following simple rules:
1. Only one disk can be moved at a time.
2. Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack.
3. No disk may be placed on top of a smaller disk. <br />
In terms of complexity, for $n$ disks, we have to make $2^{n} - 1$ movements. So, if we have 4 disks, we have to make 15 movements to achieve the required formation.<br />
This animation depicts how this puzzle game on. <br />
![hanoi-tower](../images/tower_of_hanoi.gif){: .align-center}
### Code
Now, to solve this problem programmatically, one has to see the operations it involves. Obviously, only disks are moved over and over again, hence, one can say that movement of disk is done _recursively_. The best way to solve a problem this complex, is to use recursion. <br />
