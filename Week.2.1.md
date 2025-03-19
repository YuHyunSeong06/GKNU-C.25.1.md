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
