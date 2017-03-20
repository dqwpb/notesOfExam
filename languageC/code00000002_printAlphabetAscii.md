# 用 ACSII 字碼印出英文字母

`main.c`

```c
#include <stdio.h>

int main(void) {
    int ctr;
    for (ctr = 65; ctr < 91; ctr++)
        printf("%c", ctr);
    puts("");

    for (ctr = 97; ctr < 123; ctr++)
        printf("%c", ctr);
    puts("");

    return 0;
}
```
