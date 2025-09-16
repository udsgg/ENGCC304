## โจทย์ทบทวนความรู้
เขียนโปรแกรมภาษาซีสำหรับคำนวณเงินเดือนสุทธิและโบนัสของโปรแกรมเมอร์ตามเงื่อนไขดังนี้:

### โปรแกรมจะรับข้อมูลเบื้องต้นจากผู้ใช้ดังนี้:
ตำแหน่งงาน (เช่น Junior Programmer, Mid-Level Programmer, Senior Programmer) โดยใช้ตัวเลข 1, 2, หรือ 3 แทนตามลำดับ
- จำนวนปีที่ทำงาน (อายุงาน)
- จำนวนโปรเจคที่สำเร็จในปีนี้

### การคำนวณโบนัส:

#### โปรแกรมเมอร์จะได้รับโบนัสตามอายุงาน ดังนี้:
- หากอายุงานน้อยกว่า 1 ปี จะไม่ได้รับโบนัส
- หากอายุงาน 1-3 ปี ได้รับโบนัส 10% ของเงินเดือน
- หากอายุงาน 4-5 ปี ได้รับโบนัส 15% ของเงินเดือน
- หากอายุงานมากกว่า 5 ปี ได้รับโบนัส 20% ของเงินเดือน
- นอกจากนี้ยังมีโบนัสพิเศษหากโปรแกรมเมอร์ทำโปรเจคได้สำเร็จมากกว่า 5 โปรเจค โดยจะได้รับโบนัสเพิ่มอีก 5% ของเงินเดือน

#### การกำหนดเงินเดือนพื้นฐานตามตำแหน่ง:
- Junior Programmer: 20,000 บาท
- Mid-Level Programmer: 35,000 บาท
- Senior Programmer: 50,000 บาท

#### โปรแกรมจะคำนวณและแสดงผลดังนี้:
- เงินเดือนพื้นฐาน
- โบนัสตามอายุงาน
- โบนัสพิเศษ (ถ้ามี)
- เงินเดือนสุทธิ (เงินเดือนพื้นฐาน + โบนัสตามอายุงาน + โบนัสพิเศษ)

## FIX CODE
```c++
#include <iostream>
int position;
int EXP;
int project;
int salary;
int Bonus;
int special;

int main() {
    printf("Input your position 1 (Junior Programmer) \n");
    printf("Input your position 2 (Mid-level Programmer) \n");
    printf("Input your position 3 (Senior Programmer) \n");
    scanf("%d", &position);
    printf("Years of Experience: \n");
    scanf("%d", &EXP);
    printf("Number of Projects Completed this Year:\n");
    scanf("%d", &project);
    if (position == 1) salary = 20000;
    else if (position == 2) salary = 35000;
    else if (position == 3) salary = 50000;
    else {
        printf("Error: Invalid Position\n");
        return 0;
    }
    printf("Base Salary =  %d THB \n", salary);
    if (EXP < 1) Bonus = 0;
    else if (EXP <= 3) Bonus = salary * 10 / 100;
    else if (EXP <= 5) Bonus = salary * 15 / 100;
    else if (EXP > 5) Bonus = salary * 20 / 100;
    printf("Bonus =  %d THB \n", Bonus);
    if (project > 5) special = salary * 5 / 100;
    else special = 0;
    printf("Special Bonus =  %d THB \n", special);
    printf("Total salary =  %d THB ", salary + Bonus + special);
    return 0;
}
```

## FLOWSHART
!(<img width="2211" height="1111" alt="ssss drawio" src="https://github.com/user-attachments/assets/3624e029-b92b-46b8-942c-c52e4b681f58" />)


## TEST CASE
### Input
```bash
Input your position 1 (Junior Programmer) 
Input your position 2 (Mid-level Programmer) 
Input your position 3 (Senior Programmer) 
3
Years of Experience: 
4
Number of Projects Completed this Year:
7
```
### Output
```bash
Base Salary = THB 50000 
Bonus = THB 7500 
Special Bonus = THB 2500 
Total salary = THB 60000 
```

## TEST CASE
### Input
```bash
Input your position 1 (Junior Programmer) 
Input your position 2 (Mid-level Programmer) 
Input your position 3 (Senior Programmer) 
1
Years of Experience: 
2
Number of Projects Completed this Year:
4
```
### Output
```bash
Base Salary =  20000 THB 
Bonus =  2000 THB
Special Bonus =  0 THB
Total salary =  22000 THB
```
