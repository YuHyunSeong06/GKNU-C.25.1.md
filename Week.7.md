# 포인터

#### 기본 문제
```c
#include <stdio.h>

int main() {
	int val = 77;
	int* p = &val;
	printf("val = %d\n", *p);
	return 0;
}
```

```c
#include <stdio.h>

void foo(int x) {
	printf("%p\n", &x); // x 의 주소값을 출력
	x = 88; // 
}

int main() {
	int x = 77; // main 함수 내의 메모리 x에 77을 저장
	printf("%p\n", &x); // main 함수의 x의 주소 값을 출력
	printf("%d\n", x); // x 값을 출력
	foo(x); // foo 함수의 x 주소를 출력
	printf("%d\n", x); 
}
```

```c
#include <stdio.h>

void foo(int* a) { // * 포인터 밸류 생성 CallByValue
	printf("%p\n", &a);
	*a = 88; // 
}

int main() {
	int x = 77; // main 함수 내의 메모리 x에 77을 저장
	printf("%p\n", &x); // x의 주소 값을 출력
	printf("%d\n", x);
	foo(&x); // &(엔퍼센트) 포인터 역참조 CallByAdress
	printf("%d\n", x);
}
```

# 문자열

### 문자열은 문자열의 끝을 표시하기 위해 '\0' 을 표시하는데 같은 말로 'NULL'이 있다.
```c
#include <stdio.h>
 
char n[14] = "Yuhyun Seong"; // 문자열 n의 크기를 14로 설정 "Yuhyun Seong"을 문자열 n 에 담음

int main(){
	printf("%s", n);
	printf("%c", n[0]); // 한 글자만을 출력
}
```

### ASCII 코드 16 진수 사용
### 숫자 1과 문자 0은 다르다
### Value = Hex
#### NULL = 0 
#### 1 = 31
#### A = 41
```c
#include <stdio.h>

// 문자 1과 숫자 1은 다르다.

char n[14] = "GKNU"; // n[0] n[1] n[2] n[3] n[4] NULL=='\0'
//                       G    K    N    U    \0
int main() {
	printf("%s", n);
	printf("%x", n[1]); // ASCII 코드의 Hex값을 출력한다.
}
```
