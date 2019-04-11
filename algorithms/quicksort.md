---
title: Quicksort Algorithm
layout: article
keywords: programming
summary: "Optimise quicksort algorithm using 3 way partition."
permalink: /quicksort_algorithm/
tags: [algorithms]
---

#### Problem statement

##### Optimise the quicksort algorithm to make it faster, using a 3 way partition function instead of a 2 way partition.

```cpp
#include <iostream>
#include <vector>

using namespace std;
using std::vector;

void partition3(vector<int> &a, int l, int r, int &m1, int &m2) {
  int x = a[l];
  m1 = l;
  m2 = r;

  if (r - l <= 1) {
    if (a[r] < a[l]) {
      swap(a[r], a[l]);
    }
    m1 = l;
    m2 = r;
    return;
  }
  while (l <= r)  {

    if (a[l] < x) {
      swap(a[l], a[m1]);
      m1++;
      l++;
    }
    else if (a[l] == x) {
      l++;
    }
    else if (a[l] > x) {
      swap(a[l], a[m2]);
      m2--;
      r--;
    }
  }
  return;
}

void quick_sort(vector<int> &a, int l, int r) {
  if (l >= r) {
    return;
  }
  int m1, m2;
  partition3(a, l, r, m1, m2);

  quick_sort(a, l, m1-1);
  quick_sort(a, m2+1, r);
}


int main() {
  int n;
  cin >> n;
  vector<int> a(n);
  for (size_t i = 0; i < a.size(); ++i) {
    cin >> a[i];
  }
  quick_sort(a, 0, a.size() - 1);
  for (size_t i = 0; i < a.size(); ++i) {
    cout << a[i] << ' ';
  }
}
```
