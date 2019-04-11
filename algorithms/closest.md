---
title: Closest Pair
layout: article
keywords: programming
summary: "Given a set of points find the smallest distance between a pair."
permalink: /closest_pair/
tags: [algorithms]
---

#### Problem statement

##### Given a set of points find the smallest distance between a pair.

```cpp
#include <algorithm>
#include <iostream>
#include <sstream>
#include <iomanip>
#include <vector>
#include <string>
#include <cmath>
#include <climits>


using std::vector;
using std::string;
using std::pair;
using std::min;
using namespace std;


double minimal_distance(vector<int> x, vector<int> y) {
  vector<Point> points(x.size());
  for (int i=0; i<x.size(); i++) {
    points[i].x = x[i];
    points[i].y = y[i];
  }
  sort(points.begin(), points.end(), [](const Point &a, const Point &b) -> bool {
    return a.x < b.x;
  });

  if (x.size() < 4) {
    return quickMin(points, x.size());
  }
  int n = x.size();
  int mid = x.size()/2;
  Point midPoint = points[mid];

  // recursively call points on each side of the split to find minimum distance
  float min_left = getMin(points, 0, mid);
  float min_right = getMin(points, mid, x.size());

  // find the minimum of the two = d
  float d = min(min_left, min_right);
  // focus on the points within d of the midway split
  vector<Point> strip;
  for (int i = 0; i < points.size(); i++) {
    if (abs(points[i].x - midPoint.x) <= d) {
      strip.push_back(points[i]);
    }
  }

  return min(d, stripMin(strip, strip.size(), d));
}

int main() {
  size_t n;
  cin >> n;
  vector<int> x(n);
  vector<int> y(n);
  for (size_t i = 0; i < n; i++) {
    cin >> x[i] >> y[i];
  }
  cout << fixed;
  cout << setprecision(9) << minimal_distance(x, y) << "\n";
}

```
