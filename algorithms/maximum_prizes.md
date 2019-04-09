---
title: Maximum Prizes
layout: article
keywords: programming
summary: "Find the maximum amount of numbers that can sum to n, with each number being greater than the last."
permalink: /maximum_prizes/
tags: [algorithms]
---

#### Problem statement

##### The goal of this problem is to represent a given positive integer 𝑛 as a sum of as many pairwise distinct positive integers as possible. That is, to find the maximum 𝑘 such that 𝑛 can be written as 𝑎1 + 𝑎2 + · · · + 𝑎𝑘 where 𝑎1, . . . , 𝑎𝑘 are positive integers and 𝑎𝑖 ̸= 𝑎𝑗 for all 1 ≤ 𝑖 < 𝑗 ≤ 𝑘.
```
#include <iostream>
#include <cassert>
#include <random>
#include <sys/time.h>
#include <algorithm>
#include <vector>
#include <climits>

using namespace std;
using std::vector;


struct Segment {
  int start, end;
};

vector<int> test_solution(int n) {
  vector<int> summands;
  int remainder = n - 1;
  int ii = 1;
  if (n < 3) {
    summands.push_back(n);
    return summands;
  }
  summands.push_back(1);

  while (remainder > 0) {
    if (remainder <= summands.back()) {
      summands.back() += remainder;
      remainder = 0;
    }
    else {
      summands.push_back(summands.back() + 1);
      remainder -= summands.back();
      ii++;
    }
  }
  return summands;
}

int main() {
  int n;
  cin >> n;

  vector<int> summands = test_solution(n);

  cout << summands.size() << '\n';
  for (size_t i = 0; i < summands.size(); ++i) {
    cout << summands[i] << ' ';
  }
}

```
