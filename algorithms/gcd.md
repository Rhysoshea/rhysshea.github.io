---
title: Greatest Common Divisor
layout: article
keywords: programming
summary: "Return the greatest common divisor for two integers."
permalink: /greatest_common_divisor/
tags: [algorithms]
---

#### Problem statement

##### Return the greatest common divisor for two integers.
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
