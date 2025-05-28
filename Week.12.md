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
        printf("%d\n", a / b);

    return 0;
}
```
### 2차원 배열열
```c
#include <stdio.h>

void foo(int v[][3]) 렬
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
