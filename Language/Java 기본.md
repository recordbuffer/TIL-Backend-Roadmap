# Java 기본
![image](https://user-images.githubusercontent.com/76642597/216765648-8abda3ea-b526-47fc-a62a-a4f52d9026a7.png)
<br>
래퍼런스 : https://roadmap.sh/backend  https://roadmap.sh/java
<br><br>

> Write Once, Run Anywhere

## 객체 지향 프로그래밍 Object Oriented Programming (OOP)
데이터를 객체화해 부품처럼 쓸 수 있는 언어

#### 📌 객체화
데이터(속성) + 기능
→ 행동, 상태, 식별자을 부여

- 행동
- 상태
- 식별자


<b>객체화의 장점</b> <br>
- 유연성
- 자율성
- 유지보수성
- 가비지 컬렉터
- 다형성
- 캡슐화
<br><br>

## 동작 과정
- JDK Java Development Kit : 자바 개발 도구
- JRE Java Runtime Environment : 자바 코드가 실행되기 위한 최소 환경
- JVM Java Virtual Machine : .class 파일이 실행되기 위한 환경 

1. .java파일이 javac에 의해 .class 파일로 컴파일됨
2. .class파일은 JVM의 메모리 영역에 로딩됨
- JVM Memory (Runtime Data Area)
  ![image](https://user-images.githubusercontent.com/76642597/216766046-03a94064-21df-4cb9-8c72-53994b3e80e6.png)

  - Metaspace (=Method Area / Static Area / Class Area)
  - Heap
  - Java Stacks
  - PC Register
  - Native Method Stack

3. 운영체제에 맞게 컴파일 후 실행 (main 함수 호출)
- Interpreter
- JTI Compiler
- Profiler
- Garbage Collector

#### 📌 Static vs Stack vs Heap
<b>Static</b> <br>
: class 파일의 byte code가 로드되는 곳
- 클래스 로딩 : .class 파일을 찾아 메모리에 로딩해 메서드를 호출하는 과정
→ JVM 시작부터 종료까지 메모리에 있는 데이터

<b>Stack</b> <br>
: 메서드 내 선언된 지역변수와 매개변수를 저장하는 곳
→ 메서드 호출될 떄 메모리에 할당, 종료되면 삭제
→ 실제 주소는 힙 영역에 저장됨

<b>Heap</b> <br>
: new 연산자 통해 생성된 인스턴스 변수를 저장하는 곳
→ 메서드 호출 끝나도 사라지지 않음
→ 주소 잃어버려 가비지 컬렉터가 지우거나 JVM이 종료될 때 사라짐
<br><br>

## 값
#### 📌 변수 Variable
: 변할 수 있는 하나의 값을 저장할 수 있는 메모리 공간

<b>변수의 종류</b> <br>
- 인스턴스 변수 
  - 클래스 영역에 선언
  - 클래스의 인스턴스가 생성될 때 생성
  - 인스턴스마다 독립적인 저장 공간 가짐
- 클래스 변수
  - static + 인스턴스 변수
  - 클래스 영역에 선언
  - 클래스가 메모리에 로딩됐을 때 생성
  - public을 붙이면 전역변수로 사용 가능
  → 공통으로 사용되는 것에 사용함 (메모리 할당을 한번만 하고 같은 메모리 주소를 공유)
- 지역 변수
  - 클래스 영역 외의 영역에 선언 (메서드, 생성자 등)
  - 변수 선언문이 수행되었을 때 생성
  - 사용 전 반드시 
 
 #### 📌 상수 Constant
 : 변하지 않는 값
 
 <b>리터럴</b> <br>
: 값 그 자체
<br><br>

## 객체
: 클래스에 정의된 대로 메모리에 생성된 것
→ 속성과 기능이 묶인 프로그램 단위

- 속성 : 객체가 가진 고유한 특성
- 기능 : 객체의 행동 패턴

#### 📌 클래스 Class
: 고유성을 가진 객체가 모여 개념화된 특성

> 클래스 → 객체로 만드는 과정 (인스턴스화) →객체 (인스턴스)

#### 📌 메서드 Method
: 객체간 고류되는 프로그램화한 명령 메시지 단위 (객체의 기능)

<b>메서드의 구조</b> <br>
![image](https://user-images.githubusercontent.com/76642597/216767166-42b90912-78fb-459e-b0d6-83ec8e9c4b91.png)

- 선언부
  - 접근제한자 
    - public : 제한 없이 접근 가능
    - protected : 같은 패키지 내에서만 접근 가능, 상속받으면 접근 가능
    - default : 같은 패키지 내 클래스에서만 접근 가능 
    - private : 같은 클래스 내에서만 접근 가능
  - 반환형 : 메서드 작업 수행 결과 타입
  - 매개변수 : 메서드 작업 수행에 필요한 전달받을 값 (인자)  
- 구현부
  - 지역변수 : 메서드 내에서 선언된 변수
  - return문 : 선언부 반환형이 void가 아닌 경우의 결과 값

<b>메서드의 종류</b> <br>
- 인스턴스 메서드
  - 일반 메서드
  - 메서드 작업 수행시 인스턴스 변수를 필요로 하는 메서드 
- 클래스 메서드
  - static + 메서드
  - 객체를 생성하지 않고 메서드 호출 가능
  - 인스턴스와 관련 없는 메서드
  - Util성 메서드에서 많이 사용함

#### 📌 패키지 Package
: 클래스와 인터페이스의 묶음
→ 서로 관련있는 클래스들끼리 그룹 단위로 묶어 효율적으로 관리

#### 📌 생성자 Constructor
: 인스턴스가 생성될 떄 호출되는 인스턴스 초기화 메서드

- 기본 생성자 : 클래스에 정의된 생성자가 하나도 없을 때 컴파일러가 자동으로 제공
- 매개변수 생성자 : 인스턴스를 생성함과 함께 원하는 값으로 초기화할 수 있음

<b>this</b> <br>
: 인스턴스 자신을 가리키는 참조 변수
→ 생성자에서 다른 생성자를 호출할 때

#### 📌 제어자 Modifier
<b>접근제어자</b> <br>

<b>static</b> <br>

<b>fianl</b> <br>

<b>abstract</b> <br>


