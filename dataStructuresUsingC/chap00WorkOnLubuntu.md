# 在 Lubuntu 下編譯與執行 C 程式

## 一般編譯指令:

```bash
gcc -ansi -g -Wall -O2 file.c main.c -o main.out
```

**要執行的程式** 放在 main.c 裡面，額外程式另外寫成 **標頭檔** (.h) 且另外放 (.c)

main.c 範本:

```c
#include "file.h"

int main(int argv, char argv[]){
  /*
    (code)
  */
  
  return 0;
}
```

file.h 範本:

```c
#ifndef FILE_H
#define FILE_H

#include <(lib).h>
#include "(diy).h"

int funcTest(int a);

#endif
```

file.c 範本:

```c
int funcTest(int a) {
  /*
  (code body)
  */
}
```

## 特殊編譯指令

```bash
gcc -std=c11 -g -Wall -O2 file.c main.c -o main.out
```

如果是 C++:

```bash
g++ -std=c++11 -g -Wall -O2 file.c main.c -o main.out
```
