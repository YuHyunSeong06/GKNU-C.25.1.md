# 포인터

#### 포인터는 메모리의 주소를 나타내는 변수다. 포인터는 (자료형)* 식으로 선언된다. * 을 어디에 붙여도 상관은 없지만 자료형 뒤에 적는것이 일반적이다.
#### 
```c
#include <stdio.h> // c언어는 2가지 방법으로 컴파일함 #(전처리부호)부터 '프리 컴파일' 한다

// val 메모리에 88을 담고 포인터 p를 선언한다. p를 val의 주소로 초기화하고 주소값과 val의 값, p의 주소의 값을 출력한다.

int main() { // 함수의 시작 { 
	int val = 88;
	int* p; // 포인터 선언 
	p = &val; // 포인터의 초기화
	// *p = 11; <- 포인터의 값을 설정한다.

	printf("%p\n", &val); // val의 주소값 출력
	printf("%d\n", val);
	printf("%d\n", *p); // *p는 포인터가 지정하는 주소의 값
} // 함수의 끝 }
```

# 그래픽스

#### 그래픽스중 openGL인 raylib 라이브러리를 통해 원 그리기
#### 창을 하나로 바꾸는 법:
#### 프로젝트 -> 속성 -> 링커 -> 시스템 -> 하위 시스템 : 창 (/SUBSYSTEM:WINDOWS) -> 고급 -> 진입점 : mainCRTStartup
```c
#include "raylib.h"

// 변수나 함수명에 '!'를 적을시 0 을 1 으로 1 을 0으로 바꾼다.
int main() {
	InitWindow(640, 480, "ANU"); // 크기가 가로 640, 세로 480 이름이 ANU인 창 생성
	while (!WindowShouldClose()) { // WindowShouldClose가 아니면 반복한다 ( X 표시 누르기 전까지 반복)
		BeginDrawing(); 
		DrawCircle(640 / 2, 480 / 2, 150, MAGENTA); // 원을 ( 좌표값, 좌표값, 크기, 색상)으로 그림 ( 320, 240 좌표에 150의 핑크색 원을 그린다.)
		EndDrawing();
	}
	CloseWindow();
}
```
