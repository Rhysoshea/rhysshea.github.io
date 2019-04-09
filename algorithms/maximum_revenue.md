---
title: Maximum Revenue
layout: article
keywords: programming
summary: "output the maximum dot product of two sequences of integers."
permalink: /maximum_revenue/
tags: [algorithms]
---

#### Problem statement

##### Given two sequences 𝑎1, 𝑎2, . . . , 𝑎𝑛 (𝑎𝑖 is the profit per click of the 𝑖-th ad) and 𝑏1, 𝑏2, . . . , 𝑏𝑛 (𝑏𝑖 is the average number of clicks per day of the 𝑖-th slot), we need to partition them into 𝑛 pairs (𝑎𝑖, 𝑏𝑗) such that the sum of their products is maximized.
```
#include <iostream>
#include <cassert>
#include <random>
#include <sys/time.h>
#include <algorithm>
#include <vector>

using namespace std;
using std::vector;

long long test_solution(vector<long long> a, vector<long long> b) {
  long long result = 0;
  sort(a.begin(), a.end());
  sort(b.begin(), b.end());
  for (size_t i = 0; i < a.size(); i++) {
    result += ((double) a[i]) * b[i];
  }
  return result;
}

int main() {
  size_t n;
  cin >> n;
  vector<long long> a(n), b(n);
  for (size_t i = 0; i < n; i++) {
    cin >> a[i];
  }
  for (size_t i = 0; i < n; i++) {
    cin >> b[i];
  }
  cout << test_solution(a, b) << endl;
}

```
