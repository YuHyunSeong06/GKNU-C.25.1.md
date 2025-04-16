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
