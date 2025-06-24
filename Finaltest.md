# 기말고사

## 함수의 포인터
### 포인터:메모리의 주소를 나타내는 변수
### (자료형)* 형태로 선언

### 포인터 선언
```c
#include <stdio.h> // c언어는 2가지 방법으로 컴파일함 #(전처리부호)부터 '프리 컴파일' 한다

// val 메모리에 88을 담고 포인터 p를 선언한다. p를 val의 주소로 초기화하고 주소값과 val의 값, p의 주소의 값을 출력한다.

int main() { // 함수의 시작 { 
	int val = 88;
	int* p; // 포인터 선언 
	p = &val; // 포인터의 초기화
	// *p = 11; <- 포인터의 값을 설정한다.

	printf("%p\n", &val); // val의 주소값 출력
	printf("%d\n", val);
	printf("%d\n", *p); // *p는 포인터가 지정하는 주소의 값
} // 함수의 끝 }
```

### 포인터의 주소 이해
```c
#include <stdio.h>

void foo(int* a) { // * 포인터 밸류 생성 CallByValue
	printf("%p\n", &a);
	*a = 88; // 
}

int main() {
	int x = 77; // main 함수 내의 메모리 x에 77을 저장
	printf("%p\n", &x); // x의 주소 값을 출력
	printf("%d\n", x);
	foo(&x); // &(엔퍼센트) 포인터 역참조 CallByAdress
	printf("%d\n", x);
}
```

## 랜덤 함수

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

## swap() 함수를 활용하여 매개변수로 전달된 두 수를 교환
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

## 명령형 매개변수를 활용하여 사칙연산을 구현 
### if문
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

### switch 문
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
        case '+': c = a + b;
	break;
        case '-': c = a - b;
	break;
        case '*':c = a * b;
	break;
        case '/': c = a / b;
	break;
        default:
	break;
    }
    printf("%d\n", c);
    return 0;
}
```

## 자료구조의 종류 
#### 배열(Array) 
#### 연결 리스트(Linked List) 
#### 스택(Stack) 
#### 큐(Queue)
#### 트리(Tree)
#### 해시 테이블(Hash Table)
## 알고리즘의 종류
#### 정렬, 탐색, 재귀, 동적계획법, 그래프, 백트래킹
