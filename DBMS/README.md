# DBMS
Database Management System   
: 데이터베이스를 관리하기 위한 프로그램      
: 파일 시스템 단점과 문제점 개선      
: 데이터에 직접 접근하지 않고 필요한 데이터를 SQL 명령어를 통해 요청하여 사용        
: 다중 사용자 동시 접속, 데이터 추상화, 독립성, 무결성, 보안, 로깅 등 기능 지원       


- [DBMS 종류](#dbms-종류)
- [DBMS 역사](#dbms-역사)
- [DBMC 특징](#dbms-특징)

```
사용자  -->  DBMS  -->  DB
```



## DBMS 종류

**데이터 저장 방식에 따라**       
- [HDBMS (계층형 데이터 베이스)](./HDBMS.md)
- [NDBMS (네트워크형 데이터베이스)](./NDBMS.md)
- [RDBMS (관계형 데이터베이스)](/RDBMS/)
- [OODBMS (객체 지향 데이터베이스)](/OODBMS/)
- [ORDBMS (객체 관계 데이터베이스)](/ORDBMS/)


**비정형 데이터 처리를 위한**   
- [NoSQL](/NoSQL/)
- [NewSQL](/NewSQL/)


**기타**
- [CDBMS](./CDBMS.md)
- [DDBMS](./DDBMS.md)
- [MMDBMS](./MMDBMS.md)


**검색 엔진**
- Search Engine
- Full Text Search



## DBMS 역사

세대 | 시기 | 특징
---|---|---
제 1 세대 | 1960년대 초반 | IDS (Integrated Data Store)<br>: 최초 범용 DBMS <br>: 네트워크 데이터 모델 시초
&nbsp;  | 1960년대 후반 | IMS (Information Management System)<br>: 최초 사용화된 제품으로 현재도 사용 <br>: 계층 데이터 모델 시초
&nbsp;  | 1970년대 초반 | IDS + IMS <br>: 벤더사별 DBMS를 제작하여 판매
제 2세대  | 1970년대 후반 | 관계 DBMS, SQL
제 3세대  | 1980년대 후반 | 객체 지향 DBMS, 객체 관계 DBMS



## DBMS 특징

- 데이터 독립성 보장
- 데이터 중복 최소화
- 데이터 동시 공유
- 데이터 일관성 유지
- 데이터 무결성 유지
- 데이터 표준화 달성
- 데이터 실시간 처리  
- 데이터 보안 -- 데이터 접근 권한 통제


**데이터 독립성**   
: 프로그램이 데이터에 종속되지 않는 것

- 논리적 데이터 독립성  
	- 데이터의 논리적 구조로부터 사용자와 프로그램 독립
	- 사용자는 데이터베이스의 내부 구조에 신경쓰지 않고 작업 가능

- 물리적 데이터 독립성  
	- 데이터의 물리적 구조로부터 사용자와 프로그램 독립
	- 사용자는 데이터가 실제 저장된 저장 위치나 파일구조에 관계없이 작업 가능



[top](#)
