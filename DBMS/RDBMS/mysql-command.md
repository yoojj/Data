# MySQL Command


```bash

# 설정 변경
$ sudo vim /etc/my.cnf

    # 인코딩 설정
    # [client]
    # default-character-set = utf8

    # [mysql]
    # default-character-set=utf8

    # [mysqld]
    # collation-server = utf8_unicode_ci
    # init-connect = 'SET NAMES utf8'
    # character-set-server = utf8


# 보안 설정
$ mysql_secure_installation


# sql 파일 import
$ mysql -u 아이디 -p --database=디비 < 파일.sql

# 덤프 -- 테이블의 구조와 레코드 저장
$ mysqldump -u root -p 디비 > 파일.sql


# 환경 확인
> SHOW VARIABLES;
```



## user

```sql
-- 루트 접속
$ mysql -u root -p

-- 스키마 변경
> use mysql;

-- 사용자 확인
> select host, user, password from user;

-- 사용자 추가
> create user '아이디'@localhost identified by '비밀번호';
> create user '아이디'@'%' identified by '비밀번호';

-- 비밀번호 변경
> update user set password=password('비밀번호') WHERE user='아이디';

-- 사용자 삭제
> delete from user where user='아이디';

-- 반영
> flush privileges;
```



## database

```sql
-- 조회
> show databases;

-- 생성
> create database 디비 default character set utf8;
> create schema 디비 default character set utf8;

-- 사용
> use 디비;

-- 사용중인 디비 확인
> select database();

-- 제거
> drop database 디비;


-- 모든 권한 부여
> grant all privileges on *.* to '사용자'@'호스트' identified by '사용자';

-- grant 명령어 사용 가능  
> grant all privileges on *.* to '사용자'@'호스트' identified by '사용자' with grant option;

-- 특정 테이블 권한만 부여
> grant all privileges on 디비.테이블 to '사용자'@'호스트' identified by '사용자';

-- 권한 부여 확인
> show grants for '사용자'@'호스트';

-- 권한 삭제
> revoke all on *.* from '사용자'@'호스트';
> revoke all on 디비.테이블 from '사용자'@'호스트';
> revoke grant option on *.* from '사용자'@'호스트';


-- 인코딩 수정
> alter databse 디비 default character set utf8;
```



## table

```sql
-- 사용자 접속
$ mysql -u 아이디 -p

-- 사용
> use 디비;

-- 조회
> show tables;


-- 생성
> create table 테이블(
    컬럼명 타입(길이) 옵션
);

-- 삭제
> drop table 테이블;


-- 컬럼 추가
> alter table 테이블 add column 컬럼명 타입(길이) 옵션;

-- 컬럼 타입 수정
> alter table 테이블 modify column 컬럼명 타입(길이);

-- 컬럼 삭제
> alter table 테이블 drop column 컬럼명;


-- 테이블 정보 확인
> desc 테이블;

-- 실행 계획 정보 확인
> explain 테이블;


-- insert
> insert into 테이블 (컬럼명) value(값);

-- select
> select * from 테이블;
> select 컬럼명 from 테이블;

-- update
> update 테이블 set 컬럼=값 where 조건;

-- delete
> delete from 테이블 where 조건;
```



[top](#)
