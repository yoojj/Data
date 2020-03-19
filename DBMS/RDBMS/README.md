# RDBMS
: 관계형 모델을 기반으로 하는 데이터베이스 관리 시스템     
: 열과 행으로 이루어진 2차원 테이블에 성격에 맞게 분리된 데이터 저장     
: 테이블과 테이블 사이에 관계를 형성하여 데이터 중복 문제 해결        
: 트랜잭션을 지원해 데이터 불일치 문제 해결    

- [Table](#table)
- [Relation](#relation)
- Transaction
- Schema
- Index
- View
- ORM


**solutions**  
- [H2](./h2.md)
- [Oracle Database](./oracle.md)
- [MySQL](./mysql.md)
- [PostgreSQL](./postgresql.md)
- [Microsoft SQL Server](./sqlserver.md)
- Hive
- Sybase
- SQLite
- CouchDB
- MariaDB
- Redis Enterprise
- Amazon SimpleDB
- Amazon Aurora
- Google Fusion Tables
- ...



## Table   
: 가로-열-컬럼과 세로-행-로우로 구성된 표  

**컬럼**  
= 필드, 속성     
: 테이블을 구성하는 데이터 타입       
: 컬럼 수 = 디그리(Degree)

**로우**   
= 레코드, 튜플   
: 지정된 컬럼 데이터 집합  
: 로우 수 = 카디날리티(Cardinality)



## Relation
: 성격에 맞게 분리된 테이블들을 연결 역할을 하는 컬럼-키를 통해 관계를 맺음    
: 데이터 무결성을 위해 하나의 테이블에는 하나의 키 필수   

**키**  
: 연결 역할을 하는 컬럼   


키 | 설명
---|---
primary key | 기본 키 : 하나의 유일한 로우 데이터를 식별하는 키-컬럼
foreign key | 참조 키 : 다른 테이블 기본 키와 연결이 되는 키-컬럼


**종류**    
- 일대일(one-to-one)
- 일대다(one-to-many)
- 다대다(many-to-many)



[top](#)
