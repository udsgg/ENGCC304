
## โจทย์
จงเขียนโปรแกรมทายตัวเลขซึ่งทำงานดังนี้
- ตอนเริ่มเกมผู้เล่นจะมีคะแนนเต็ม 100
- โปรแกรมจะสุ่มตัวเลขที่มีค่าตั้งแต่ 1 ถึง 100
- ให้ผู้เล่นทายว่าตัวเลขที่โปรแกรมสุ่มมามีค่าเป็นเท่าใด
- หากทายผิด โปรแกรมจะลบคะแนนของผู้เล่นไป 10 หน่วย พร้อมแจ้งคะแนนปัจจุบันให้ผู้เล่นทราบด้วย
- หากทายผิด โปรแกรมจะต้องบอกใบ้ว่าคำตอบที่ถูกมีค่า "มากกว่า" หรือ "น้อยกว่า" ตัวเลขที่ผู้ใช้ทาย
- หากทายผิด ให้โปรแกรมรอรับตัวเลขถัดไปได้เลย
- หากทายถูก ให้โปรแกรมแสดงความยินดีกับผู้ใช้ พร้อมแจ้งคะแนนปัจจุบันให้กับผู้เช่น
- เมื่อเล่นเสร็จโปรแกรมรอรับคำสั่งจากผู้ใช้ หากผู้ใช้กรอกเลข 1 จะเข้าสู่โหมดการเล่นเกมใหม่อีกครั้ง หากกด -1 ให้หยุดการทำงานของโปรแกรม

<br />หมายเหตุ : การสุ่มตัวเลขจะใช้คำสั่ง rand() ที่อยู่ใน stdlib.h หากต้องการสุ่มตัวเลข 0 ถึง 100 ต้องใช้คำสั่งดังนี้
```c++
rand() % 100 + 1
```
<br />หมายเหตุ : หากต้องการสุ่มตัวเลขที่เปลี่ยนแปลงตามเวลา ต้องใช้คำสั่ง srand( time( NULL ) ) ในตอนต้นของโปรแกรมด้วย
```c++
srand( time( NULL ) ) ;
```

## FIX CODE
```c++
#include <stdlib.h>
```

## FIXED CODE

```c++
#include <stdlib.h>
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

void playGame() {
    int target = rand() % 100 + 1;
    int score = 100;
    int guess;
    int lower = 1;
    int upper = 100;

    cout << "\n(Score=100)\n";

    while (true) {
        cout << "\nGuess the winning number (" << lower << "-" << upper << ") : ";
        cin >> guess;

        if (cin.fail()) {
            cin.clear();
            cin.ignore(10000, '\n');
            cout << "Please enter a valid number.\n";
            continue;
        }

        if (guess == target) {
            cout << "\nScore this game: " << score << "\n";
            cout << "That is correct! The winning number is " << target << ".\n";
            break;
        } else {
            score -= 10;

            if (score <= 0) {
                cout << "Score is 0. Game over!\n";
                break;
            }

            if (guess < target) {
                cout << "\nSorry, the winning number is HIGHER than " << guess << ". (Score=" << score << ")";
                if (guess + 1 > lower)
                    lower = guess + 1;
            } else {
                cout << "\nSorry, the winning number is LOWER than " << guess << ". (Score=" << score << ")";
                if (guess - 1 < upper)
                    upper = guess - 1;
            }
        }
    }
}

int main() {
    srand(time(0));
    int choice;

    while (true) {
        cout << "\n\nDo you want to play game (1=play,-1=exit) :\n";
        cin >> choice;

        if (cin.fail()) {
            cin.clear();
            cin.ignore(10000, '\n');
            cout << "Please enter 1 or -1.\n";
            continue;
        }

        if (choice == 1) {
            playGame();
        } else if (choice == -1) {
            cout << "\nSee you again.\n";
            break;
        } else {
            cout << "Please enter 1 to play or -1 to exit.\n";
        }
    }

    return 0;
}
```

## FLOWSHART
![game](https://github.com/user-attachments/assets/d3d7d634-b162-468b-8955-f3a5ddb6189f)



## TEST CASE
### Input & Output
```bash
Do you want to play game (1=play,-1=exit) :
1

(Score=100)

Guess the winning number (1-100) : 12

Sorry, the winning number is HIGHER than 12. (Score=90)
Guess the winning number (13-100) : 23

Sorry, the winning number is HIGHER than 23. (Score=80)
Guess the winning number (24-100) : 56

Sorry, the winning number is HIGHER than 56. (Score=70)
Guess the winning number (57-100) : 69

Sorry, the winning number is HIGHER than 69. (Score=60)
Guess the winning number (70-100) : 78

Sorry, the winning number is HIGHER than 78. (Score=50)
Guess the winning number (79-100) : 89

Sorry, the winning number is HIGHER than 89. (Score=40)
Guess the winning number (90-100) : 98

Sorry, the winning number is LOWER than 98. (Score=30)
Guess the winning number (90-97) : 96

Sorry, the winning number is LOWER than 96. (Score=20)
Guess the winning number (90-95) : 93

Sorry, the winning number is HIGHER than 93. (Score=10)
Guess the winning number (94-95) : 94

Score this game: 10
That is correct! The winning number is 94.


Do you want to play game (1=play,-1=exit) :

```



