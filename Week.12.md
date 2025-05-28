### argc, argv의 응용
```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char* argv[]) {
    if (argc < 3) exit(0);
    printf("%s %s %s\n", argv[1], argv[2], argv[3]);
    
    int a = atoi(argv[1]);
    int b = atoi(argv[3]);
    int c;
    switch (argv[2][0]) {
    case '+':c = a + b;
        break;
    case '-':c = a - b;
        break;
    case '*':c = a * b;
        break;
    case '/':c = a / b;
        break;
    default:
        break;
    }
    if (argv[2][0] == '+')
        printf("%d\n", a + b);
    if (argv[2][0] == '-')
        printf("%d\n", a - b);
    if (argv[2][0] == '*')
        printf("%d\n", a * b);
    if (argv[2][0] == '/')
        용
```c
#include <stdio.h>
#include <memory.h>

#define N 5

void Pr(int v[]) {
	for (int i = 0;i < N;i++)
		printf("%d ", v[i]);
}
void swap(int* a, int* b) {
	int t = *a;
	*a = *b;
	*b = t;

}
int main() { // 버블 정렬 -> 큰 수를 뒤로 보내기
	int v[] = { 3,1,5,2,4, }, t;

	for (int i = 0;i < N - 1;i++) {
		for (int j = 0;j < N - 1 - i;j++) {
			if (v[j] > v[j + 1]) { // 값 교환
				swap(&v[j], &v[j + 1]);
			}
		}
	}
	Pr(v);
	return 0;
}
```
### 2차원 배열 
```c
#include <stdio.h>

int main() {
	int v[2][3] = { {1,2,3},{4,5,6} };
	int i, j;
	for (i = 0;i < 2;i++) {
		for (j = 0;j < 3;j++) {
			printf("%2d ", v[i][j]);
		}
		printf("\n");
	}
}
```

### 2차원 배열 - 함수처리
```c
#include <stdio.h>

void foo(int v[][3]) {
	int i, j;
	for (i = 0;i < 2;i++) {
		for (j = 0;j < 3;j++) {
			printf("%2d ", v[i][j]);
		}
		printf("\n");
	}
}
int main() {
	int v[][3] = { {1,2,3},{4,5,6} };
	foo(v); // v == &v[0][0]
}
```

### swap 함수를 통한 교체 - 정수
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
	int t;
	printf("%d %d\n", a, b);
	swap(&a, &b);
	printf("%d %d\n", a, b);
}
```

### swap함수를 통한 교체 - 배열
```c
#include <stdio.h>

void swap(int v[]) {
	int t;
	t = v[0];
	v[0] = v[1];
	v[1] = t;

	return;
}
int main() {
	int v[] = { 3,5 };
	printf("%d %d\n", v[0], v[1]);
	swap(v);
	printf("%d %d\n",v[0], v[1]);
}
```

### 버블 정렬
```c
#include <stdio.h>
#define N 5

void Pr(int v[]) {
	for (int i = 0;i < N;i++)
		printf("%d ", v[i]);
}
int main() { // 버블 정렬 -> 큰 수를 뒤로 보내기
	int v[] = { 3,1,5,2,4, }, t;

	for (int i = 0;i < N - 1;i++) {
		for (int j = 0;j < N - 1 - i;j++) {
			if (v[j] > v[j + 1]) { // 값 교환
				t = v[j];
				v[j] = v[j + 1];
				v[j + 1] = t;
			}
		}
	}
	Pr(v);
	return 0;
}
```

### 버블 정렬 - swap함수
```c
#include <stdio.h>

#define N 5

void Pr(int v[]) {
	for (int i = 0;i < N;i++)
		printf("%d ", v[i]);
}
void swap(int* a, int* b) {
	int t = *a;
	*a = *b;
	*b = t;

}
int main() { // 버블 정렬 -> 큰 수를 뒤로 보내기
	int v[] = { 3,1,5,2,4, }, t;

	for (int i = 0;i < N - 1;i++) {
		for (int j = 0;j < N - 1 - i;j++) {
			if (v[j] > v[j + 1]) { // 값 교환
				swap(&v[j], &v[j + 1]);
			}
		}
	}
	Pr(v);
	return 0;
}
```
