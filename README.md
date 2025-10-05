输入 n 个字符，找到并输出大小排行中间的字符（ASCII 顺序）。


Input
第一行输入字符长度 n，第二行输入个字符（空格隔开）(温馨提示：%c 会吃掉空格和回车哦~~~)


Output
输出大小排行中间的字符（ASCII 顺序）。如果是偶数，就输出2个；中间用空格分开。


Sample Input 1 

5
a e g f b
Sample Output 1

e
Language: 
C
  
Theme: 
Solarized Light

1
dw#include <stdio.h>
2
#include <math.h>
3
​
4
// 用于qsort的比较函数
5
int cmp(const void *a, const void *b) {
6
    return (*(char*)a - *(char*)b);
7
}
8
​
9
int main() {
10
    int n;
11
    scanf("%d", &n);
12
    char arr[n];
13
    for (int i = 0; i < n; i++) {
14
        scanf(" %c", &arr[i]); // 注意%c前的空格，用于跳过空白符
15
    }
16
    
17
    qsort(arr, n, sizeof(char), cmp);
18
    
19
    if (n % 2) {
20
        printf("%c\n", arr[n / 2]); // n为奇数
21
    } else {
22
        printf("%c %c\n", arr[n / 2 - 1], arr[n / 2]); // n为偶数
23
    }
24
    
25
    return 0;
26
}
