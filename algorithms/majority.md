---
title: Majority Element
layout: article
keywords: programming
summary: "Calculate if an element appears more than 50% of the time."
permalink: /majority_element/
tags: [algorithms]
---

#### Problem statement

##### Given a sequence of elements, check whether it contains an element that appears more than n/2 times (more than 50% of the elements), if yes output 1 else 0, implement technique in O(nlogn) time

```cpp
#include <iostream>
#include <vector>

using namespace std;
using std::vector;


int test_solution(vector<int> &arr, int left, int right) {
    int count = 0, i, majorityElement;
    // read through the array and find the element with the highest count
    for (i = 0; i < right; i++) {
        if (count == 0)
            majorityElement = arr[i];
        if (arr[i] == majorityElement)
            count++;
        else
            count--;
    }
    // read through the array a second time checking whether that element exceeds 50% of the elements
    count = 0;
    for (i = 0; i < right; i++)
        if (arr[i] == majorityElement)
            count++;
    if (count > right/2)
        return majorityElement;
    return -1;
}

int main() {
  int n;
  cin >> n;
  vector<int> a(n);
  for (size_t i = 0; i < a.size(); ++i) {
    cin >> a[i];
  }
  cout << (test_solution(a, 0, a.size()) != -1) << '\n';
}
```
