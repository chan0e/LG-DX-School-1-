###### DBMS는 ORACLE

## 데이터 베이스란?

- 여러 사용자가 공유하여 사용할 수 있도록 통합해서 저장한 운영 데이터의 집합

### 파일 시스템 방식에 단점?

- 실시간 데이터 공유가 불가능
- 데이터의 결함
- 데이터의 중복

👉 따라서, 데이터 베이스는 특정 목적을 위해 여러 사람이 공유해서 사용하고 효율적인 관리와 검색을 위해 구조화 한 데이터 집합

## 데이터 모델링

현실 대상을 DB로 저장할 수 있도록 설계 및 구축을 하는 과정

과정은❓

![Untitled](https://github.com/chan0e/LG_DX_School_1/assets/94053008/9cba5fa9-7406-44c6-9788-95f127d029ac)


### 개념적 모델링?

- 현실 세계의 복잡한 대상들을 추상화, 단순화 하여 데이터로 표현하는 과정이고 어떤 데이터를 저장할 것인지 결정하는 단계

![Untitled (1)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/87924fa2-16f5-465e-a54d-2d3a5542732e)


→ ERD를 그림

### ERD그리는 순서는?

 개체(사각형) → 속성(원형) → 관계(마름모)

### 관계 중복(Cardinality)를 기술하는 방법

![Untitled (2)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/5583f1cf-1385-404c-b132-ba8aa532ad3c)


### 관계의 참여도(Optionality)를 기술하는 방법
![Untitled (3)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/620415f5-0761-4eb6-878e-5fce31d1db97)



### ERD의 표기법

![Untitled (4)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/709fb44b-cd1c-4825-a3a8-f3c13a040bf4)


### 실습❗

```jsx
실제 요구사항

AI캠퍼스에서 학생들의 정보를 관리하는 프로그램을 만들려고 합니다.
학생에 대해 필요한 정보는 학생id, 이름, 과정명, 성별, 나이 ,연락처

과정에 대해서는 과정id, 과정명, 과정기간, 교육장소

이 때 학생은 반드시 하나의 과정에 등록되어야 합니다.
과정은 학생들을 보유하지 않을 수 도 있고,
여러 학생들을 보유하고 있을 수 있습니다.
```
![Untitled (5)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/bd2f0c14-aaa3-4af1-8c48-56a681d9fa57)



이렇게 작성한 이유는?

학생 한명의 입장에서 1 : N 즉, 한명의 학생의 입장에서 봄.

정답)👌 → 과정이 한가지로 의도했을 때 였음. 나는 대학교 수강신청 느낌으로 작성함

![Untitled (6)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/7a8ced61-3f26-4103-803d-491e9184ebc4)


### 논리적 모델링

- ERD를 기준으로 개체들을 DBMS가 지원하는 데이터로 변환시키는 과정 즉, 데이터들을 구조적으로 설계하는 과정

→ 식별자 선택, 정규화, 관계설정 등을 진행

### 정규화 진행

- 데이터가 중복되지 않도록 엔터티를 쪼개는 것

![Untitled (7)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/b506253b-446c-4a6d-bf3a-8e2e0811e8de)

![Untitled (8)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/12b3b5e0-f1f4-4d2a-8cca-0f3431948c91)



### 실습❗

```jsx
직원에 대해 필요한 정보는
직원ID, 이름, 성별, 나이, 연락처, 주소, 부서ID

부서에 대해 필요한 정보는
부서ID, 부서명, 근무지

이 때 직원은 반드시 하나의 부서에 등록
부서는 직원들을 보유하지 않을 수 도 있고,
여러 직원들을 보유하고 있을 수 있다.
```

![Untitled (9)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/9d8705f0-a8d8-4f7a-ab7a-b645ade0a1a2)



## 제약 조건

### **primary key(PK)**

- 식별자를 물리적 모델링 한 것, not null + unique = null 불가 + 중복 불가
- “식별자”는 테이블에서 행을 식별할 수 있는 컬럼

### **unique key(UK)**

- PK와 다르게 null 값 입력가능 단, 중복은 불가

### **not null**

- null 불가능

### **check**

- 지정한 데이터만 입력 가능

### **foreign key(FK)**

- 외래키, 테이블끼리 연결되어 있는 관계를 물리적 모델링 한 것
- 다른 테이블의 기본키를 참조하는 속성의 집합
- FK를 사용하면 데이터 무결성

### **무결성**

- 데이터에 결함이 없는 상태

### **무결성 제약조건**

- 개체 무결성  : 기본키를 구성하는 속성은 null 값을 가질 수 없음
- 참조 무결성 :  외래키는 참조할 수 없는 값을 지닐 수 없음

실습❗

```sql
alter table 테이블명 add constraint 제약조건 제약조건(컬럼);

-- pk
alter table 사원 add constraint 사원_사원ID_PK primary key(사원ID);

-- fk
-- 1. 부서 테이블의 부서코드 칼럼이 uk or pr가 아니기 때문에 참조가 불가능!
-- ORA-02270: no matching unique or primary key for this column-list
alter table  사원 add constraint 사원_부서코드 foreign key(부서코드) 
REFERENCES 부서(부서코드);

```

```sql
실습 문제

--1. 네이버 회원 테이블 생성
drop table 네이버회원;

create table 네이버회원(
    Naver_ID varchar2(15)
    , Naver_name varchar2(12) not null
    , Naver_pw varchar2(16)
    , Naver_birth date
    , Naver_gender varchar2(3)
);

--1.1 네이버 회원 테이블 제약조건 추가

alter table 네이버회원 
add constraint 네이버회원_ID_PK
primary key(Naver_ID);

alter table 네이버회원 
add constraint 성별제약조건_CK
check(Naver_gender IN('남','여'));

--2. 네이버 블로그 테이블 생성
drop table 네이버블로그;
create table 네이버블로그(
    Blog_Number number
    ,Blog_title varchar(100) not null
    , Naver_ID varchar2(15)

);

--2.1 네이버 블로그 테이블 제약조건
alter table 네이버블로그
add constraint 블로그_ID_PK
primary key(Blog_Number);

alter table 네이버블로그
add constraint 블로그_ID_FK
foreign key(Naver_ID) references 네이버회원(Naver_ID);
```

