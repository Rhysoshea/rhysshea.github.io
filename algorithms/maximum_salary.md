---
title: Maximum Salary
layout: article
keywords: programming
summary: "Compose the largest number out of a set of integers."
permalink: /maximum_salary/
tags: [algorithms]
---

#### Problem statement

##### Compose the largest number out of a set of integers.
```
#include <iostream>
#include <cassert>
#include <random>
#include <sys/time.h>
#include <algorithm>
#include <vector>
#include <climits>
#include <sstream>

using namespace std;
using std::vector;
using std::string;


bool isGreaterOrEqual(int a, int b) {

  stringstream c;
  stringstream d;

  c << a << b;

  d << b << a;

  int one;
  int two ;

  c >> int one;
  d >> int two;

  if (one >= two) {
    return true;
  }
  else {
    return false;
  }
}


string test_solution(vector<int> a) {

  stringstream ret;

  while (!a.empty()) {
    int maxDigit = -10000;
    int index = 0;
    for (size_t i = 0; i < a.size(); i++) {
      if (isGreaterOrEqual(a[i], maxDigit)) {
        maxDigit = a[i];
        index = i;
      }
    }
    a.erase(a.begin() + index);

    ret << maxDigit;

  }
  string result;
  ret >> result;

  return result;
}

int main() {
  int n;
  cin >> n;
  vector<int> a(n);
  for (size_t i = 0; i < n; ++i) {
    cin >> a[i];
  }
  cout << test_solution(a);
}

```
