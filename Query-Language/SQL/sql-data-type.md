# SQL Data Type
: 컬럼이 가질 수 있는 데이터의 유형    



## 숫자

키워드 | 크기
---|---
NUMERIC(p,s) |
DECIMAL(p,s) |
TONYINT      | 1byte
SMALLINT     | 2byte
INTEGER      | 4byte
INT          | 4byte
BIGINT       | 8byte
REAL         | 4byte
FLOAT        | 4byte
DOUBLE       | 8byte
PRECISION    | 8byte



## 문자

키워드 | 설명
---|---
CHAR(n)      | 고정 길이 문자열, 최대 2000byte
VARCHAR(n)   | 가변 길이 문자열, 최대 4000byte
LONG         | 가변 길이 문자열, 최대 2GB



## 날짜 및 시간    

키워드 | 설명
---|---
DATE         | YYYY-MM-DD
TIME         | HH:MM:SS
DATETIME     | YYYY-MM-DD HH:MM:SS, 문자형으로 저장, 8byte
TIMESTAMP    | YYYY-MM-DD HH:MM:SS, 숫자형으로 저장, 8byte



## 논리

키워드 | 설명
---|---
BOOLEAN      | TRUE, FALSE, (NOT NULL 제약 조건이 없다면) NULL



[top](#)
