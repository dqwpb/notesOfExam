# 所有練習在 Virtualbox 下的 Lubuntu 中完成

## 版本

```bash
lsb_release -a
```

```
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 16.10
Release:	16.10
Codename:	yakkety
```

## 特別注意

ubuntu 的 **UEFI** 手動安裝無解，只能使用預設安裝，即使有切 **ESP** 給他也沒用！不要浪費力氣 try!

## 基本安裝套件

### 編譯工具

```bash
sudo apt-get install build-essential
```

### 新酷音輸入法

已內建 `fcitx` 輸入法框架和新酷音輸入法，但是要安裝輔助套件以方便使用**選字**功能:

```bash
sudo apt-get install qtdeclarative5-qtquick2-plugin
```
