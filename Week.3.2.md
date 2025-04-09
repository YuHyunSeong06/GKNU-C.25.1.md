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
