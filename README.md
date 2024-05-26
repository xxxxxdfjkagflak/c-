#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int result[4];
    char input;

    do {
        int t = 0;
        int z = 0;

        srand(time(0));

        printf("윷을 던지려면 아무 키나 누르세요: ");
        scanf(" %c", &input);

        for (int i = 0; i < 4; i++) {
            result[i] = rand() % 2;
            if (result[i] == 0) {
                t++;
            }
            else {
                z++;
            }
        }

        if (z == 1 && t == 3) {
            printf("도입니다.\n");
        }
        else if (z == 2 && t == 2) {
            printf("개입니다.\n");
        }
        else if (z == 3 && t == 1) {
            printf("걸입니다.\n");
        }
        else if (z == 4) {
            printf("윷입니다. 실패입니다.\n");
            break; // 윷이 나왔을 때 게임 종료
        }
        else if (t == 4) {
            printf("모입니다.\n");
            break; // 빽도가 나왔을 때 게임 종료
        }
        else {
            printf("빽도입니다. 실패입니다.\n");
        }

        if ((z == 1 && t == 3) || (z == 2 && t == 2) || (t == 4) || (z == 3 && t == 1)) {
            printf("축하드립니다. 한 번 더 도전하시겠습니까? (Y/N): ");
            scanf(" %c", &input);
        }
        else if (z == 4) {
            printf("윷이 나와 실패입니다. 게임을 종료합니다.\n");
            break; //윷이 나왔을 때 게임 종료

            
        }
        else {
            printf("빽도가 나와 실패입니다. 게임을 종료합니다.\n");
            break; // 빽도가 나왔을 때 게임 종료
        }
    } while (input == 'Y' || input == 'y');

    

    return 0;
}
