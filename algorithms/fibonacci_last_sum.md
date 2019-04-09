---
title: Fibonacci Last Sum
layout: article
keywords: programming
summary: "Find the last digit of a sum of Fibonacci numbers."
permalink: /fibonacci_last_sum/
tags: [algorithms]
---

#### Problem statement

##### Find the last digit of a sum of Fibonacci numbers.
```
def fib(n):
    if n <= 1:
        return n

    previous = 0
    current  = 1

    for _ in range(n - 1):
        previous, current = current, previous + current
    return (current)


def solution(n, m):
    # pisano period of 10 is 60
    pp = 60
    remainder = n % pp
    sum = fib(remainder+2)-1

    return (sum%10 )

if __name__ == '__main__':

  input = int(input())
  print (solution(input))

```
