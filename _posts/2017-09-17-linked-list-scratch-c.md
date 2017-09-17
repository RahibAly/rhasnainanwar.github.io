---
layout: post
title: "Linked Lists from Scratch"
excerpt: "A linked list is an array-like classic data structure that connects nodes to the nodes after them, like a chain."
image: https://d2lm6fxwu08ot6.cloudfront.net/img-thumbs/960w/HRN8C1WJRF.jpg
tags: 
  - algorithms
  - C
  - data structures
comments: true
---
I'm very excited today, not only because I'm posting after more than a week but also because I'm posting about an exciting topic. For starters, third semester has started introducing me to an importa, Data Structures and Algorithms, course. I has started [100 Algorithms](/100-algorithms/) series. I needed a break to settle in, now I'm back with something big. <br />
My [instructor](http://seecs.nust.edu.pk/faculty/shafait.html){:target="_blank"} started this course by introducing us to pointers. This made me think _'wat?'_, but after digging in, I found out that pointers are the most basic building block of Data Structures. So, now I'll create Linked List data structure from scratch in C using pointers.

Pointers
: are variables that _point_ to some variable using memory addresses. By using pointers we have access to a variable's memory and value which allows efficient programming having more control over memory management. <br /> Read More: [Pointers in C](http://www.cprogramming.com/tutorial/c/lesson6.html){:target="_blank"}

# Linked List
Linked List is a data structure similar to arrays. The difference is that, unlike arrays, linked lists don't have indices which means we can't access any arbitrary _node_ from linked list. Instead, we have to traverse through all the nodes, from the head to required node. Nodes are structs which have their own value and a pointer to the next node. This allows **dynamic** (re)allocation of list on **runtime**. All these nodes are connected like a chain, where the first node is called the `head` and the last one is called the `tail`, which points to nothing.

{% capture fig_img %}
![Linked List](https://68.media.tumblr.com/504c58dcff78718975ef92b2c3676988/tumblr_onw2uloGEg1w0dccho1_1280.gif)
{% endcapture %}
<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Linked List Illustration</figcaption>
</figure>

## Linked List in C