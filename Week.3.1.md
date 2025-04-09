```c
#include <stdio.h>

int Add(int a, int b) {
    return a + b;
}
int main()
{
    int a = 2, b = 3, c;
    c = Add(a, b);
    printf("%d\n", c);
}
```

```c
#include <stdio.h>
#define NUM 2

int Add(int v[NUM]) {
    int i, s = 0;
    for (i = 0;i < NUM;i++) {
        s = s + v[i];
    }
    return s;
}
int main()
{
    int v[NUM] = { 4,5 };
    printf("%d\n", Add (v));
}
```

```c
#include <stdio.h>

int main() {
	int i = 1;
	while (i<=10) {
			if((i%2)!=0){
			printf("%d ", i);
			 i=i+1;
			}
	}
}
```

```c
#include<stdio.h>
int main() {
	for (int i = 1;i <= 10;i++) {
		if (i % 3 == 0 || i % 2 == 0) {
			printf("%d ", i);
		}
	}
}
```

```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main() {
	int a, b;
	puts("Two value: ");
	scanf("%d %d", &a, &b);
	printf("%d\n", a + b);
}
```

```c
#include <stdio.h>

int Add(int v[2]) {
	return v[0] + v[1];
}
int main() {
	int v[] = { 11,22 };
	printf("%d\n", Add(v));
}
```

```c
#include <stdio.h>

int s = 0; // 전역변수, 자동 0
int main() {
	int i; // 지역변수
	for (i = 1;i <= 1000;i++) {
		s = s + i;
		printf("%d ", s); //getchar();
	}
}
```

```c
#include <stdio.h>

int Add(int v[2]) {
	return v[0] + v[1];
}
int main() {
	int v[] = { 2,3 };
	printf("%d", Add(v));
}
```
