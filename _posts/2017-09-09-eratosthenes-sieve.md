---
layout: post
title: "Algo #9: The Sieve of Eratosthenes"
excerpt: "Eratosthenes' Sieve is a popular ancient method for finding prime numbers within a number range."
image: ../images/pay-2446670_1280.jpg
tags: 
  - 100 algorithms
  - python
  - maths
comments: true
---
Today we'll do some time traveling and MATH, yay! So, this is about finding/listing prime numbers. Eratosthenes' Sieve is an ancient method for finding prime numbers, and it is fast! Let's find out..

# Eratosthenes' Sieve
The Sieve of Eratosthenes is one of the most popular methods for finding and counting prime numbers within a range. The reason for its popularity is, as you can guess, its speed.

## Working
This algorithm is based on the theory of prime numbers and factors. The algorithms iterates over all the possible factors of the given range (limit), and crosses out their multiples, which means those cannot be prime numbers. After all the factors have been scanned, the numbers still left are prime numbers. Its time complexity is `O( log( log n ) )` operations.

**Note:** A number cannot have a factor greater than its square root, so avoid redundant iterating.
{: .notice_info}

{% capture fig_img %}
![Next Permutation Animation](https://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Source: Wikipedia</figcaption>
</figure>

### Code
The implementation of this method is very straightforward and simple.
```python
def prime_generator( limit ):
# start off with all numbers in the bag
    ls = [True] * limit
    
    '''Consider point about maximum factor, mentioned in description'''
    # prime numbers start from 2
    for i in range(2, int(math.sqrt(limit)) + 1): # iterate over all possible factors
        for j in range(i*2, limit, i): # and their multiples
            ls[j] = False # cross 'em out
    
    # 0 and 1 are not prime numbers but they are still in list, so count -2
    print( "We  have ", ls.count(True) - 2, " prime numbers." )
    print( [i for i in range(2, limit) if ls[i]]) # print all prime numbers

# test run
if __name__ == '__main__':
	prime_generator(10)
```
Output:
```
We  have  4  prime numbers.
[2, 3, 5, 7]
```

See more results in [this IPython Notebook](https://github.com/rhasnainanwar/100_days_of_algorithms/blob/master/Algo_09_-_Eratosthenes_Sieve.ipynb).
<small>In case of any errors, open an issue in [100 Algorithms repo](https://github.com/rhasnainanwar/100_days_of_algorithms/issues/new) OR comment below.</small>