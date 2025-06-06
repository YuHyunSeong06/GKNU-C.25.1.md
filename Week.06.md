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

# Other

## 함수 선언 3개의 변수

```c
#include <stdio.h>

double Add(double a, double b,double c) {
	double s = a + b + c;
	return s;
}

int main() {
	double a = 1.1, b = 2.2, c = 3.3;
	double s = Add(a, b, c);
	printf("%lf\n", s);
}
```

## system 함수를 이용한 다양한 프로그램 실행

```c
#include <stdio.h>

int main() {
	system("mspaint.exe"); // 그림판 실행
	system("notepad.exe"); // 메모장 실행
	system("dir"); // 디렉토리 실행
}
```

# random 함수

#### 사용된 함수 rand(), srand(), time()

##### 주사위를 1000번 던졌을때 각각 나오는 눈의 개수
```c
// 기말 시험 1번 문항!!

#include <stdio.h>
#include <time.h>

// rand 함수는 무작위 수를 추출한다

int main() {
	int i;
	int h[6] = { 0,0,0,0,0,0 };

	srand(time(NULL)); // 

	for (i = 1; i <= 1000;i++) { // 범위
		h[rand() % 6]++;
	}
	for (i = 0;i < 6;i++) {
		printf("[%d]=%d\n", i, h[i]);
	}
}
```

##### 주사위를 던졌을때 확률 구하기

```c
#include <stdio.h>
#include <time.h>
#define NUM 10000

// rand 함수는 무작위 수를 추출한다

int main() {
	int i;
	int h[6] = { 0,0,0,0,0,0 };

	srand(time(NULL)); // 

	for (i = 1; i <= NUM;i++) { // 범위
		h[rand() % 6]++;
	}
	for (i = 0;i < 6;i++) {
		printf("[%d]=%f\n", i+1, (float)h[i]*100./NUM);
	}
}
```

# 그래픽스

#### 그래픽스중 openGL인 raylib 라이브러리를 통해 원 그리기
#### 창을 하나로 바꾸는 법:
#### 프로젝트 -> 속성 -> 링커 -> 시스템 -> 하위 시스템 : 창 (/SUBSYSTEM:WINDOWS) -> 고급 -> 진입점 : mainCRTStartup

### 기본 창에 원 그리기
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

### 마우스를 따라 원그리기

```c
#include "raylib.h"

// 변수나 함수명에 '!'를 적을시 0 을 1 으로 1 을 0으로 바꾼다.
int main() {
	Vector2 m = { 320,240 }; // 구조체로 되어진 값 m.x와 m.y가 각각 값을 가진다

	InitWindow(640, 480, "ANU"); // 크기가 가로 640, 세로 480 이름이 ANU인 창 생성

	while (!WindowShouldClose()) { // WindowShouldClose가 아니면 반복한다 ( X 표시 누르기 전까지 반복)
		BeginDrawing();
		m = GetMousePosition(); // 마우스의 위치에 따라 m값이 변화한다.

		DrawCircle(m.x, m.y, 16, MAGENTA); // 원을 ( 좌표값, 좌표값, 크기, 색상)으로 그림 ( 320, 240 좌표에 150의 핑크색 원을 그린다.)
		EndDrawing();
	}
	CloseWindow();
}
```

### 클릭할 시에 그려지는 원 그리기

```c
#include "raylib.h"

// 변수나 함수명에 '!'를 적을시 0 을 1 으로 1 을 0으로 바꾼다.
int main() {
	InitWindow(640, 480, "ANU"); // 크기가 가로 640, 세로 480 이름이 ANU인 창 생성

	while (!WindowShouldClose()) { // WindowShouldClose가 아니면 반복한다 ( X 표시 누르기 전까지 반복)
		BeginDrawing();

		if (IsMouseButtonDown(MOUSE_LEFT_BUTTON)) {
			Vector2 m = GetMousePosition(); // m의 값을 마우스의 위치에 따라 설정한다
			DrawCircle(m.x, m.y, 16, MAGENTA); // 원을 ( 좌표값, 좌표값, 크기, 색상)으로 그림 ( 320, 240 좌표에 150의 핑크색 원을 그린다.)
		}
		EndDrawing();
	}
	CloseWindow();
}
```

### 계속 낙하하는 원 그리기

```c
#include "raylib.h"

// 변수나 함수명에 '!'를 적을시 0 을 1 으로 1 을 0으로 바꾼다.
int main() {
	Vector2 m = { 320,240 }; // 구조체로 되어진 값 m.x와 m.y가 각각 값을 가진다

	InitWindow(640, 480, "ANU"); // 크기가 가로 640, 세로 480 이름이 ANU인 창 생성

	while (!WindowShouldClose()) { // WindowShouldClose가 아니면 반복한다 ( X 표시 누르기 전까지 반복)
		BeginDrawing();
		m = GetMousePosition(); // 마우스의 위치에 따라 m값이 변화한다.

		DrawCircle(m.x, m.y, 16, MAGENTA); // 원을 ( 좌표값, 좌표값, 크기, 색상)으로 그림 ( 320, 240 좌표에 150의 핑크색 원을 그린다.)
		EndDrawing();
	}
	CloseWindow();
}
```

### 사각형 안에 원 그리기

```c
#include "raylib.h"

int main() {
	InitWindow(320, 240, "HI");
	while (!WindowShouldClose()) {
		BeginDrawing();
		DrawRectangle(20, 20, 280, 200, VIOLET); // 사각형 그리기
		DrawEllipse(160, 120, 140, 100, BLUE); // 사각형 안에 원 그리기
		EndDrawing();
	}
	CloseWindow();
}
```

### 원 3개 그리기

```c
#include "raylib.h"

int main() {
	InitWindow(640, 480, "HI");
	while (!WindowShouldClose()) {
		BeginDrawing();
		DrawCircle(320, 40, 200, RED);
		DrawCircle(120, 120, 200, GREEN);
		DrawCircle(480, 360, 200, BLUE);
		EndDrawing();
	}
	CloseWindow();
}
```
