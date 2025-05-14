# 구조체

#### 구조체: 서로 다른 자료형을 하나로 묶어주는 사용자 정의 자료형
#### 다양한 데이터 묶음 표현에 사용

### 기초 구조체 문항
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

### 학번과 점수 출력
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

### 구조체와 포인터
```c
#include <stdio.h>

typedef struct Num {
	int a, b;
}Num;

int main() {
	Num x = {2,3};
	Num* p = &x;
	printf("%d %d\n", p->a, p->b);
}
```

### 기말고사 출제 문항
##### 파일 적기
```c
#include <stdio.h>

typedef struct Num {
	int a, b;
}Num;

int main() {
	Num x = { 2,3 };
	FILE* fp = fopen("my.bin", "wb");
	fwrite(&x, sizeof(Num), 1, fp); // 배열이 아닐시 &(주소를 적어줘야함)
  fclose(fp);
	printf("%d %d\n", x.a, x.b);
}
```
##### 파일 읽기
```c
#include <stdio.h>

typedef struct Num {
	int a, b;
}Num;

int main() {
	Num x;
	Num x = { 2,3 };
	FILE* fp = fopen("my.bin", "rb");
	fread(&x, sizeof(Num), 1, fp); // 배열이 아닐시 &(주소를 적어줘야함)
	fclose(fp);
	printf("%d %d\n", x.a, x.b);
}
```

### 구조체와 배열
```c
#include <stdio.h>

struct User { // 구조체 선언
	int age;
	char name[20];
};

int main() {
	struct User user[2] = { // 구조체의 배열 선언
		{19,"Hyun Geon"},
		{18,"Yu Hyun"}
	};
	for (int i = 0;i < 2;i++) { // for 문을 통해 printf 문의 재사용화
		printf("Age: %d Name: %s\n", user[i].age, user[i].name);
	}
}
```

### 함수를 응용한 구조체의 배열
```c
#include <stdio.h>

struct ur {
	int age;
	char name[20];
};

void pr(struct ur me) {
	printf("%d %s\n", me.age, me.name);
}

int main() {
	struct ur me = { 18,"Yuhyun" };
	pr(me);
}
```
