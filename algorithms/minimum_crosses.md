---
title: Greedy Knapsack
layout: article
keywords: programming
summary: "Find the minimum number of cross over points between line segments."
permalink: /greedy_knapsack/
tags: [algorithms]
---

#### Problem statement

##### Given a set of 𝑛 segments {[𝑎0, 𝑏0], [𝑎1, 𝑏1], . . . , [𝑎𝑛−1, 𝑏𝑛−1]} with integer coordinates on a line, find the minimum number 𝑚 of points such that each segment contains at least one point. That is, find a set of integers 𝑋 of the minimum size such that for any segment [𝑎𝑖, 𝑏𝑖] there is a point 𝑥 ∈ 𝑋 such that 𝑎𝑖 ≤ 𝑥 ≤ 𝑏𝑖.
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

vector<int> test_solution(vector<Segment> &segments) {
  vector<int> points;
  //write your code here

  sort(segments.begin(), segments.end(), [](const Segment &a, const Segment &b) -> bool {
    return a.end < b.end;
  });

  int point = segments[0].end;
  points.push_back(point);

  for (size_t i = 0; i < segments.size(); ++i) {
    if (point < segments[i].start || point > segments[i].end) {
      point = segments[i].end;
      points.push_back(point);
    }
  }
  return points;
}

int main() {
  int n;
  cin >> n;
  vector<Segment> segments(n);
  for (size_t i = 0; i < segments.size(); ++i) {
    cin >> segments[i].start >> segments[i].end;
  }
  vector<int> points = test_solution(segments);
  cout << points.size() << "\n";
  for (size_t i = 0; i < points.size(); ++i) {
    cout << points[i] << " ";
  }
}

```
