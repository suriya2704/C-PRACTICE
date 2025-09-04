# C-DYNAMIC MEMORY ALLOCATION
## PROGRAME-1

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
## Rules and conditions :
 //so malloc assign each int 4 byte ,if i want loop 4 loop int then 4*4 16 byte i want give.it automatically asingn
    //bytes to each ,the only thing is we want store all bytes we want. so only we are giving n*whic means n*4 because we looping using n.
    //But if you want 3 integers?
    //You need 3 × 4 = 12 bytes.
    ///Why? Because:
    /*c
    Copy
    Edit
    ptr[0]  → 4 bytes
    ptr[1]  → next 4 bytes
    ptr[2]  → next 4 bytes
    So total = 12 bytes.*/
  ```
  ---
