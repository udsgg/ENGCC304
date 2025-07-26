## โจทย์
เขียนโปรแกรมภาษาซีเพื่อรับข้อมูลพนักงานของบริษัทซอร์ฟแวร์ โดยรับข้อมูล รหัสประจำตัวพนักงาน , จำนวนชั่วโมงที่ทำงาน , รายได้ต่อชั่วโมง จากนั้นให้แสดงข้อมูลเลขประจำตัวพนักงาน พร้อมกับรายได้ทั้งหมดที่หนักงานจะได้รับทั้งหมด

## FIX CODE
```c++
#include <stdio.h>
```

## FIXED CODE
```c++
#include <stdio.h>

int main(){
    char ID[11] ;
    int workhrs ;
    int salary ;
    printf( "Input Employees ID Max. 10 chars):\n") ;
    scanf( "%10s" , ID ) ;
    printf( "Input the working hrs: \n" ) ;
    scanf( "%d" , &workhrs ) ;
    printf( "Salary amount/hr:\n" ) ;
    scanf( "%d" , &salary ) ;
    printf( "Expected Output:\n" ) ;
    printf( "Employees ID = %s \n" ,ID ) ;
    printf( "Salary = U$ %0.2f" , (float)(salary*=workhrs) ) ;

    return 0 ;

}
```

## TEST CASE
### Input
```bash
Input Employees ID Max. 10 chars):
001
Input the working hrs: 
4
Salary amount/hr:
12300
```


### Output
```bash
Expected Output:
Employees ID = 001 
Salary = U$ 49200.00
```
