# 在Lubuntu 16.10 下安裝 PostgreSQL

## 1. 直接安裝

```bash
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib
```

## 2. 進入資料庫系統

使用**系統管理帳號** `postgres` 進入:

```bash
sudo su postgres
psql
postgres # \conninfo
postgres # \q
```
