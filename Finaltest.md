# 기말고사
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
