# 所有程式都在 Lubuntu 16.10 下撰寫編譯執行

## 最一般的編譯指令

```bash
gcc -ansi -g -Wall -O2 file.c main.c -o main.out
```

然後 `file.c` 所用的 headers 寫在 `file.h` 裡面, `main.c` 純粹是使用函式作動作.

## 碰到新的標準

例如:

```bash
gcc -std=C11 -g -Wall -O2 file.c main.c -o main.out
```

