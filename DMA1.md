# C-DYNAMIC MEMORY ALLOCATION
## PROGRAM-1

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int n , *ptr;
    printf("enter the value of n :");
    scanf("%d",&n);
    ptr=(int*)malloc(n*sizeof(int));
    
    for(int i=0;i<n;i++){
        scanf("%d",ptr+i);
    }

    printf("values are: ");

    for(int i=0;i<n;i++){
       printf("%d\n",*(ptr+i));
    }
    free(ptr);
    return 0;
}

 ```
 **output** 
 ```
 enter the value of n :3
1 2 3
values are: 1
2
3
```
---
## Rules and conditions 
  - so malloc assign each int 4 byte,if i want loop 4 loop int then 4*4 16 byte i want give.it automatically asingn bytes to each ,the only thing is we want store all bytes we want.  
  - But if you want 3 integers?
  - You need 3 × 4 = 12 bytes.
  - Why? Because:
  - ptr[0]  → 4 bytes
  - ptr[1]  → next 4 bytes
  - ptr[2]  → next 4 bytes
  - So total = 12 bytes.
  ----

## PROGRAM-2

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n,*ptr;
    printf("enter the value : ");
    scanf("%d",&n);
    printf("enter the value :");
    ptr=(int *)malloc(n *sizeof(int));
    
    for (int i=0;i<n;i++){
        scanf("%d",ptr+i);
    }
    
    printf("enter reassinged value: ");
    scanf("%d",&n);
    printf("reassinged value: ");
    int *ptr1=(int *)realloc(ptr,n*sizeof(int));
    
    for(int i=0;i<n;i++){
        printf("%d\n", *(ptr1+i));
    }
    
    free(ptr1);
}

```
**output**
```
enter the value : 3
enter the value :1 2 3
enter reassinged value: 4
reassinged value: 1
2
3
0
```
---

## PROGRAM-3

```c
#include <stdio.h>
#include <stdlib.h>

int *display (){
    int *ptr;
    ptr=(int*)malloc(3*sizeof(int));
    printf("enter the value:");

    for (int i=0;i<3;i++){
        scanf("%d",(ptr+i));
    }
    return ptr;
}

int main()
{
    int   *ptr1;
    ptr1=display();
    printf("values are: ");

    for(int i=0;i<3;i++){
       printf("%d\t",*(ptr1+i));
    }
    free(ptr1);
    return 0;
}

```
**output**
```
enter the value:3 4 5
values are: 3	4	5	
```
---

## PROGRAM-4

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr; 
    arr = (int*)malloc(3 * sizeof(int));
    printf("enter the value:");
     for (int i = 0; i < 3; i++) {
       scanf("%d",arr+i);   
    }
    printf("values are:");
    for (int i = 0; i < 3; i++) {
       printf("%d ",*(arr+i));   
    }
    
    int *arr1 = (int*)realloc(arr, 6 * sizeof(int));
    if (arr1 == NULL) {
        printf("Reallocation failed!\n");
        return 1;}
   
    printf("\nenter the value:");
    for (int i = 0; i < 6; i++) {
        scanf("%d", arr+ i );  
    } 
    printf("Array after realloc: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", *(arr+i));
    }
    free(arr);
    return 0;
}

```
**output**
```
enter the value:1 2 3
values are:1 2 3 
enter the value:4 5 5 6 7 8
Array after realloc: 4 5 5 6 7 
```
---

## PROGRAM-5

```c
#include <stdio.h>
#include <stdlib.h>

 struct device {
    int vol;
    int cur;
};

int main() {
    struct device *a;
    a=(struct device*)malloc(3*sizeof(struct device));
    
    for(int i=0;i<3;i++){
      a[i].vol=i+1;
       a[i].cur=i+2;
    }
    printf("values are:\n");
    for(int i=0;i<3;i++){
     printf(" volt=%d,cut=%d\n", a[i].vol, a[i].cur );
    }

    return 0;
}
```
**output**
```
values are:
 volt=1,cut=2
 volt=2,cut=3
 volt=3,cut=4
 ```
 ---

