# Install PostgreSQL on Lubuntu 16.10

## 1. Installation:

'''{bash}
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib
'''

## 2. Into the DBMS:

'''{bash}
sudo su postgres
psql
postgres # \conninfo
postgres # \q
'''
