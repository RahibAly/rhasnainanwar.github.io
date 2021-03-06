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
First up, I have to admit that this post is a bit of disappointment for some people. I can feel ya, folks. In my defense, I really wanted to _fix_ this somehow somewhere; because understanding the code at bit level can guarantee better **algorithmic thinking**.

# Binary in Code
Computer processes data only in 1's and 0's ... bla.. bla.. you know the story, right. The point is that using binary number system, or at least understanding it, can result in more _cool_ code with efficient performance. As this series is all about algorithms, let me present a bunch of cool _hacks_ (if you will) that can boost the run time of your code.

For Example
: We use built-in function for taking higher powers. Most languages have this function `pow()` for this. But using bit operations, you can compute higher powers much faster than the given function.

with that and more, let's start playing with bits.

**Note:** Keep a pen/pencil and a piece of paper with you while reading this post.
{: .notice_info}

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

## No. of active bits
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

## Check power of 2
Simple function that checks if the given number is a power of two.
Using normal programming approach
```python
def isPowerOf2(num):
	if not num:
		return False
	while num % 2 is 0:
		num /= 2
	return num==1
```
Using bit manipulation
```python
def isPowerof2(num):
	return (num and not (num & (num - 1)))
```
Run a paper test on this and see the difference yourself!

## _i_-th power of 2
Given the example above; if you need to find some power of 2, using library functions can cost more time. The easy way to do it using bit operations is:
```python
# i is the power of 2
1 << i
# that's it!!
```

## Bitwise Shift
Left and right shift can double and half the given number, respectively. As left shift moves all bits to the left, the doubled value is returned. Similarly, right shift divides the value by 2, python equivalent of `//` operator.

**Warning:** Beware of the possible loss of data because of bit limits.
{: .notice_warning}

## Check if a particular bit is set
If you want to check if a particular _i_-th bit (from right) is set in a number `N`, AND it with a binary number with only 1 at that place followed by all zeros.
```python
def isSet(N, i):
	if (N & ( 1 << i )):
		return True
	return False
```
This binary expression will always yield some arbitrary number if i-th bit is set, otherwise 0.

## Set a particular bit
In contrary to the last example, if you want to _set_ _i_-th bit (from right) in a number `N`, do this:
```python
def set(N, i):
	return (N | (1 << i))
```

### Conclusion
You can get the idea how small bitwise expressions can do great things. See the properties of binary numbers and come up with your own expressions (comment them and I'll add them in this post with credit). I haven't included any working example and I want you to do that yourself as explaining step-by-step at this level can be very hectic and I'm too laazZzzyyy to do that.

See the results in [this IPython Notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_08_-_bit_manipulation.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new) OR comment below.</small>