
## โจทย์
จงเขียนโปรแกรมรับค่าตัวเลขจากผู้ใช้ ใส่ไว้ในตัวแปร N และทำการแสดงข้อมูลดังเงื่อนไขต่อไปนี้
<br />- หากผู้ใช้กรอกเลขคี่ ให้โปรแกรมแสดงลำดับตัวเลขตั้งแต่ 1 ถึง N และให้แสดงเฉพาะตัวเลขคี่เท่านั้น
<br />- หากผู้ใช้กรอกเลขคู่ ให้โปรแกรมแสดงลำดับตัวเลขตั้งแต่ N ถึง 0 และให้แสดงเฉพาะตัวเลขคู่เท่านั้น


## FIX CODE
```c++
#include <stdio.h>

int main() {
int N;
    printf("กรุณากรอกค่าตัวเลข: ");
    
    if (scanf("%d", &N) != 1) {
        printf("Error: กรุณากรอกเฉพาะตัวเลขเท่านั้น!\n");
        return 1;  //สำหรับ eror
    }

    if (N % 2 == 1) {  // สำหรับเลขคี่
        printf("ลำดับเลขคี่จาก 1 ถึง %d:\n", N);
        for (int i = 1; i <= N; i += 2) {
            printf("%d ", i);
        }
    } else {  // สำหรับเลขคู่
        printf("ลำดับเลขคู่จาก %d ถึง 0:\n", N);
        for (int i = N; i >= 0; i -= 2) {
            printf("%d ", i);
        }
    }

    printf("\n");
    return 0;
}

```

## TEST CASE
### Input
```bash
Enter value:
27
```
![Screenshot (95)](https://github.com/udsgg/ENGCC304/blob/main/Lab06/Screenshot%202025-07-31%20110453.png)

### Output
```bash
ลำดับเลขคี่จาก 1 ถึง 27:
1 3 5 7 9 11 13 15 17 19 21 23 25 27 
```
![Screenshot (96)](https://github.com/udsgg/ENGCC304/blob/main/Lab06/Screenshot%202025-07-31%20110506.png)

## TEST CASE
### Input
```bash
Enter value:
24
```

![Screenshot (97)](https://github.com/udsgg/ENGCC304/blob/main/Lab06/Screenshot%202025-07-31%20110933.png)


### Output
```bash
ลำดับเลขคู่จาก 24 ถึง 0:
24 22 20 18 16 14 12 10 8 6 4 2 0
```


![Screenshot (98)](https://github.com/udsgg/ENGCC304/blob/main/Lab06/Screenshot%202025-07-31%20110946.png)
