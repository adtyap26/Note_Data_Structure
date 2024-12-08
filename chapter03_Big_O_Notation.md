---
title: chapter03 note for A common sense guide to data structures and algorithms
author: Aditya Permana
date: 2023-09-28 14:39
urlcolor: 'blue'
---

# Big O: Count the Steps

- Big O (big oh) is just a fancy ways that borrowed from mathematics to describe a concise and consistent language around the efficiency of data structures and algorithms.

## Big O: Count the Steps

- Instead of focusing on units of time, big O achieves consistency by focusing only on the number of steps that an algorithm takes.

* O(1) "big O of 1"

- Reading from an array only takes just one step. No matter how large the array is.

- Or insertion and deletion at the end of an array

* O(N) "big O of N"

- In worst case scenario, linear search will take as many steps as there are elemetns in the array.

## Constant Time vs Linear Time

- Big O(N) also known as linear time. It takes one additional step for every additional piece of data 

- Contrast with big O(1) which also reffered to as constant time. No matter how much the additional data, it only take one step.

```
 Steps   |
       6 |            + O(N)
       5 |          +
       4 |        +
       3 |      +
       2 |    +               O(1)
       1 +--+-------------------|------------------
         |_________________________________________
         0  1  2  3 4 5 6 7 8 9 10
                    number of Elements


```
