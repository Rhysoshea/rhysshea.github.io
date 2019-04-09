---
title: Car Fueling
layout: article
keywords: programming
summary: "What is the minimum number of refills needed?"
permalink: /car_fueling/
tags: [algorithms]
---

#### Problem statement

##### You are going to travel to another city that is located 𝑑 miles away from your home city. You can can travel at most 𝑚 miles on a full tank and you start with a full tank. Along your way, there are gas stations at distances stop1, stop2, . . . , stop𝑛 from your home city. What is the minimum number of refills needed?
```
#include <iostream>
#include <cassert>
#include <random>
#include <sys/time.h>
#include <algorithm>
#include <vector>

using namespace std;
using std::vector;


int compute_min_refills(int d, int m, vector<int> & stops) {
    int numRefills = 0;
    int currentRefill = 0;

    stops.insert(stops.begin(), 0);
    stops.push_back(d);
    int n = stops.size();

    while (currentRefill < n) {
      int lastRefill = currentRefill;
      while (currentRefill < n && ((stops[currentRefill+1] - stops[lastRefill]) <= m)) {
        currentRefill += 1;
      }
      if (currentRefill == lastRefill) {
        return -1;
      }
      if (currentRefill < n-1) {
        numRefills += 1;
      }
    }
    if (d - stops[currentRefill-1] <= m) {
      return numRefills;
    }
    else {
      return -1;
    }
}

int main() {
    int d = 0;
    cin >> d;
    int m = 0;
    cin >> m;
    int n = 0;
    cin >> n;

    vector<int> stops(n);
    for (size_t i = 0; i < n; ++i)
        cin >> stops[i];

    cout << compute_min_refills(d, m, stops) << "\n";

    return 0;
}

```
