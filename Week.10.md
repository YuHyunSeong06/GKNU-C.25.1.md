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
