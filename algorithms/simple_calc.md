---
title: Simple Calculator
layout: article
keywords: programming
summary: "Create a simple calculator."
permalink: /simple_calc/
tags: [algorithms]
---

#### Problem statement

##### Given x, find the minimum number of operations to get to n with only x*2, x*3 and x+1 as possible operations

```cpp
#include <iostream>
#include <cassert>
#include <random>
#include <vector>
#include <algorithm>
#include <sys/time.h>
#include <csignal>


using namespace std;
using std::vector;

vector<int> test_sequence(int n) {
  vector <int> temp_sequence(n,n);
  temp_sequence[0] = 0;
  if (n == 1) {
    temp_sequence[0] = 1;
    return temp_sequence;
  }
  vector <int> sequence(n+1,n);
  sequence[0] = 0;
  sequence[1] = 0;
  // sequence[n] = 0;

  // create array
  for (int i=1; i < n; i++) {
    int m = i * 3;
    // cout << "i*3: "<< sequence[m] << "\n";
    if (m<=n && sequence[i]+1 < sequence[m]) {
      sequence[m] = sequence[i]+1;
    }
    m = i * 2;
    // cout << "i*2: "<< sequence[m] << "\n";
    if (m<=n && sequence[i]+1 < sequence[m]) {
      sequence[m] = sequence[i]+1;
    }
    m = i + 1;
    // cout << "i+1: "<< sequence[m] << "\n";
    if (m<=n && sequence[i]+1 < sequence[m]) {
      sequence[m] = sequence[i]+1;
    }
  }
  // resize vector to include the shortest path
  int q = n;
  int r = n;
  int s = n;

  vector <int> new_sequence;
  while (n >= 1) {
    new_sequence.push_back(n);
    if (n % 3 == 0) {
      q = sequence[n/3];
    }
    if (n % 2 == 0) {
      r = sequence[n/2];
    }
    if (n - 1 != 0) {
      s = sequence[n-1];
    }
    if (q<=r && q<=s) {
          n /= 3;
    } else if (r<s && r<q){
        n /= 2;
    } else {
        n = n-1;
    }
  }

  reverse(new_sequence.begin(), new_sequence.end());
  return new_sequence;
  // return sequence;
}

```
