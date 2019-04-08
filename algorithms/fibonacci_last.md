---
title: Fibonacci Last
layout: article
keywords: programming
summary: "Create a function that calculates the last digit of a Fibonacci number."
permalink: /fibonacci_last/
tags: [algorithms]
---

#### Problem statement

##### Create a function that calculates the last digit of a Fibonacci number.
```
def solution(input):
    if input <= 1:
        return input
    cache = [0 for _ in range(input)]
    cache[0] = 1
    for i in range(1,len(cache)):
        cache[i] = cache[i-1]%10 + cache[i-2]%10


    return (cache[-1])%10

if __name__ == '__main__':

    input = int(input())
    print (solution(input))

```
