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

