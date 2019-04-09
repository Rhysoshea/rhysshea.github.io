---
title: Fibonacci Sum Square
layout: article
keywords: programming
summary: "Find the last digit of the sum of square of Fibonacci Numbers."
permalink: /fibonacci_sum_square/
tags: [algorithms]
---

#### Problem statement

##### Find the last digit of the sum of square of Fibonacci Numbers.
```
def fib(n):
    if n <= 1:
        return n
    previous = 0
    current  = 1

    for _ in range(n - 1):
        previous, current = current, previous + current
    return (current)

def solution(n):
    # F0^2+F1^2+.....+Fn^2 = Fn * F(n+1)
    pp = 60
    fib1 = fib(n%pp)
    fib2 = fib((n+1)%pp)

    return (fib1*fib2) % 10

if __name__ == '__main__':

    input = int(input())
    print (solution(input))

```
