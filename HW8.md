> **mult.asm**


```
#include <stdio.h>

int main() {
    int R0 = 3;
    int R1 = 5;
    int R2 = 0;
    
//    while (R0 > 0) {
loop:
    if (R0 <= 0) goto exit1;
    R2 = R2 + R1;
    R0 = R0 - 1;
    printf("R0=%d R1=%d R2=%d\n", R0, R1, R2);
    goto loop;
exit1:
//    }
    
    printf("R2=%d\n", R2);//顯示結果
}
```


```
// #include <stdio.h>

// int main() {
//    int R0 = 3;
//    int R1 = 5;
// =>    int R2 = 0;
@0 //a設為0
D=A  //d=0
@R2 //a設為2
M=D //m[2]=d
//    while (R0 > 0) {
// => loop:
(loop)
// =>    if (R0 <= 0) goto exit1;
@R0
D=M  //d= m[0]
@exit1 //把a設為exit1
D; JLE //d<=0就goto exit1

// =>  R2 = R2 + R1;
@R1 //a=1
D=M  d=m[1]
@R2 //a=2
M=D+M //m2=d+m2

// =>  R0 = R0 - 1;
@R0
M=M-1 //計數器-1

//     printf("R0=%d R1=%d R2=%d\n", R0, R1, R2);
// =>  goto loop;
@loop
0;JMP //回到LOOP1

// => exit1:
(exit1)
@exit1
0;JMP
//    }
    
//     printf("R2=%d\n", R2);
// }
```
