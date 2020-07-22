---
title:  "C++/JAVA/Python 빠른 입출력"
excerpt: ""
date: 2020-07-23 02:00:00 -0400
categories:
  - Tips
tags:
  - C++
  - JAVA
  - Python
last_modified_at: 2020-07-23T02:00:00-05:00
---

### **`C++`**
```
cin.tie(NULL)
ios::sync_with_stdio(false)
단, scanf/printf/puts/getchar/putchar 등 사용 불가.
```

### `**JAVA**`
```
BufferedReader
BufferedWriter
BufferedWriter.flush (마지막)
```

### `**Python**`
```
sys.stdin.readline
개행문자도 받기 때문에 .rstrip() 추가로 사용.
```
