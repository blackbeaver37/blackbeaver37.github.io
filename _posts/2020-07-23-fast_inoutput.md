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

## **C++**
```c++
#include <iostream>

using namespace std;

int main() {
  cin.tie(NULL)
  ios::sync_with_stdio(false)
  
  return 0;
}
```
+ `ios::sync_with_stdio(false)`후에는 scanf/printf/puts/getchar/putchar 등 사용 불가

## **JAVA**
```java
import java.io.IOException;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.BufferedWriter;
import java.io.OutputStreamWriter;

class Main {
    public static void main(String[] args) {
        BufferedReader br = new BufferedReader( new InputStreamReader( System.in ) );
        int T = Integer.parseInt( br.readLine() );
        
        BufferedWriter bw = new BufferedWriter( new OutputStreamWriter( System.out ) );
        bw.write( "Hello World!!\n" );
        bw.flush();
        bw.close();
    }
}
```
+ `BufferedReader`는 개행("\n")만 구분자로 인식, 데이터형 String으로 고정
+ `BufferedWriter.flush()`는 버퍼에 남아있는 데이터를 출력

## **Python**
```python
import sys
 
for x in sys.stdin.readline():
    print(x)

for line in sys.stdin:
    print(line)
```
+ `sys.stdin.readline()`은 스페이스 및 개행을 포함하여 한줄씩 받는다.
+ `sys.stdin`을 사용하면 한번에 받을 수 있다.

