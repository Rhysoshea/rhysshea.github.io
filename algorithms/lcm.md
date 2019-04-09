---
title: Least Common Multiple
layout: article
keywords: programming
summary: "Return the least common multiple of two integers."
permalink: /least_common_multiple/
tags: [algorithms]
---

#### Problem statement

##### Return the least common multiple of two integers.
```
def solution(n):
    if b == 0:
        return a
    a_prime = a % b

    return solution(b, a_prime)

if __name__ == '__main__':

    a, b = map(int, sys.stdin.read().split())
    print (solution(a, b))

```
