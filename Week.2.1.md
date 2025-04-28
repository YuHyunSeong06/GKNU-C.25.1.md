# 입력과 출력 자료형
```c
#include <stdio.h> // 전처리 함수  

int main() //printf: 화면에 출력하기 scanf: 키보드로부터 입력받기 
{
	// int : 정수 float : 소수점 나타내기  double : 실수
	float a, b, c, r; 
	printf("a:");
	scanf("%f", &a); // %d는 정수 표시,%f는 실수 표시 %lf는 실수 표시 
	printf("b:");
	scanf("%f", &b); //&앤퍼센트: 주소지 
	printf("c:");
	scanf("%f", &c);
	 
	r = a + b + c;
	printf("%f",r);
}
```

# 상수 선언과 배열, 함수 선언
```c
#include <stdio.h>  // 전처리함수 standard input output.header 
					// #은 전처리부호로 컴파일시 선행됨
#define PI=3.141592 // 상수 PI 정의 
					// 파일이름, 변수이름, 배열이름, 구조체이름, 함수이름은 우리가 자유롭게 설정가능
					// 작명규칙: 첫 글자는 무조건 영어 대소문자, 숫자는
int Add(int x, int y) // 함수 Add 작성 
{
	return (x+y); // 함수 Add는 덧셈 연산자 선언
}
int main() // 배열, index 
{
	int r, a[2]={2,3}; // a = a[0], b = a[1]
	r = Add(a[0], a[1]);
	printf("%d", r);
} 
```
