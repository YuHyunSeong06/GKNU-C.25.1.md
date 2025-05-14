# 구조체

### 구조체: 서로 다른 자료형을 하나로 묶어주는 사용자 정의 자료형
### 다양한 데이터 묶음 표현에 사용

#### 기초 구조체 문항
```c
#include <stdio.h>

struct Student {  // 태그 네임
	int a, b;
};

int main()
{
	struct Student n = { 2,3 };

	printf("%d %d\n", n.a, n.b);
}
```

#### 학번과 점수 출력
```c
#include <stdio.h>

typedef struct Student { // 구조체 선언
	int id; 
	double grade;
}Student; // typedef를 이용한 단축

int main() {
	Student cs; // 구조체명 선언
	cs.id = 1002;
	cs.grade = 85.5;
 // Stud me = { 1002,85.5 };로 단축 가능
	printf("ID: %d, Score: %.1lf\n", cs.id, cs.grade); // 출력 주소 : 구조체명.변수이름
}
```
