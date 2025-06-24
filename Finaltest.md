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

### swap() 함수를 활용하여 매개변수로 전달된 두 수를 교환
```c
#include <stdio.h>

void swap(int* a, int* b) { 
	int t;
	t = *a;
	*a = *b;
	*b = t;
	return;
}
int main() {
	int a = 3, b = 5;
	printf("%d %d\n", a, b);
	swap(&a, &b);
	printf("%d %d\n", a, b);
}
```

### 명령형 매개변수를 활용하여 사칙연산을 구현 - if문
```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char* argv[]) {
    if (argc < 3) exit(0);
    printf("%s %s %s\n", argv[1], argv[2], argv[3]);

    int a = atoi(argv[1]);
    int b = atoi(argv[3]);

    if(argv[2][0]=='+')
        printf("%d\n", a + b);
    if (argv[2][0] == '-')
        printf("%d\n", a - b);
    if (argv[2][0] == '*')
        printf("%d\n", a * b);
    if (argv[2][0] == '/')
        printf("%d\n", a / b);
    return 0;
}
```

### 명령형 매개변수를 활용하여 사칙연산을 구현 - switch 문
```c
#include <stdio.h>
#include <stdlib.h>
int main(int argc, char* argv[]) {
    if (argc < 3) exit(0);
    printf("%s %s %s\n", argv[1], argv[2], argv[3]);
    int a = atoi(argv[1]);
    int b = atoi(argv[3]);
    int c=0;
    switch (argv[2][0]) {
        case '+': c = a + b; break;
        case '-': c = a - b; break;
        case '*': c = a * b; break;
        case '/': c = a / b; break;
        default: break;
    }
    printf("%d\n", c);
    return 0;
}
