# 축약연산자의 이해 증감
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

# 메모리에 값 저장에 대한 이해, 작명규칙
```c
#include<stdio.h>

int main() {
	int a_1, b_1, s_1; // 메모리에 정수 변수를 선언
	a_1 = 2; // 작명규칙으로 인해 첫 글자에는 무조건 영어 or _
	b_1 = 3;
	s_1 = a_1 + b_1;
	printf("%d\n", s_1);
}
```

# if else문 구현
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

# for문을 이용한 무한반복복
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

# case문을 통한 성적분류
```c
#include <stdio.h>

void main() {
	int a;
	char c;
	while(1) { // 무한반복 조건이 없기 때문
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

# while문을 통한 무한 반복 두 수를 입력받아 두 수가 모두 0이면 멈춘다다
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

# 함수를 이용한 덧셈
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

# my.txt에 22와 3을 적기기
```c
#include <stdio.h>

int main() {
	FILE* fp = fopen("my.txt", "w"); // FILE 주소를 fp로 설정 my.txt 파일을 write 모드로 오픈
	fprintf(fp, "22\n33"); // 파일 fp에다가 22와 33을 출력
	fclose(fp); // 파일 닫기
}
```

# my.txt를 읽고 두 수를 더하기
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

# 함수와 배열의 응용
```c
#include <stdio.h>

int Add(int v[2]) { // 함수 Add의 매개변수를 배열로 선언
	return v[0] + v[1];
}

int main() {
	int v[2] = { 2,3 }; // 배열 v[0]을 2 v[1]을 3으로 지정
	printf("%d\n", Add(v)); // 함수를 통해 배열을 호출 시에 배열 이름을 적는다
}
```

# for문을 이용한 1부터 100까지 수의 짝수 구분
```c
#include <stdio.h>

int main() {
	int a, sum = 0;
	for (a = 1;a < 101;a++) { // for 문의 구조 for(초기값; 범위; 증감값)
				// 1부터 100까지 반복
		if (a % 2 == 0) { // 짝수 판별 조건
			sum += a;
		}
	}
	printf("%d\n", sum);
}
```

# for 문을 통한 2단부터 9단까지 출력력
```c
#include <stdio.h>

int main() {
	int p, q;
	for (p = 2;p < 10;p++) { // 2단부터 9단까지
		printf("\n"); // 단이 바뀔때마다 엔터
		for (q = 1;q < 10;q++) { // 1부터 9까지 곱하는값
			printf("%d ", p * q); 출력
		}
	}
}
```

# if 문을 통한 양수, 0, 음수 구분
```c
#include<stdio.h>

int main() {
	int a;
	do {
		scanf_s("%d", &a); // a 를 입력받기
		if (a > 0) { // 조건에 충족할 경우 아래 내용 실행
			printf("a는 양수\n");
		}
		else { // if 문을 만족하지 못한경우 else 내용 실행
			if (a == 0) {
				printf("a는 0");
			}
			else printf("a는 음수");
		}
		printf("%d\n", a);
	} while (1); // 무한반복
}
```

# 1부터 10까지를 반복할때 continue의 이해해
```c
#include<stdio.h>

int main() {
	int i, s=0; 
	for (i = 1;i <= 10;i++) {// for 문의 구조 for(초기값; 범위; 증감값)
		if (i == 5)break; // break는 반복문의 코드를 즉시 종료한다.
		if (i == 3)continue; // countinue는 밑의 코드를 실행하지 않고 반복문의 처음으로 간다.
		s = s + i;
	}
	printf("%d\n",s); 
}
```

# while 문을 이용한 1부터 10의 합
```c
#include <stdio.h>

int main() {
	int i = 0, s = 0;
	while (i <= 10){
		s = s + i;
		printf("i=%d, s=%d\n", i, s);
		getchar(); // getchar는 내가 엔터키를 치기까지 기다린다
		i = i + 1;
	}
	printf("%d\n", s);
	return 0;
}
```
