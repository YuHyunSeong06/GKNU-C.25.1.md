# 포인터

### 1. 배열과 포인터
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
	int arr[3] = { 10,20,30 };
	int* p = arr; // 포인터 p의 주소를 배열 arr (주소 & 를 활용할시 정확한 배열 인덱스 첨가 &arr[0])
	printf("%d\n", *(p + 1)); // p의 주소값을 출력
	return 0;
}
```

### 2. 함수의 포인터
```c
#include <stdio.h>

int add(int a, int b) {
	return a + b;
}

int main() {
	int (*fp)(int, int) = add; // 함수를 포인터할때 자료형 (포인터명)( 자료형 자료형) = 함수명 형태인것같음 마찬가지로 주소 안붙임
	printf("%d\n", fp(3, 4)); // (*fp)형태로도 가능
	return 0;
}
```

### 3. 배열의 포인터로 과일 이름 출력
```c
#include <stdio.h>
 
int main() {
    char* arr[] = { "Apple", "Banana", "Cherry" }; // 배열의 인덱스는 초기화할때와 함수로 전달할때는 없게한다.
    printf("%s\n", arr[1]);  // Banana 출력
    return 0;
}
```

# 복습
## 반복문
#### 구구단
```c
#include <stdio.h>

int main() {
    for (int i = 2; i <= 9; i++) { // 단 수
        for (int j = 1; j <= 9; j++) // 곱하는 수
            printf("%d x %d = %d\n", i, j, i * j);
    }
    return 0;
}
```
## 배열
#### 이차원 배열
```c
#include <stdio.h>

int main() {
    int scores[2][3] = { {90, 80, 70}, {60, 50, 40} }; // 3개짜리가 2개가 있다. 뒤에가 뭉치 앞에가 묶음
    printf("%d\n", scores[1][2]);  // 40 출력
    return 0;
}
```

## 공용체(union)

#### 유니온은 모든 멤버가 메모리를 공유한다.
```c
#include <stdio.h>

union Data {
    int i;
    float f;
};
int main() {
    union Data d;
    d.i = 10;
    printf("%d\n", d.i);  // 10 출력
    return 0;
}
```

## 열거형(enum)
```c
#include <stdio.h>

enum Day { SUN, MON, TUE };

int main() {
    enum Day today = MON;
    printf("%d\n", today);  // 1 출력
    return 0;
}
```
# main함수의 argc, argv를 이용한 덧셈

```c
#include <stdio.h>    // 표준 입출력 함수(printf 등)를 사용하기 위한 헤더 파일
#include <stdlib.h>   // atoi 함수(문자열을 정수로 변환)를 사용하기 위한 헤더 파일

int main(int argc, char* argv[]) { // argc: 인자의 개수, argv: 인자 문자열 배열
    if (argc < 3) return 1;        // 인자가 3개 미만이면(프로그램 이름 + 숫자 2개가 아니면) 프로그램 종료

    int a = atoi(argv[1]);         // argv[1]에 저장된 문자열을 정수로 변환하여 a에 저장
    int b = atoi(argv[2]);         // argv[2]에 저장된 문자열을 정수로 변환하여 b에 저장

    printf("%d\n", a + b);         // 두 정수의 합을 출력

    return 0;                      // 프로그램 정상 종료
}
```
