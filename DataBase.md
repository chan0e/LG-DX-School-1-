###### DBMS는 ORACLE

데이터 베이스란?

- 여러 사용자가 공유하여 사용할 수 있도록 통합해서 저장한 운영 데이터의 집합

파일 시스템 방식에 단점?

- 실시간 데이터 공유가 불가능
- 데이터의 결함
- 데이터의 중복

👉 따라서, 데이터 베이스는 특정 목적을 위해 여러 사람이 공유해서 사용하고 효율적인 관리와 검색을 위해 구조화 한 데이터 집합

데이터 모델링

현실 대상을 DB로 저장할 수 있도록 설계 및 구축을 하는 과정

과정은❓

![Untitled](https://github.com/chan0e/LG_DX_School_1/assets/94053008/9cba5fa9-7406-44c6-9788-95f127d029ac)


개념적 모델링?

- 현실 세계의 복잡한 대상들을 추상화, 단순화 하여 데이터로 표현하는 과정이고 어떤 데이터를 저장할 것인지 결정하는 단계

![Untitled (1)](https://github.com/chan0e/LG_DX_School_1/assets/94053008/87924fa2-16f5-465e-a54d-2d3a5542732e)


→ ERD를 그림

ERD그리는 순서는?

 개체(사각형) → 속성(원형) → 관계(마름모)

관계 중복(Cardinality)를 기술하는 방법

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/a30a84ca-e868-418d-b3d5-9bd5f4de9cbe/Untitled.png)

관계의 참여도(Optionality)를 기술하는 방법

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/a790e441-a2a6-4898-b105-1640097418b4/Untitled.png)

ERD의 표기법

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/95ca7394-ef80-4a21-89f8-e93849322be7/Untitled.png)

실습❗

```jsx
실제 요구사항

AI캠퍼스에서 학생들의 정보를 관리하는 프로그램을 만들려고 합니다.
학생에 대해 필요한 정보는 학생id, 이름, 과정명, 성별, 나이 ,연락처

과정에 대해서는 과정id, 과정명, 과정기간, 교육장소

이 때 학생은 반드시 하나의 과정에 등록되어야 합니다.
과정은 학생들을 보유하지 않을 수 도 있고,
여러 학생들을 보유하고 있을 수 있습니다.
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/d8a13f2b-f7d6-4089-8a67-d0c04cae30fd/Untitled.png)

이렇게 작성한 이유는?

학생 한명의 입장에서 1 : N 즉, 한명의 학생의 입장에서 봄.

정답)👌 → 과정이 한가지로 의도했을 때 였음. 나는 대학교 수강신청 느낌으로 작성함

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/64ce3fda-8eed-476d-84c7-7bc4c92272c8/Untitled.png)

논리적 모델링

- ERD를 기준으로 개체들을 DBMS가 지원하는 데이터로 변환시키는 과정 즉, 데이터들을 구조적으로 설계하는 과정

→ 식별자 선택, 정규화, 관계설정 등을 진행

정규화 진행

- 데이터가 중복되지 않도록 엔터티를 쪼개는 것

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/a18d9639-45aa-4ad7-803a-f2e50d742727/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/d5943d0b-ccfd-4afa-aad7-bd1488eca57c/Untitled.png)

실습❗

```jsx
직원에 대해 필요한 정보는
직원ID, 이름, 성별, 나이, 연락처, 주소, 부서ID

부서에 대해 필요한 정보는
부서ID, 부서명, 근무지

이 때 직원은 반드시 하나의 부서에 등록
부서는 직원들을 보유하지 않을 수 도 있고,
여러 직원들을 보유하고 있을 수 있다.
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/cdfa4d55-2fb4-4225-a210-896d8982461a/39df60c3-f839-442d-9877-12107eae42ba/Untitled.png)
