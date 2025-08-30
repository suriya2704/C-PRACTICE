# C-POINTER
## pointers-increment and decrement

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

