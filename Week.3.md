# Add함수를 이용한 두 수의 덧셈
```c
#include <stdio.h>

int Add(int a, int b) {
    return a + b;
}
int main()
{
    int a = 2, b = 3, c;
    c = Add(a, b);
    printf("%d\n", c);
}
```

# Add 함수의 배열 응용, 상수 NUM 설정, for문을 통한 반복
```c
#include <stdio.h>
#define NUM 2

int Add(int v[NUM]) {
    int i, s = 0;
    for (i = 0;i < NUM;i++) {
        s = s + v[i];
    }
    return s;
}
int main()
{
    int v[NUM] = { 4,5 };
    printf("%d\n", Add (v));
}
```

# while 문을 통한 반복 if를 이용한 홀수 짝수 구분
```c
#include <stdio.h>

int main() {
	int i = 1;
	while (i<=10) {
		if((i%2)!=0){
			printf("%d ", i);
			i=i+1;
			}
	}
}
```

# for문을 통한 조건 반복 1부터 10까지 2와 3의 배수 찾기
```c
#include<stdio.h>
int main() {
	for (int i = 1;i <= 10;i++) {
		if (i % 3 == 0 || i % 2 == 0) {
			printf("%d ", i);
		}
	}
}
```

# 두 값을 입력받아 덧셈
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main() {
	int a, b;
	puts("Two value: ");
	scanf("%d %d", &a, &b);
	printf("%d\n", a + b);
}
```

# 함수를 이용한 배열의 덧셈(2)
```c
#include <stdio.h>

int Add(int v[2]) {
	return v[0] + v[1];
}
int main() {
	int v[] = { 11,22 };
	printf("%d\n", Add(v));
}
```

# for문을 통한 반복 전역변수를 통한 변수 초기화
```c
#include <stdio.h>

int s = 0; // 전역변수, 자동 0
int main() {
	int i; // 지역변수
	for (i = 1;i <= 1000;i++) {
		s = s + i;
		printf("%d ", s); //getchar();
	}
}
```

# 함수와 배열을 이용한 덧셈(3)
```c
#include <stdio.h>

int Add(int v[2]) {
	return v[0] + v[1];
}
int main() {
	int v[] = { 2,3 };
	printf("%d", Add(v));
}
```

# raylib를 이용한 원 생성성
```c
#include "raylib.h"
int x=0, y=0;
int main(void)
{
    InitWindow(800, 600, "GKNU");
    SetTargetFPS(60);
    while (!WindowShouldClose())  // ESC 또는 창 닫힘 이벤트 감지
    {
        BeginDrawing();
        ClearBackground(RAYWHITE);      // 배경을 흰색으로 초기화 (없으면 깜빡일 수 있음)
        DrawCircle(x++,y++, 150, GREEN);  // 초록 원 (x=400, y=300, 반지름=150)
        EndDrawing();
        if (x>800||y > 600) {
            x,y = 0;
        }
    }
    CloseWindow();  // 창 닫기
}
```

# raylib를 이용한 블록깨기
```c
#include "raylib.h"

#define MAX_BLOCKS 36

int main() {
    InitWindow(800, 600, "Block");
    SetTargetFPS(60);

    // 패들과 공
    Rectangle paddle = { 350, 550, 100, 20 };
    Vector2 ball = { 400, 300 };
    Vector2 speed = { 5, -5 };
    float radius = 10;

    // 블록들
    Rectangle blocks[MAX_BLOCKS];
    Color colors[6] = { RED, ORANGE, YELLOW, GREEN, BLUE, PURPLE };
    bool active[MAX_BLOCKS] = { 0 };
    for (int i = 0; i < MAX_BLOCKS; i++) {
        blocks[i] = (Rectangle){ 20 + (i % 12) * 63, 50 + (i / 12) * 30, 60, 20 };
        active[i] = true;
    }

    while (!WindowShouldClose()) {
        // 패들 이동
        if (IsKeyDown(KEY_LEFT)) paddle.x -= 8;
        if (IsKeyDown(KEY_RIGHT)) paddle.x += 8;

        // 공 이동
        ball.x += speed.x;
        ball.y += speed.y;

        // 벽 충돌
        if (ball.x < radius || ball.x > 800 - radius) speed.x *= -1;
        if (ball.y < radius) speed.y *= -1;

        // 바닥
        if (ball.y > 600) ball = (Vector2){ 400, 300 };

        // 패들 충돌
        if (CheckCollisionCircleRec(ball, radius, paddle)) speed.y *= -1;

        // 블록 충돌
        for (int i = 0; i < MAX_BLOCKS; i++) {
            if (active[i] && CheckCollisionCircleRec(ball, radius, blocks[i])) {
                active[i] = false;
                speed.y *= -1;
                break;
            }
        }

        // 그리기
        BeginDrawing();
        ClearBackground(BLACK);
        DrawRectangleRec(paddle, WHITE);
        DrawCircleV(ball, radius, WHITE);
        for (int i = 0; i < MAX_BLOCKS; i++)
            if (active[i]) DrawRectangleRec(blocks[i], colors[i / 12]);
        EndDrawing();
    }

    CloseWindow();
    return 0;
}
```
