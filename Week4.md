```c
#include <stdio.h>

void main() {
	int abc = 5;
	printf("%d\n", abc); // 5
	printf("%d\n", abc++); // 5
	printf("%d\n", abc); // 6
	printf("%d\n", abc++); // 6

}
```

```c
#include<stdio.h>

int main() {
	int a_1, b_1, s_1; // 메모리에 정수 변수를 선언
	a_1 = 2;
	b_1 = 3;
	s_1 = a_1 + b_1;
	printf("%d\n", s_1);
}
```

```c
#include <stdio.h>

void main() {
	int a = 2, b = 3;
	if (a > b) { // 비교 연산자는 1 or 0
		printf("a가 b보다 크다\n");
	}
	else {
		printf("a가 b보다 작다\n");
	}
}
```

```c
#include <stdio.h>

void main() {
	int a;
	for(;;){ // 무한반복 초기값, 범위, 증감값 모두 없기때문
		scanf_s("%d", &a);
		a = a / 10;
		switch (a) {
			case 9:printf("%c\n", 'A'); // 값이 9면 A출력
				break; // case 문 뒤에는 항상 break를 적는다
			case 8:printf("%c\n", 'B'); // 값이 8면 B출력
				break;
			default: printf("%c\n", 'F'); // 다른 경우 F출력
				break;
		}
	}	
}
```

```c
#include <stdio.h>

void main() {
	int a;
	char c;
	while(1) { // 무한반복 범위가 없기 때문
		scanf_s("%d", &a);
		a = a / 10;
		switch (a) {
		case 10:c = 'A+';
			break;
		case 9: c = 'A';
			break;
		case 8:c = 'B';
			break;
		default: c = 'F';
			break;
		}
		printf("%c\n", c); // switch 문이 끝난 뒤에 c값이 출력
	}

}
```

```c
#include <stdio.h>

void main() {
	int a, b;
	while (1) { // 무한 반복
		scanf_s("%d%d", &a, &b); // a값, b값 입력받음
		printf("%d\n", a + b); 
		if (a == 0 && b == 0)
			break; // if문 괄호 내의 범위가 맞을 시에 if문 break 실행
	}
}
```

```c
#include <stdio.h>

int Add(int a, int b) { // 함수 구조: 반환형 함수명(매개변수){return 함수내용;}
	return (a + b); // 함수 내용
}

void main() {
	int a = 2, b = 3; // 변수 선언
	printf("%d\n", Add(a, b)); // 출력
}
```

```c
#include <stdio.h>

int main() {
	FILE* fp = fopen("my.txt", "w"); // FILE 주소를 fp로 설정 my.txt 파일을 write 모드로 오픈
	fprintf(fp, "22\n33"); // 파일 fp에다가 22와 33을 출력
	fclose(fp); // 파일 닫기
}
```

```c
#include <stdio.h>

int main() {
	int a, b; // 변수 선언
	FILE* fp = fopen("my.txt", "r"); // my.txt 파일을 read 모드로 오픈
	fscanf_s(fp, "%d%d", &a, &b); // 파일에 있는 두수를 a, b로 대입
	fclose(fp); // 파일 닫기
	printf("%d\n", a + b); // 출력
}
```

```c
#include <stdio.h>

int Add(int v[2]) { // 함수 Add의 매개변수를 배열로 선언
	return v[0] + v[1];
}

int main() {
	int v[2] = { 2,3 };
	printf("%d\n", Add(v));
}
```

```c
#include <stdio.h>

int main() {
	int a, sum = 0;
	for (a = 1;a < 101;a++) {
		if (a % 2 == 0) {
			sum += a;
		}
	}
	printf("%d\n", sum);
}
```

```c
#include <stdio.h>

int main() {
	int a, sum = 0;
	for (a = 1;a < 101;a++) {
		if (a % 2 == 0) {
			sum += a;
		}
	}
	printf("%d\n", sum);
}
```

```c
#include <stdio.h>
#include <stdio.h>

int main() {
	int p, q;
	for (p = 2;p < 10;p++) {
		printf("\n");
		for (q = 1;q < 10;q++) {
			printf("%d ", p * q);
		}
	}
}
```
