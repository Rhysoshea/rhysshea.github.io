---
title: Binary Search
layout: article
keywords: programming
summary: "Create a binary search algorithm."
permalink: /binary_search/
tags: [algorithms]
---

#### Problem statement

##### Create a binary search algorithm which takes in an ascending array of integers and an array of search criteria, outputting the indices of the search values or -1 if they do not exist.

```cpp
#include <iostream>
#include <vector>

using namespace std;
using std::vector;


static int test_solution(const vector<int> &a,  int x) {

  int first = 0, last = (int)a.size();

  while (last > first) {
    int middle = floor((first+last)/2);
    // cout << "Middle " << a[middle] << "\n";
    if (x == a[middle]) {
      return middle;
    }
    else if (x < a[middle]) {
      last = middle;
    }
    else if (x > a[middle]){
      first = middle+1;
    }
  }
  return -1;
}


int main() {

  int n;
  cin >> n;
  vector<int> a(n);
  for (size_t i = 0; i < n; i++) {
    cin >> a[i];
  }
  int m;
  cin >> m;
  vector<int> b(m);
  for (int i = 0; i < m; i++) {
    cin >> b[i];
  }

  for (int i = 0; i < m; ++i) {
    cout << test_solution(a, b[i]) << ' ';
  }
}

```
