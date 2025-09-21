# C-STORAGE CLASS
## PROGRAM-1

```c
#include <stdio.h>
#include <stdlib.h>

int main(){
    auto int x=10;
    {
        auto int x=20;
        printf("%d\n",x);
    }
    printf("%d",x);
}
```
***output***
```
20
10
```
---

## PROGRAM-2

```c
#include <stdio.h>
#include <stdlib.h>

void fun(){
    static int x;
    x+=10;
    printf("%d\n",x);
}
int main(){
    fun();
    fun();
}
```
***output***
```
10
20
```
---

## PROGRAM-3

```c
#include <stdio.h>
#include <stdlib.h>

void fun(){
     extern int x;
    x+=10;
    printf("%d\n",x);
}
void fun1(){
    extern int x;
    printf("%d\n",x);
}
int main(){
    extern int x;
    printf("%d\n",x);
    fun();
    fun1();
}
int x=60;
```
***output***
```
60
70
70
```
---

## PROGRAM-4 

```c
#include <stdio.h>
#include <stdlib.h>

int fun(){
     static int x=16;
     return x--;
}

int main(){
    
    for(fun();fun();fun())
        printf("%d\t",fun());
        return 0;   
}
```
***output***
```
14	11	8	5	2	
```
---

## PROGRAM-5

```c
#include <stdio.h>
#include <stdlib.h>
int a=1,b;

void fun(){
     static int a=2;
     int b=1;
     a+= ++b;
     printf("fun a= %d %d\n",a,b);
}

int main(){
   // static int a; //check with this line
    fun();
    a=a+1;
    fun();
    printf("mainfun a= %d %d",a,b);
}
```
***output***
```
fun a= 4 2
fun a= 6 2
mainfun a= 2 0
```
---

## PROGRAM-6

```c
#include <stdio.h>
#include <stdlib.h>
int a=1,b;

void fun(){
     register int a=2;
     int b=1;
     a+= ++b;
     printf("fun a= %d %d\n",a,b);
}

int main(){
   auto int a=1;
    fun();
    a=a+1;
    fun();
    printf("mainfun a= %d %d",a,b);
}
```
***output***
```
fun a= 4 2
fun a= 4 2
mainfun a= 2 0
```
---