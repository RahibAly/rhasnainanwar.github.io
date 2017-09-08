---
layout: post
title: "Algo #8: Bit Manipulation"
excerpt: "Computer handles everything in 1's and 0's, called bits. Understanding how computer handles them can eliminate most of the labor work from code."
image: ../images/network-1762521_1920.jpg
tags: 
  - 100 algorithms
  - programming
  - algorithms
  - python
comments: true
---
First up, I have to admit that this post is a bit of disappoint for some people. I can feel ya, folks. In my defense, I really wanted to _fix_ this somehow somewhere; because understanding the code at bit level can guarantee better **algorithmic thinking**.

# Binary in Code
Computer processes data only in 1's and 0's ... bla.. bla.. you know the story, right. The point is that using binary number system, or at least understanding it, can result it more _cool_ code with efficient performance. As this series is all about algorithms, let me present a bunch of cool _hacks_ (if you will) that can boost the run time of your code.

For Example
: We use built-in function for taking higher powers. Most languages have this function `pow()` for this. But using bit operations, you can compute higher powers much faster than the given function.

with that and more, let's start playing with bits.

**Note:** Keep a pen/pencil and a piece of paper with you as your go further into this post.
{: .notice}

## Bit Operations
Before going into any details, familiarize yourself with basic bit operations.

Bit Operations
: `&:` performs bitwise **AND** operation<br />
`|:` performs bitwise **OR** operation<br />
`~:` inverts the bits of given numbers; bitwise **NOT**<br />
`^:` performs bitwise **XOR**, exclusive OR<br />
`<<:` left shift; shifts all the bits to the left by the given amount<br />
`>>:` right shift; shifts all the bits to the right by the given amount<br />
Read more: [Python Wiki](https://wiki.python.org/moin/BitwiseOperators){:target="_blank"}

> Note that the given operation is performed bitwise even if the given value is decimal or in any other system.

## No. of Active Bits
Numbers in binary consist of only 1's and 0's, sometimes it's required to know how many 1's or active bits the number contains. Here's is how to do that:
```python
def count( value ):
    count = 0 # no. of active bits
    while value: # until the number is reduced to zero
    	# value = value & (value - 1)
        value &= value - 1
        count += 1
    return count
```
If you grab a pen and paper, work this out and you'll be surprised to see how remarkable it looks in operation.

## Check Power of 2
Simple function that checks if the given number is a power of two.
Using normal programming approach
```python
def isPowerOf2(num):
	if not num:
		return False
	while num % 2 is 0:
		x /= 2
	return x==1
```
Using bit manipulation
```python
def isPowerof2(num):
	return (x and not (x & (x - 1)))
```
Run a paper test on this and amaze yourself!

## 