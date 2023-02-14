# Persistence Framework
![image](https://user-images.githubusercontent.com/76642597/217845495-4c1996a1-3443-43bd-9fce-5710ab5da400.png)
<br>
래퍼런스 : https://roadmap.sh/backend  https://roadmap.sh/java
<br><br>

> 영속성 프레임워크 : 애플리케이션과 DB 사이의 간극을 추상화해주는 연결 도구

## SQL Mapper
: 객체와 SQL문을 매핑해 데이터를 객체화 하는 기술

#### 📌 MyBatis
: 아파치에서 제공하는 SQL Mapper 프레임워크

<b>특징</b> <br>
- 복잡한 쿼리나 다이나믹한 쿼리에 강함
- 자바 프로그램과 SQL 쿼리의 분리로 코드의 간결성, 유지보수성 가짐


## ORM Object Relational Mapping
: 객체와 RDBMS를 매핑해 DB의 테이블을 객체 지향적으로 사용하기 위한 기술

#### 📌 Hibernate
: Java를 위한 객체 관계 매핑 프레임워크 <br>
→ 지원하는 메소드 속에서 JDBC API가 동작

<b>JDBC</b> <br>
: 자바에서 DB에 접속할 수 있도록 하는 자바 API

#### 📌 JPA Java Persistence API
: 자바 객체와 DB 테이블간 매핑 처리하는 ORM 기술 표준 <br>
→ 객체지향을 자동으로 관계형 데이터베이스에 맞게 처리해주는 기술

<b>특징</b> <br>
- 인터페이스
- 대표적인 구현체가 하이버네이트

<b>장점</b> <br>
- 객체 자동 생성로 개발이 편함
- 객체 지향적인 개발 가능
  - 상속
  - 연관 관계
  - 객체의 동일성 보장 
- DB에 독립적인 개발 가능
- 유지보수가 쉬워짐

#### 📌 Spring Data JPA
: Spring Framework에서 제공하는 JPA를 추상화 시킨 Repository Interface 제공해 JPA를 좀 더 편하게 쓸 수 있게 하는 모듈



