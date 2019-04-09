---
title: Fibonacci Pisano
layout: article
keywords: programming
summary: "Use the Pisano period to calculate Fn mod m i.e. the remainder of a Fibonacci number divided by m."
permalink: /fibonacci_pisano/
tags: [algorithms]
---

#### Problem statement

##### Use the Pisano period to calculate Fn mod m i.e. the remainder of a Fibonacci number divided by m.
```
def pisano_period(m):
    for i in range(2, m*m):
        if fib(i)%m == 0 and fib(i+1)%m == 1:
            return i

def fib(n):
    if n <= 1:
        return n
    previous = 0
    current  = 1
    for _ in range(n - 1):
        previous, current = current, previous + current

    return current

def solution(n, m):
    pp = pisano_period(m)
    remainder = n % pp

    return (fib(remainder) % m)

if __name__ == '__main__':

  a, b = map(int, sys.stdin.read().split())
  print (solution(a, b))

```
