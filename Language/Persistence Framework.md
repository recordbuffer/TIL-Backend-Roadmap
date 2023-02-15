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
<br><br>

## ORM Object Relational Mapping
: 객체와 RDBMS를 매핑해 DB의 테이블을 객체 지향적으로 사용하기 위한 기술

#### 📌 Hibernate
: Java를 위한 객체 관계 매핑 프레임워크 <br>
→ 지원하는 메소드 속에서 JDBC API가 동작

<b>JDBC</b> <br>
: 자바에서 DB에 접속할 수 있도록 하는 자바 API

![image](https://user-images.githubusercontent.com/76642597/218939229-c702356e-fcba-45bb-9944-79638c17e566.png)
- Application
- JDBC API : Java 프로그램에서 SQL문 실행하고 결과 검색할 수 있게 하는 API
- Driver Manager : DB와 연결 도움
- JDBC Driver : JDBC API를 통해 데이터 소스와 통신하는 드라이버

▶️ JDBC Template : JDBC의 코어 패키지의 중앙 클래스로 JDBC의 사용을 단순화함


#### 📌 JPA Java Persistence API
: 자바 ORM 기술 표준 <br>
→ 객체지향을 자동으로 관계형 데이터베이스에 맞게 처리(매핑)해주는 기술

<b>특징</b> <br>
- 인터페이스
- 대표적인 구현체가 하이버네이트

<b>장점</b> <br>
- 패러다임 불일치 해결
- 객체 자동 생성로 개발이 편함
- 객체 지향적인 개발 가능
  - 상속
  - 연관 관계
  - 객체의 동일성 보장 
- DB에 독립적인 개발 가능
- 유지보수가 쉬워짐

#### 📌 Spring Data JPA
: Spring Framework에서 제공하는 JPA를 추상화 시킨 Repository Interface 제공해 JPA를 좀 더 편하게 쓸 수 있게 하는 모듈
> You don't need to write the before and after code for persisting, updating, deleting or searching object such as creating Persistence instance, creating EntityManagerFactory instance, creating EntityTransaction instance, creating EntityManager instance, commiting EntityTransaction instance and closing EntityManager.

<br><br>

# ⭐ JPA
## 영속성 관리
: JPA의 EntityManager가 각 엔티티를 영속성 컨텍스트 (Persistence Context)로 관리

#### 📌 Entity Manager Factory
- 하나의 DB당 하나의 EM Factory 생성
- 하나의 EM Factory로 애플리케이션 전체에서 공유
- Entity는 트랜잭션 시작될 때 DB와의 커넥션 풀 생성
- DB와 소통


#### 📌 Persistence Context
: 엔티티를 영구 저장하는 환경 <br>
→ 스프링 컨테이너에 등록된 bean을 찾아 주입

<b>특징</b> <br>
- 영속성 컨텍스트는 엔티티를 식별 값으로 구분함
- 영속성 컨텍스트는 엔티티를 flush로 DB에 반영함


<b>장점</b> <br>
- 1차 캐시 사용
- 동일성 보장
- 트랜잭션을 지원하는 쓰기 지연
- 변경 감지 Dirthy Checking
- 지연 로딩 Lazy Loading


<b>```flush()```</b> <br>
- 직접 호출
- 트랜잭션 커밋
- JPQL 쿼리 실행

<b>Entity Lifecycle</b> <br>
![image](https://user-images.githubusercontent.com/76642597/218954451-88609b1a-351e-4ec3-876a-2aa6b13eeb9e.png)
- 비영속 (New / Transient) : 객체를 생성한 상태
- 영속 (Persistent) : 객체를 저장한 상태 (영속성 컨텍스트가 관리하는 엔티티)
- 준영속 (Detached) : 객체를 영속성 컨텍스트에서 분리한 상태
- 삭제 (Removed)
<br><br>

## 기본키 매핑
- 직접 할당 ```@ID```
- 자동 생성 ```@GeneratedValue```


#### 📌 strategy
<b>IDENTITY</b> <br>
: DB에 기본키 생성을 위임
- ① 엔티티 생성 → 영속성 컨텍스트에 저장
- ② DB insert (+nextval)
- ③ 엔티티에 id 할당

<b>SEQUENCE</b> <br>
: DB 시퀀스 사용해 기본키 생성, allocationSize로 미리 증가시키고 메모리에 시퀀스 값 할당해 사용
- ① DB에서 select nextval
- ② 엔티티 생성 → 영속성 컨텍스트에 저장
- ③ DB insert
- ④ 엔티티에 id 할당

<b>TABLE</b> <br>
: 키 전용 테이블 사용해 기본키 관리

<b>AUTO</b> <br>
: DB에 따라 자동 선택
<br><br>


## 연관 관계 매핑
#### 📌 OneToOne 일대일 연관관계
: 서로 오직 하나뿐인 관계, FK로 연결된 관계 <br>
→ 중복제거를 위해 연관관계의 주인을 정의해 외래키 관리 (mappedBy)

<b>Fetch Join</b> <br>
: default는 EAGER이다.

#### 📌 ManyToOne / OneToMany 다대일 일대일 연관관계
: 제일 흔한 연관 관계
→ 연관관계의 주인(mappedBy)을 설정해주지 않으면 둘의 관계 테이블이 자동으로 생성됨 

<b>Fetch Join</b> <br>
- OneToMany에서 default는 LAZY이다.
- ManyToOne에서 default는 EAGER이다.

#### 📌 ManyToMany 다대다 연관관계
→ 연관관계의 주인(mappedBy)을 설정해주지 않으면 둘의 관계 테이블 각각의 기준 2개 자동으로 생성됨 

<b>Fetch Join</b> <br>
: default는 LAZY이다.



