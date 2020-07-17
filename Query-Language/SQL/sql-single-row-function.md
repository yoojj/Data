# SQL Single-Row Function
: SELECT, WHERE, ORDER BY 절에서 사용    

- [숫자 함수](#숫자-함수)
- [문자 함수](#문자-함수)
- [날짜 함수](#날짜-함수)
- [형변환 함수](#형변환-함수)
- [기타 함수](#기타-함수)



## 숫자 함수
: 숫자 데이터를 받아 피연산자로 연산한 숫자형 반환

함수 | 설명
---|---
ABS(n)        | n의 절대 값 반환
CEIL(n)       | 올림 함수 : n과 같거나 나머지를 올림한 정수 반환
FLOOR(n)      | 내림 함수 : n과 같거나 나머지 버린 정수 반환
ROUND(n, i)   | 지정한 자릿수에서 반올림한 수 반환
TRUNC(n1, n2) | 지정한 자릿수 이하 삭제한 수 반환
MOD(n2, n1)   | n2를 n1로 나눈 나머지 값 반환
POWER(n2, n1) | n2의 n1승 반환
SQRT(n)       | n의 제곱근 반환
SIGN(n)       | n의 부호 반환 (양수면 1, 음수면 -1)
EXP(n)        | 지수 함수 : e의 n 제곱 값을 반환
LN(n)         | 자연 로그 함수 : n의 자연 로그 값 반환
LOG(n2, n1)   | n2를 밑수로 하는 n1의 로그 값을 반환



## 문자 함수
: 문자열 데이터를 받아 피연산자로 연산한 결과 반환     
: 대부분 문자형을 반환하지만 일부 숫자형으로 반환   

함수 | 설명
---|---
CHR(n)            | n(아스키 코드)에 해당하는 문자 반환
CONCAT(c1, c2)    | c1과 c2 문자 결합한 결과 반환
UPPER(c)          | 문자를 대문자로 변환하여 반환
LOWER(c)          | 문자를 소문자로 변환하여 반환
INITCAT(c)        | 첫 번째 문자를 대문자로 변환하여 반환
SUBSTR(c, n1, n2) | 문자의 n1 위치에서 n2 까지 길이 만큼 잘라낸 결과 반환
TRIM(c)           | 양쪽 공백 문자 제거 후 남은 문자 반환  
LTRIM(e1, e2)     | e1에서 e2를 왼쪽부터 제거한 문자 반환  
RTRIM(e1, e2)     | e1에서 e2를 오른쪽부터 제거한 문자 반환
LPAD(e1, n, e2)   | e1에 e2를 왼쪽부터 채워 총 길이가 n이 되면 반환  
RPAD(e1, n, e2)   | e1에 e2를 오른쪽부터 채워 총 길이가 n이 되면 반환


**숫자 반환 함수**

함수 | 설명
---|---
ASCII(c)              | 문자의 아스키 코드 값 반환
LENGTH(c)             | 문자의 길이 반환
INSTR(c1, c2, n)      | c1에서 c2의 n번째 인덱스 반환


```sql
> SELECT LTRIM('***string***', '*')
> string***

> SELECT RTRIM('***string***', '*')
> ***string


> SELECT LPAD('string', 10, '*')
> ****string

> SELECT RPAD('string', 10, '*')
> string****


> SELECT INSTR('ABCABCABC', 'A', 2)
> 4
```



## 날짜 함수

함수 | 설명
---|---
SYSDATE                | 현재 일자와 시간 반환
ADD_MONTHS(d, n)       | date에 n개월을 더한 날짜 반환, n이 음수일 경우 뺀 날짜 반환
MONTHS_BETWEEN(d1, d2) | date1과 date2 사이의 개월 수 반환
LAST_DAY(d)            | date가 속한 월의 마지막 일자 반환
NEXT_DAY(d, e)         | date를 기준으로 expr에 명시한 날짜 반환
ROUND(d, f)            | date를 format 기준으로 반올림한 날짜 반환
TRUNC(d, f)            | date를 format 기준으로 잘라낸 날짜 반환


```sql
> SELECT SYSDATE;
> 0000-00-00 00:00:00.000

> SELECT TO_CHAR(SYSDATE, 'YYYY-MM-DD');
> 0000-00-00

> SELECT TO_CHAR(SYSDATE, 'YYYY-MM-DD HH24-MI:SS');
> 0000-00-00 00:00:00
```



## 형변환 함수

함수 | 설명
---|---
TO_CHAR(n, format) | n을 포맷에 맞게 문자로 변환하여 반환
TO_CHAR(d, format) | d을 포맷에 맞게 문자로 변환하여 반환
TO_NUMBER(c)       | (숫자인 문자일 경우) c를 숫자형으로 반환
TO_DATE(c, format) | c를 날짜 포맷에 맞게 변환하여 반환


```sql
> SELECT TO_CHAR(12345, '0,0000');
> 1,2345

> SELECT TO_CHAR(SYSDATE, 'YYYY-MM');
> 0000-00
```



## 기타 함수

함수 | 설명
---|---
NVL(e1, e2)      | e1 값이 null이면 e2 반환
NVL2(e1, e2, e3) | e1 값이 null이면 e3 반환하고 null이 아니면 e2 반환   
NULLIF(e1, e2)   | e1과 e2의 비교해 값이 같으면 null을 반환하고 같지 않으면 e1 반환
COALESCE(e1 ...) | 처음으로 null이 아닌 값 반환
GREATEST(e1 ...) | 값을 비교하여 가장 큰 값 반환
LEAST(e1 ...)    | 값을 비교하여 가장 작은 값 반환
DECODE(e, s1, r1 ... d) | e이 s1과 같으면 r1 반환하고 같지 않으면 d 반환


```sql
> SELECT NVL(null, 'str');
> str

> SELECT NVL2(null, '0', '1');
> 1

> SELECT NVL2(true, '0', '1');
> 0

> SELECT NVL2(false, '0', '1');
> 0


> SELECT COALESCE(null, null, '1', null, '2');
> 1


> SELECT NULLIF('1', '2');
> 1

> SELECT NULLIF('1', '1');
> null


> SELECT GREATEST(1,2,3,4,5);
> 5

> SELECT GREATEST('a','b','c');
> c
```


**CASE 표현식**  
: DECODE 함수와 동일

```sql
> SELECT DECODE(0, 1,'일', 2,'이', 3,'삼', '없음');
> 없음


> SELECT CASE 0  WHEN 1 THEN '일'
                 WHEN 2 THEN '이'
                 WHEN 3 THEN '삼'
                 ELSE '없음'
  END;
> 없음
```



[top](#)
