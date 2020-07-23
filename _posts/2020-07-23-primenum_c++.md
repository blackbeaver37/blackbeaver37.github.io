---

title: C++ 소수 찾기 최적화
excerpt: "find Prime Number"
date: July 23, 2020
categories:
  - MyCodes
tags:
  - C++
last_modified_at: 2020-07-23T23:58:00-05:00

---

```c++
#include <cmath>

#define MAX_NUM 1000000

bool isPrime[MAX_NUM+1] = {true, };

void initPrime(int num) {
    isPrime[0] = false;
    isPrime[1] = false;
    for (int i = 2; i <= sqrt(num); i++) {
        if (isPrime[i] == false)
            continue;
        else {
            for (int j = i * i; j <= num; j += i)
                isPrime[j] = false;
        }
    }
}
```
