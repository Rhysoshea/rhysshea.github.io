---
title: Change dynamic programming
layout: article
keywords: programming
summary: "Use dynamic programming to calculate the amount of change given ."
permalink: /change_dp/
tags: [algorithms]
---

#### Problem statement

##### Given Use dynamic programming to calculate the amount of change given

```cpp
int get_change(int m) {
  //write your code here
  if (m < 2) {
    return m;
  }
  int minCoins[m];
  minCoins[0] = 0;

  int coins[] = {1,3,4};

  for (int k=1; k <= m; k++) {
    int numCoins = 0;
    minCoins[k] = 100000;
    for (int c=0; c < 3; c++) {
      if (k >= coins[c]) {
        numCoins = minCoins[k-coins[c]] + 1;
        if (numCoins < minCoins[k]) {
          minCoins[k] = numCoins;
        }
      }
    }
  }


  return minCoins[m];
}

int main() {
  int m;
  cin >> m;
  cout << get_change(m) << '\n';
}



```
