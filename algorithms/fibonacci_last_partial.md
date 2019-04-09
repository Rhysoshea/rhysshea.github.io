---
title: Fibonacci Last Partial
layout: article
keywords: programming
summary: "Find the last digit of a partial sum of Fibonacci numbers."
permalink: /fibonacci_last_partial/
tags: [algorithms]
---

#### Problem statement

##### Find the last digit of a partial sum of Fibonacci numbers.
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
    pp = 60

    sum_m = fib((m%pp)+1)-1
    sum_n = fib((n%pp)+2)-1

    return (sum_n - sum_m)%10

if __name__ == '__main__':

  a, b = map(int, sys.stdin.read().split())
  print (solution(a, b))

```
