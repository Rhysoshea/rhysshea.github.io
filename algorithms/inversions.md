---
title: Number of Inversions
layout: article
keywords: programming
summary: "Count how many inversions there are in an array."
permalink: /inversions/
tags: [algorithms]
---

#### Problem statement

##### Count how many inversions there are in an array. An inversion is counted as a pair of numbers b and c, where b > c but comes after c from left to right. This solution uses the merge sort algorithm.

```cpp
#include <iostream>
#include <vector>

using namespace std;
using std::vector;


long long merge(vector<int> &A, int left, int mid, int right) {
  long long inversions = 0;

  int m1 = mid - left + 1;
  int m2 = right - mid;
  vector<int> B(m1);
  vector<int> C(m2);

  for (int i=0; i < m1; i++) {
    B[i] = A[left+i];
  }
  for (int j=0; j < m2; j++) {
    C[j] = A[j+mid+1];
  }
  int k = left;
  int i = 0;
  int j = 0;

  while (i < m1 && j < m2) {
    if (B[i] <= C[j]) {
      A[k] = B[i];
      i++;
    }
    else {
      A[k] = C[j];
      j++;
      inversions += (m1-i);
    }
    k++;
  }
  while (i < m1) {
    A[k] = B[i];
    i++;
    k++;
  }
  while (j < m2) {
    A[k] = C[j];
    j++;
    k++;
  }
  return inversions;
}

int main() {
  int n;
  cin >> n;
  vector<int> A(n);
  for (int i = 0; i < A.size(); i++) {
    cin >> A[i];
  }
  cout << mergeSort(A, 0, A.size()-1) << '\n';
}

```
