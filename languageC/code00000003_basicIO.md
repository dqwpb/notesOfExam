# 基本輸入輸出

**注意**: 要有防呆機制!

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(void) {
    char buffer[256];

    printf("Enter your name and press <Enter>: \n");
    if (fgets(buffer,256,stdin) != NULL) {
        printf("\nYour name has %ld characters and spaces!\n", strlen(buffer));
    } else {
        printf("Failed to read input!\n");
    }
    
    return 0;
}
```
