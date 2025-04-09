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
