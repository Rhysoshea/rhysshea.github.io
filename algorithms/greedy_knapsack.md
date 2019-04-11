---
title: Greedy Knapsack
layout: article
keywords: programming
summary: "Find the most valuable combination of items assuming that any fraction of loot item can be put into the bag."
permalink: /greedy_knapsack/
tags: [algorithms]
---

#### Problem statement

##### Find the most valuable combination of items assuming that any fraction of loot item can be put into the bag.
```cpp
#include <iostream>
#include <cassert>
#include <random>
#include <sys/time.h>
#include <algorithm>
#include <vector>

using namespace std;

int check_max(double array[][3], int num) {
  double max = 0.0;
  int index = 0;
  for (int ii=0; ii < num; ii++) {
    if (array[ii][2] > max){
      max = array[ii][2];
      index = ii;
    }
  }
  return index;
}

double test_solution(double capacity, vector<double> weights, vector<double> values) {
  double value = 0.0;
  double bag = 0.0;
  double array[weights.size()][3];
  for (int i=0; i<weights.size(); i++) {
    array[i][0] = values[i];
    array[i][1] = weights[i];
    array[i][2] =  values[i]/weights[i];
  }


  int index = check_max(array, weights.size());

  while (bag < capacity) {
    value += array[index][2];
    array[index][1] -= 1;
    bag += 1;
    if (array[index][1] == 0) {
      array[index][2] = 0;
      index = check_max(array, weights.size());
    }
  }
  return value;
}

int main() {

  int m;
  double capacity;
  cin >> m >> capacity;
  vector<double> values(m);
  vector<double> weights(m);

  for (int i = 0; i < m; i++) {
    cin >> values[i] >> weights [i];
  }
  // function call
  double value = test_solution(capacity, weights, values);

  cout.precision(12);
  cout << value << "\n";

}

```
