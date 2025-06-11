# 기말고사
## 자료구조의 종류 
#### 배열(Array) 
#### 연결 리스트(Linked List) 
#### 스택(Stack) 
#### 큐(Queue)
#### 트리(Tree)
#### 해시 테이블(Hash Table)
## 알고리즘의 종류
#### 정렬, 탐색, 재귀, 동적계획법, 그래프, 백트래킹
### 랜덤으로 주사위를 굴리기
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main() {
    int c[6] = { 0 }, i;
    srand(time(0));
    for (i = 0; i < 600; i++) c[rand() % 6]++;
    for (i = 0; i < 6; i++)   printf("%d: %d\n", i + 1, c[i]);
}
```
