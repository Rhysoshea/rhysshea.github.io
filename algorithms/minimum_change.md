---
title: Minimum Change
layout: article
keywords: programming
summary: "Find the minimum number of coins needed to change the input value into coins with denominations 1, 5 and 10."
permalink: /minimum_change/
tags: [algorithms]
---

#### Problem statement

##### Find the minimum number of coins needed to change the input value into coins with denominations 1, 5 and 10.
```
#include <iostream>
#include <cassert>
#include <random>
#include <sys/time.h>

using namespace std;

void test_solution(int m, int coins) {

    int remainder = m;

    if (remainder >= 10) {
      remainder -= 10;
      coins += 1;
      test_solution(remainder, coins);
    }
    else if (remainder >= 5) {
      remainder -= 5;
      coins += 1;
      test_solution(remainder, coins);
    }
    else if (remainder > 0) {
      remainder -= 1;
      coins += 1;
      test_solution(remainder, coins);
    }
    else {
      cout << coins << "\n";
    }
}

int main() {

  int m;
  int coins = 0;
  cin >> m;
  test_solution(m, coins);

}

```
