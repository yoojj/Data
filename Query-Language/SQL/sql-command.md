# SQL Command
: 테이블 생성 및 삭제와 데이터 삽입 및 삭제 등을 위한 명령어   

- [DDL](#ddl)
- [DML](#dml)
- [DCL](#dcl)



## DDL  
Data Definition Language     
: 데이터 정의 언어   
: 데이터 구조-스키마를 생성, 수정, 제거하기 위한 언어        


키워드 | 설명
---|---
CREATE   | 테이블-객체 생성
DROP     | 테이블-객체 제거
ALTER    | 테이블-객체 변경
TRUNCATE | 테이블에 저장된 모든 데이터-로우-인덱스 삭제  
RENAME   | 테이블-객체 이름 수정  

! COMMIT 자동
! RENAME 역할을 ALTER가 대신 할 수 있음


```sql
-- 테이블 생성
CREATE TABLE 테이블명;
CREATE TABLE 테이블명(컬럼 데이터타입);

-- 테이블 변경
ALTER TABLE 테이블명 SET UNUSED;
ALTER TABLE 테이블명 ADD COLUMN;
ALTER TABLE 테이블명 MODIFY COLUMN;
ALTER TABLE 테이블명 DROP COLUMN;

-- 테이블 제거
DROP TABLE 테이블명;
```


**식별자 규칙**  
1. 문자로 시작
2. 1~30 자리수
3. A~Z, 0~9, _, $, # 사용 가능  


**MODIFY COLUMN**  
- 컬럼 수정시 해당 컬럼에 데이터가 없는 경우 데이터 타입과 크기 변경 가능
- 컬럼 수정시 해당 컬럼에 데이터가 있는 경우 데이터 크기를 크게 변경하는 것만 가능
- CHAR과 VARCHAR2 사이의 데이터 타입은 변경 가능



## DML
Data Manipulation Language   
: 데이터 조작 언어   
: 데이터 삽입, 조회, 수정, 삭제를 위한 언어   


키워드 | 설명
---|---
INSERT | 테이블에 데이터 삽입
SELECT | 테이블에서 데이터 조회
UPDATE | 테이블에 저장된 데이터 수정
DELETE | 테이블에 저장된 데이터 삭제
MERGE  | 조건에 따라 INSERT + UPDATE

! COMMIT 명시


```sql
-- 데이터 삽입
INSERT INTO 테이블명 (컬럼명..) VALUES (값..);

-- 데이터 조회
SELECT 컬럼명 FROM 테이블명;
SELECT 컬럼명 FROM 테이블명 WHERE 조건;

-- 데이터 수정
UPDATE 테이블명 SET 컬럼=값 WHERE 조건;

-- 데이블 삭제
DELETE FROM 테이블명 WHERE 조건;
```



### DQL  
Data Query Language   
: 데이터 쿼리 언어   
: DML에서 SELECT만 분리     



## DCL
Data Control Language   
: 데이터 관리 언어   
: 사용자 권한을 관리하는 언어   


DCL | 설명
---|---
GRANT    | 테이블-객체에 대한 권한 부여
REVOKE   | 테이블-객체에 대한 권한 박탈
COMMIT   | 트랜잭션 결과 반영
ROLLBACK | 트랜잭션 취소, 원복



### TCL  
Transaction Control Language    
: 트랜잭션 제어 언어   
: DCL에서 COMMIT과 ROLLBACK 분리  



[top](#)
