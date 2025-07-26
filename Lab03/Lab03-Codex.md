
## โจทย์
จงจัดโค้ดโปรแกรมต่อไปนี้ให้อยู่ในรูปแบบมาตรฐาน Codex และแก้ไข Bug ของโปรแกรม

## FIX CODE
```c++
#include <stduio.h>
#include <math.h>

int isPrime(int num) {if(num<2)return 0;
for (int i = 2; i <= sqrt(num); i++) {
if (num % i == 0)return 0;}return 1;}
  int main() {
 int n;
    printf("Enter N : ");scanf("%d",&n);
int arr[n]; for(int i=0;i<n;i++){
    printf("Enter value[%d] : ",i);
  scanf("%d",&arr[i]);
      }
    printf("Index:  ");
   for (int i = 0;i < n;i++){
 printf("%2d ", i);
}printf("\n");
         printf("Array:  ");
  for(int i=0;i<n;i++){if (isPrime(arr[i]))
printf("%2d ", arr[i]); 
    else
printf("%2s ", "#"); 
    }
    printf("\n");return 0;
        }
```

## FIXED CODE
```c++
#include <stdio.h>
#include <math.h>

int isPrime ( int num ) { 
    if( num < 2 )
        return 0 ;
    for ( int i = 2 ; i <= sqrt(num) ; i++ ) {
        if ( num % i == 0 )
            return 0 ;
    }
    return 1 ; 
}

int main() {
    int n ; 
    printf( " Enter N : " ) ;
    scanf( "%d" , &n ) ; 
    int arr[n] ; 
    for( int i = 0 ; i < n ; i++ ) {
        printf( " Enter value [ %d ] : " , i ) ; 
        scanf( "%d" , &arr[i] ) ; 
    }//end for
    printf(" Index:  ") ;
    for ( int i = 0 ; i < n ; i++ ) {
        printf( "%2d" , i ) ; 
    }//end for
    printf( "\n" ) ;
    printf(" Array:  ") ;
    for( int i = 0 ; i < n ; i++ ) {
        if (isPrime(arr[i]))
            printf("%2d", arr[i]) ; 
        else
            printf( " #" ) ; //ลบ"%2s ",
    }
    printf("\n") ;
    
    return 0 ;
}
```

## TEST CASE
### Input
```bash
Enter N : 4
Enter value[0] : 5
Enter value[1] : 7
Enter value[2] : 2
Enter value[3] : 1
```
![Screenshot (95)](https://github.com/udsgg/ENGCC304/blob/main/Lab03/Screenshot%202025-07-17%20102712.png)

### Output
```bash
Index:   0  1  2  3 
Array:   5  7  2  #
```
![Screenshot (95)](https://github.com/udsgg/ENGCC304/blob/main/Lab03/Screenshot%202025-07-26%20105136.png)

