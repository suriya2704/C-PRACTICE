# C-POINTER
## pointers- 1 increment and decrement

```c
#include <stdio.h>
#include <stdlib.h>
int main(){
    char arr[]={'a','b','c'};
    char *ptr=arr;
    printf("%c\n",arr);
    ++ptr;
    printf("%d",arr);
}
  ```
  ***output***
  ```
  a
  b

  ```
  ---

## pointer-2

```c
#include <stdio.h>
#include <stdlib.h>
int main() {
    int num[]={10,20,30,40,50};
    int *p1=&num[1];
    int *p2=&num[3];
    printf("Element  between:%d/n",p2-p1);
}
```
***output***
```
Element  between: 2

```
## rules and conditions
 -  ptr++ it moves to next element sizeof(type).
 -  we can also give ptr + n or -n , p2 - p1 it gives no  element between them.
  ----

 ## pointer - 3 
 create a programe that print all arr elemrnt using only pointers :
  -find the last element and calculate the steps between of any two arr.

  **solution**
  ```c
  #include <stdio.h>

int main() {
    int arr[]={10,20,30,40,50};
    int *ptr=arr;
    
    int n, steps =0;
    printf("enter the n value:\n");
    scanf("%d",&n);
    for(int i=0;i<n;i++){

        printf("%d\n",*ptr);
        ++ptr;
        steps++;        
    }
    printf("elements between arr[0] to arr[3] :%d\n", &arr[3]-&arr[1]);
    printf("elements value diffrence between arr[0] to arr[3] :%d\n", arr[3]-arr[1]);
    printf("total steps: %d\n ",steps);
    if(n<=5){
        printf("lastvalue: %d",*(ptr-1));
    }
  return 0;
}
```

**output**
```
enter the n value:5
10
20
30
40
50
elements between arr[0] to arr[3] :2
elements value diffrence between arr[0] to arr[3] :20
total steps: 5
 lastvalue: 50
 ```
 ----

 ## pointer - 4
  ```c
  #include <stdio.h>

   void update(int *ptr, int size){
    for (int i=0; i<size; i++){
      *(ptr+i)= *(ptr+i) * 2 ;
    }

   }
  int main(){
    int arr[]={1,2,3,4,5};
    int n = sizeof(arr) / sizeof(arr[0]);
    update(arr,n);
    printf("values are:");

    for(int i=0; i<n ; i++){
      printf("%d," , *(arr+i));
    }
  }
  ```
  **output**
  ```
  values are:2,4,6,8,10
  ```
  ---

## PROGRAM -5



