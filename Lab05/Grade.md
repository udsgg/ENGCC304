## โจทย์
ผู้ใช้กรอกค่า "คะแนนดิบ" เข้ามาในระบบเพื่อต้องการตรวจสอบเกรดในรายวิชา Programming ซึ่งมีเกณฑ์การให้คะแนนคือ 
<br />F อยู่ในช่วงคะแนนน้อยกว่า 50 , 
<br />D อยู่ในช่วงระหว่าง 50 ถึง 55 , 
<br />D+ อยู่ในช่วงระหว่าง 55 ถึง 60 , 
<br />C อยู่ในช่วงระหว่าง 60 ถึง 65 , 
<br />C+ อยู่ในช่วงระหว่าง 65 ถึง 70 , 
<br />B อยู่ในช่วงระหว่าง 70 ถึง 75 , 
<br />B+ อยู่ในช่วงระหว่าง 75 ถึง 80 , 
<br />A อยู่ในช่วงคะแนนมากกว่า 80 ขึ้นไป 
<br /><br />(กำหนดให้ข้อนี้ใช้คำสั่ง if else ได้เท่านั้น)

## FIX CODE
```c++
#include <stdio.h>

int main(){
    int score = -1 ;
    printf( "Please enter your score : " ) ;
    scanf( "%d" , &score ) ;
    printf( "Grade : " ) ;
    if( score >= 80 ) {
        printf( "A !" ) ;
    }else if ( score >= 75 && score < 80 ) {
        printf( "B+ !" ) ;
    }else if ( score >= 70 && score < 75 ) {
        printf( "B !" ) ;
    }else if ( score >= 65 && score < 70 ) {
        printf( "C+ !" ) ;
    }else if ( score >= 60 && score < 65 ) {
        printf( "C !" ) ;
    }else if ( score >= 55 && score < 60 ) {
        printf( "D+ !" ) ;
    }else if ( score >= 50 && score < 55 ) {
        printf( "D !" ) ; 
    }else if ( score < 50 && score >= 0 ) {
        printf( "F !" ) ;
    }else {
        printf( "Please enter number only." ) ;
    }
    return 0 ;
}
```

## TEST CASE
### Input
```bash
enter score :
80
```
### Output
```bash
A !
```
<img width="272" height="40" alt="Screenshot 2025-07-26 123759" src="https://github.com/user-attachments/assets/20dff1cc-7aaf-40df-a7a6-6f6263b76212" />


## TEST CASE
### Input
```bash
enter score :
55
```
### Output
```bash
D+ !
```
<img width="269" height="38" alt="Screenshot 2025-07-26 123915" src="https://github.com/user-attachments/assets/45a877cc-2262-4f01-93d9-f9f0f02a86c6" />


## TEST CASE
### Input
```bash
enter score :
64
```
### Output
```bash
C+ !
```
<img width="277" height="40" alt="Screenshot 2025-07-26 124003" src="https://github.com/user-attachments/assets/ebccdd7d-935e-493b-86b1-ceca46910b89" />


## TEST CASE
### Input
```bash
enter score :
44
```
### Output
```bash
F !
```
<img width="277" height="40" alt="Screenshot 2025-07-26 124003" src="https://github.com/user-attachments/assets/51a33545-fa1b-43b8-a7e2-ca15c986248e" />


## TEST CASE
### Input
```bash
enter score :
hello
```
### Output
```bash
please enter number only.
```
<img width="318" height="39" alt="Screenshot 2025-07-26 124146" src="https://github.com/user-attachments/assets/197a9bc1-545e-45b5-8fc7-1a93d835326d" />


