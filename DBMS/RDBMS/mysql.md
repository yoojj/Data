# MySQL

- [MySQL Install](#mysql-install)
- [MySQL Command](./mysql-command.md)



## MySQL Install

```bash
# 설치
$ sudo yum install mysql-server

# 설치 확인
$ mysql --version


# 실행
$ mysqladmin -u root -p reload
$ sudo systemctl start mysqld

# 종료
$ mysqladmin -u root -p shutdown
$ sudo systemctl stop mysqld


# 루트 접속
# mysql -h아이피 -u아이디 -p비번
$ mysql -u root -p
$ mysql --user=root -p
```



## MySQL Version Upgrade

```bash
# 데이터 백업
$ mysqldump --lock-all-tables -u root -p --all-databases > dump.sql

# 이전 버전 제거
$ yum remove mysql-*

# 패키지 확인
$ rpm -qa | grep mysql

# 설치
$ rpm -ivh http://repo.mysql.com/mysql57-community-release-el7.rpm
$ yum install mysql-server


# 루트 접속을 위한 임시 비밀번호 확인
$ sudo grep 'temporary password' /var/log/mysqld.log

# 루트 접속 후 비밀번호 변경
$ mysql -u root -p mysql
$ alter user 'root'@'localhost' identified by '비밀번호';


# 데이터 복원
$ mysql -u root -p < dump.sql
```



## Troubleshooting

**Can't connect to local MySQL server through socket**   

- mysqld 실행 여부 확인
- mysql.sock 파일 여부 확인
- mysql-server 설치 여부 확인
- 이전 mysql 관련 파일이 있는지 확인



[top](#)
