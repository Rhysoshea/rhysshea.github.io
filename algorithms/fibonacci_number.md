---
title: Fibonacci Numbers
layout: article
keywords: programming
summary: "Create a function that calculates the Fibonacci number."
permalink: /fibonacci_numbers/
tags: [algorithms]
---

#### Problem statement

##### Create a function that calculates the Fibonacci number.
```
def solution(input):
    if input <= 1:
        return input
    cache = [0 for _ in range(input)]
    cache[0] = 1
    for i in range(1,len(cache)):
        cache[i] = cache[i-1] + cache[i-2]


    return cache[-1]

if __name__ == '__main__':

    input = int(input())
    print (solution(input))

```
