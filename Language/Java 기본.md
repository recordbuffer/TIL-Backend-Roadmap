# Java 기본
![image](https://user-images.githubusercontent.com/76642597/216814108-bfc73454-9705-4d94-a493-62af7b2cfd9f.png)
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
  - 사용 전 반드시 초기화
 
 #### 📌 상수 Constant
 : 변하지 않는 값
 
 <b>리터럴</b> <br>
: 값 그 자체
<br><br>

## 객체
: 클래스에 정의된 대로 메모리에 생성된 것 (인스턴스 변수의 집합)
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
: 인스턴스가 생성될 때 호출되는 인스턴스 초기화 메서드

- 기본 생성자 : 클래스에 정의된 생성자가 하나도 없을 때 컴파일러가 자동으로 제공
- 매개변수 생성자 : 인스턴스를 생성함과 함께 원하는 값으로 초기화할 수 있음

<b>this</b> <br>
: 인스턴스 자신을 가리키는 참조 변수
→ 생성자에서 다른 생성자를 호출할 때

#### 📌 제어자 Modifier
<b>접근제어자</b> <br>
- public : 제한 없이 접근 가능
- protected : 같은 패키지 내에서만 접근 가능, 상속받으면 접근 가능
- default : 같은 패키지 내 클래스에서만 접근 가능 
- private : 같은 클래스 내에서만 접근 가능

<b>static</b> <br>
: 인스턴스를 생성하지 않고 공통으로 사용할 수 있는 것에 붙임
→ 멤버 변수, 메서드, 초기화 블록에서 사용

<b>fianl</b> <br>
- final + 변수 = 상수
- final + 메서드 = @Overriding 사용 X
- final + 클래스 = 상속 X
→ 멤버 변수, 메서드, 클래스, 지역변수에서 사용

<b>abstract</b> <br>
: 메서드의 선언부만 작성되고, 실제 수행 내용은 구현하지 않은 
→ 클래스, 메서드에서 사용
<br><br>

## 상속 Inheritance
: 기존의 클래스를 재사용해 새로운 클래스를 작성하는 것
> 상속을 받는 것은 부모 클래스를 자식 클래스로 확장한다는 것이다 (extends)

→ 생성자와 초기화 블록은 상속 X <br>
→ 멤버만 상속됨

#### 📌 Super
: 자식 클래스에서 부모 클래스로부터 상속 받은 멤버를 참조할 때 사용되는 참조 변수
→ 상속을 받았으니 자신의 멤버이기도 해 this를 사용할 수 있지만 구별을 위해 super 사용 <br>
→ static 메서드에서는 사용 X

```super()``` : 부모 클래스의 생성자를 호출하는데 사용
<br><br>

## 다형성 Polymorphism
: 하나의 클래스나 메서드를 여러 가지 방법으로 사용하는 기법
![image](https://user-images.githubusercontent.com/76642597/216814512-671b496f-3d9b-45e6-a105-02c080cc2a75.png) <br>
→ 클래스의 다형성을 통해 도형의 타입으로 원의 객체와 삼각형의 객체를 사용할 수 있다.

```
class 도형 {
  String 모양;
  String 이름;
}

class 원 extends 도형 {
  float 반지름;
}

// 참조변수 타입에 따라 사용할 수 있는 멤버 개수도 달라짐
public class polymorphism() {
  원 a = new 원;
  도형 b = new 원;
  a.반지름(); 
  b.반지름();    //에러!
}
```

#### 📌 형변환 Casting
- 업 캐스팅 : 자식 타입의 참조 변수를 부모 타입의 참조 변수로 변환하는 것
- 다운 캐스팅 : 부모 타입의 참조 변수를 자식 타입의 참조 변수로 변환하는 것


<b>참조 변수가 참조하고 있는 인스턴스의 실제 타입을 알아내는 연산자</b> <br>
- ```instanceof```
→ 조건문에서 주로 사용

<br><br>

## 추상화 Abstraction
: 클래스 간의 공통점을 찾아내 공통의 조상을 만드는 작업
> 객체가 접근을 허용하는 부분만 공유

#### 📌 추상 클래스
: 추상 메서드를 포함하고 있는 클래스

#### 📌 추상 메서드
: 선언부(메서드명, 매개변수, 반환타입)만 작성하고 구현부는 작성하지 않은 채로 남겨 둔 메서드
→ 자식 클래스는 오버라이딩이 강제화되어 자식에 맞게 구현부를 작성해 사용함

#### 📌 인터페이스 Interface
: 상수만 멤버로 가질 수 있는 추상 클래스

![image](https://user-images.githubusercontent.com/76642597/216814993-10cac614-a782-4926-a110-63d426381940.png)

> 인터페이서는 작업 명세서이며 말 그대로 명세서에 따라 구현하는 것이다 (implements)

→ 객체 생성 X <br>
→ 메서드 호출 사용 X

<b>사용 이유 및 장점</b> <br>
- 독립적인 프로그래밍 가능
- 개발 시간 단축
- 표준화 가능
- 서로 관계 없는 클래스들에게 관계 맺어줄 수 있음
- 객체와 개발 코드간의 접점 역할

> 인터페이스는 실제 구현 내용을 감싸는 껍데기며, 클래스를 사용하는 쪽에서는 해당 클래스안에 코드를 몰라도 되며 또 실제로 구현되어 있지 않더라고 해도 문제되지 않는다

<br><br>


## 예외처리
: 예외를 사전에 예측하고 방어하기 위한 코드
→ 프로그램의 비정상 종료를 막기 함위함

#### 📌 오류
- 컴파일 에러 : 컴파일 시 발생하는 에러 (일반적인 문법 에러)
- 런타임 에러 : 프로그램 발생 시 발생하는 에러

#### 📌 에러 Error vs 예외 Exception
- 에러 : 프로그램 코드에 의해 수습될 수 없는 심각한 오류
- 예외 : 프로그램 코드에 의해 수습될 수 있는 다소 미약한 오류 (대처 가능)

![image](https://user-images.githubusercontent.com/76642597/216815259-3b9cba5f-5b26-4fc7-bbf8-b9b25f774273.png)

<b>try-catch</b> <br>
: 예외가 발생한 곳에서 직접 처리하는 경우 사용

<b>fianlly</b> <br>
: try-catch문 끝에 선택적으로 덧붙여 사용
→ 예외 발생 여부와 상관없이 실행되어야 할 코드 작성

<b>throw</b> <br>
: 개발자가 고의로 예외 발생할 경우 사용

<b>throws</b> <br>
: 예외 처리를 호출한 메서드에 넘기는 경우 사

<br><br>

## 컬렉션 Collection 
: 객체 그룹의 하나의 단위를 대표하는 것
#### 📌 자바 컬렉션 프레임워크 JCF
: 자바에서 제공하는 기본 자료 구조 프레임워크

![image](https://user-images.githubusercontent.com/76642597/216815399-238823ab-aac2-44e7-8a28-8b0ee0624fbb.png)


<b>List</b> <br>
: 순서가 있는 데이터 구조
→ 인덱스로 관리 <br>
→ 중복 저장 가능 <br>
- ArrayList
- LinkedList


<b>Set</b> <br>
: 집합처럼 순서 없고 중복 안되는 데이터 구조
- LinkedSet
- HashSet
- LinkedHashSet
- TreeSet : 이진 검색 트리 자료 구조 형태

<b>Map</b> <br>
: 키와 값으로 이루어진 데이터 구조
→ 키는 중복되지 않고 값은 중복됨 <br>
→ 순서 없음 <br>
- HashMap
- TreeMap
- LinkedHashMap
- Properties : 주로 애플리케이션의 환경 설정과 관련된 속성 저장

<b>Iterator</b> <br>
: 컬렉션에 저장된 각 요소에 접근하는 기능을 가진 인터페이스

<b>Comparator & Comparable</b> <br>
: 컬렉션을 정렬하는데 필요한 메서드 정의하는 인터페이스

<b>Collections </b> <br>
: static 메서드가 따로 저장된 컬렉션 클래스
- Singleton Collection : 단 하나의 객체만 저장하는 컬렉션 만들고 싶은 경우 사용

<br><br>

## 제네릭 Generic
: 다양한 타입의 객체들을 다루는 메서드나 컬렉션 클래스를 컴파일 할 때 타입 체크를 해주는 기능

#### 📌 제네릭 타입 Generic Type
: 데이터 형식에 의존하지 않고 하나의 값이 여러 다른 데이터 타입을 가질 수 있도록 하는 방법

<b>extends</b> <br>
: 제네릭 타입에 특정 타입의 자식들만 대입할 수 있게 제

<br><br>

## 쓰레드 Thread
: 프로세스의 자원을 이용해 실제 작업을 수행하는 것 (작업의 단위)
→ 여러 개의 쓰레드가 하나의 프로세스를 이룸

<b>쓰레드의 장점</b> <br>
- 적은 메모리 사용
- 빠른 프로세스 생성

<b>쓰레드의 단점</b> <br>
- 교착상태에 빠질 수 있음

#### 📌 멀티 쓰레드 Multi Thread
: 하나의 프로세스 내에서 여러 쓰레드가 동시에 작업을 수행 할 수 있는 것

#### 📌 동기화
: 하나의 쓰레드가 진행 중인 작업을 다른 쓰레드가 간섭하지 못하게 막는 것
- Synchronized
- Lock

<br><br>

## 람다식 Lamda
: 메서드를 하나의 식으로 표현한 것 = 익명 클래스의 객체
> 자바는 JDK1.8에서 람다식을 도입하며 객체 지향 언어인 동시에 함수형 언어가 되었다

→ 메서드의 이름과 반환 값이 제거되고 선언부와 구현부 사이에 ```- >``` 가 추가됨

#### 📌 함수형 인터페이스
: 변수처럼 메서드를 주고받을 수 있으므로 참조 변수로 다룰 수 있게 

<br><br>

## 스트림 Stream
: 데이터 소스를 추상화하고, 데이터를 다루는데 자주 사용되는 메서드를 정의해 놓은 것

<b>특징</b> <br>
- 일회용이다
- 작업을 내부 반족으로 처리함
- 병렬 처리가 쉬

<br><br>

## 입출력 I/O
: 외부 장치와 프로그램 간에 데이터를 주고 받는 것

#### 📌 스트림 Stream
: 입출력 시 두 대상 사이에서 데이터를 운반하는데 사용되는 연결부
→ 단방향 (FIFO구조)

![image](https://user-images.githubusercontent.com/76642597/216815940-5cb07361-abcf-4ce5-aa2f-b7b0b54f874b.png)

<b>바이트 기반 스트림</b> <br>
: 바이트 단위로 데이터를 전송하는 스트림
- Input Stream
    - FileInputStream
    - ByteArrayInputStream
- OutputStream
    - FileOutputStream
    - ByteArrayOutputStream
- 보조 스트림 : 데이터 입출력 기능은 없지만 기능을 향상시키기 위해 사용
    - FilterInputStream / FilterOutputStream
    - BufferedInputStream / BufferedOutputStream


<b>문자열 기반 스트림</b> <br>
: 문자 단위(2Byte)로 데이터를 전송하는 스트림
- Reader
    - FileReader
    - StringReader
- Writer
    - FileWriter
    - StringWriter
- 보조 스트림
    - FilterReader / FilterWriter
    - BufferedReader / BufferedWriter

<br><br>

## 직렬화 Serialization
: 객체를 데이터 스트림으로 만드는 것

#### 📌 Serializable 
: 직렬화하고자 하는 클래스가 Serializable 인터페이스를 구현

#### 📌 SerialVersionUID
: 객체가 직렬화될 때 클래스에 정의된 멤버들의 정보를 이용해 자동 생성한 클래스 버전 정보

<br><br>



