---

title: C++ STL 1. Container
excerpt: ""
date: July 24, 2020
categories:
  - Tips
tags:
  - C++
last_modified_at: 2020-07-24T04:00:00-05:00

---

## **STL 컨테이너 (STL Container)**

1. 순차 컨테이너 (Sequence Container)

    + vector  
    `맨 뒤 & 중간 삽입 삭제 가능`  
    `배열 기반`  
    `많은 삽입 삭제 필요 시 비효율적`

    ```c++
    #include<iostream>
    using namespace std;
    ```

    ```c++
    생성 및 초기화

    vector<자료형> v(size, value);
    // default size & value = 0
    // Parameter로 vector를 전달하면 복사 가능
    v.assign(size, value);
    v.reserve(size);
    // size만큼의 공간 추가로 할당
    ```

    ```c++
    원소 참조

    v.at(index);
    v[index];
    // at은 범위를 점검 하므로 안전
    // []은 범위를 점검하지 않아 빠름
    v.front();
    v.back();
    ```

    ```c++
    원소 삽입

    v.push_back(value);
    v.insert(iterator, size, value);
    v.insert(iterator, first_iterator, last_iterator);
    // iterator 위치에 해당 원소 및 범위 삽입
    // last_iterator의 값은 삽입되지 않는다.
    // 삽입한 위치의 iterator 반환
    ```

    ```c++
    원소 삭제

    v.clear();
    v.pop_back();
    v.erase(iterator);
    v.erase(first_iterator, last_iterator);
    // iterator 위치에 해당 원소 및 범위 삭제
    // last_iterator의 값은 삭제되지 않는다.
    ```

    ```c++
    반복자

    v.begin();
    v.end();
    v.rbegin();
    v.rend();
    ```

    ```c++
    크기

    v.size();
    v.resize(size, value);
    // 크기가 커질 경우 value 값으로 초기화 default = 0
    v.capacity();
    // 할당된 메모리의 크기
    // 메모리 증가 값 = 기존 메모리 x 2
    v.empty();
    ```

    ```c++
    그 외

    v_2.swap(v_1);
    // v_1과 v_2를 바꿔준다.
    vector<자료형>().swap(v);
    // v의 메모리 해제 시 사용
    ```

    ---

    + deque  
    `맨 앞 & 맨 뒤 & 중간 삽입 삭제 가능`  
    `배열 기반`  
    `앞 뒤 삽입 삭제 시 vector보다 효율적, 그 외는 vector보다 비효율적`  
    `랜덤한 데이터 접근 가능`

    ```c++
    #include <deque>
    using namespace std;
    ```

     ```c++
    생성 및 초기화

    deque<자료형> dq(size, value);
    // default size & value = 0
    // Parameter로 deque를 전달하면 복사 가능
    dq.assign(size, value);
    ```

    ```c++
    원소 참조

    dq.at(index);
    dq[index];
    // at은 범위를 점검 하므로 안전
    // []은 범위를 점검하지 않아 빠름
    dq.front();
    dq.back();
    ```

    ```c++
    원소 삽입

    dq.push_front(value);
    dq.push_back(value);
    dq.insert(iterator, size, value);
    dq.insert(iterator, first_iterator, last_iterator;
    // iterator 위치에 해당 원소 및 범위 삽입
    // last_iterator의 값은 삽입되지 않는다.
    // 앞 뒤 중 원소가 적은 곳에 삽입
    // 삽입한 위치의 iterator 반환
    ```

    ```c++
    원소 삭제

    dq.clear();
    dq.pop_front();
    dq.pop_back();
    dq.erase(iterator);
    dq.erase(first_iterator, last_iterator);
    // iterator 위치에 해당 원소 및 범위 삭제
    // last_iterator의 값은 삭제되지 않는다.
    ```

    ```c++
    반복자

    dq.begin();
    dq.end();
    dq.rbegin();
    dq.rend();
    ```

    ```c++
    크기

    dq.size();
    dq.resize(size, value);
    // 크기가 커질 경우 value 값으로 초기화 default = 0
    dq.empty();
    ```

    ```c++
    그 외

    dq_2.swap(dq_1);
    // dq_1과 dq_2를 바꿔준다.
    deque<자료형>().swap(dq);
    // dq의 메모리 해제 시 사용
    ```

    ---

    + list  
    `맨 앞 & 맨 뒤 & 중간 삽입 삭제 가능`  
    `노드 기반`  
    `이중 연결 리스트`  
    `반복자를 이용한 탐색`

    ```c++
    #include <list>
    using namespace std;
    ```

    ```c++
    생성 및 초기화

    list<자료형> lt(size, value);
    // default size & value = 0
    // Parameter로 deque를 전달하면 복사 가능
    lt.assign(size, value);
    ```

    ```c++
    원소 참조

    lt.front();
    lt.back();
    ```

    ```c++
    원소 삽입

    lt.push_front(value);
    lt.push_back(value);
    lt.insert(iterator, value);
    // iterator 위치에 원소 삽입
    // 삽입한 위치의 iterator 반환
    ```

    ```c++
    원소 삭제

    lt.clear();
    lt.pop_front();
    lt.pop_back();
    lt.erase(iterator);
    // iterator 위치에 원소 삭제
    // 다음 원소를 가리키는 iterator 반환
    lt.remove(value);
    // value와 같은 모든 원소 제거
    lt.remove_if(predicate);
    // 단항 조건자 predicate에 해당하는 모든 원소 제거
    ```

    ```c++
    반복자

    lt.begin();
    lt.end();
    lt.rbegin();
    lt.rend();
    ```

    ```c++
    크기

    lt.size();
    lt.resize(size, value);
    // 크기가 커질 경우 value 값으로 초기화 default = 0
    lt.empty();
    ```

    ```c++
    그 외

    lt_2.swap(lt_1);
    // lt_1과 lt_2를 바꿔준다.
    list<자료형>().swap(lt);
    // lt의 메모리 해제 시 사용
    lt.reverse();
    // 원소의 순서를 뒤집는다.
    lt.sort(compare);
    // 이항조건자 compare에 해당하는 기준으로 정렬, default = 오른차순
    lt_2.splice(iterator_2, lt_1);
    lt_2.splice(iterator_2, lt_1, iterator_1);
    lt_2.splice(iterator_2, lt_1, begin_iterator_1, end_iterator_1);
    // lt_2의 iterator_2 위치에 lt_1의 iterator_1위치 원소(범위)를 잘라 붙힌다.
    lt.unique();
    // 인접한 원소 중 중복값 제거
    lt_2.merge(lt_1, compare);
    // lt_1을 lt_2내부로 합병 정렬 default = 오름차순
    ```

   ---

2. 컨테이너 어댑터 (Container Adaptor)

    + stack

    ```c++
    #include <stack>
    using namespace std;
    ```

    ---

    + queue

    ```c++
    #include <queue>
    using namespace std;
    ```

    ---

    + priority_queue

    ```c++
    #include <priority_queue>
    using namespace std;
    ```

   ---

3. 연관 컨테이너 (Associate Container)

    + set

    ```c++
    #include <set>
    using namespace std;
    ```

    ---

    + multiset

    ```c++
    #include <set>
    using namespace std;
    ```

    ---

    + map

    ```c++
    #include <map>
    using namespace std;
    ```

    ---

    + multimap

    ```c++
    #include <map>
    using namespace std;
    ```

    ---

    + bitset

    ```c++
    #include <map>
    using namespace std;
    ```

    ---

---
