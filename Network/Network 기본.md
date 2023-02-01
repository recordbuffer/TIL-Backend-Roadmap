# 네트워크 기본 
![image](https://user-images.githubusercontent.com/76642597/210188967-9d22dd50-49d0-4c9d-b12f-dd667b39a8e4.png)
<br>
래퍼런스 : https://roadmap.sh/backend
<br><br>

## 인터넷 Internet
컴퓨터들이 계층 구조를 이루어 연결되어 있는 것 
> "Most popular computer network" 
<br>
TCP/IP 프로토콜 통신을 통해 연결된 컴퓨터 네트워크 통신망
<br><br>

## WWW World Wide Web
인터넷으로 연결된 정보 공간
<br><br>

## 프로토콜 Protocol
통신을 위해 정해놓은 절차
<br><br>

#### 📌 OSI 기본 참조 모델 [참고: https://www.youtube.com/watch?v=1pfTxp25MA8&feature=youtu.be]
<b>1. 물리 계층 Physical Layer</b> <br>
: 두 대의 컴퓨터가 통신하기 위해 0과 1의 신호를 주고 받을 수 있게 해주는 모듈
- 장치
  - 광 케이블 (랜선)
  - WIFI 공유기
  - 이더넷

<b>2. 데이터 링크 계층 Data Link Layer</b> <br>
: 같은 네트워크 상에 있는 여러 대의 컴퓨터들이 정확한 데이터를 주고 받기 위해 필요한 모듈
- 데이터 단위 : 프레임
- 장치 
  - 랜카드
  - 스위치
  - 라우터

<b>3. 네트워크 계층 Network Layer</b> <br>
: 여러 네트워크로 이루어진 인터넷 속에서 메시지를 정확히 목적지에 전송하기 위해 IP 주소를 통해 길을 찾고 (라우팅) 데이터를 넘겨주는 (포워딩) 모듈
- 데이터 단위 : 패킷
- IP

<b>4. 전송 계층 Transport Layer</b> <br>
: Port 번호를 사용해 메시지를 받는 컴퓨터의 최종 도착지인 프로세스까지 데이터가 도달하게 하는 모듈
- 데이터 단위 : 세그먼트

<b>5. 세션 계층 Session Layer</b> <br>
<b>6. 표현 계층 Presentation Layer</b> <br>
<b>7. 응용 계층 Application Layer</b> <br>

#### 📌 TCP/IP
→ TCP Transmission Control Protocol : 두 호스트를 연결해 데이터 스트림을 교환 담당
→ IP Internet Protocol : 데이터 전송 담당

- 통신 방식 <3 Way Handshake>
  - ① SYN
  - ② SYN/ACK
  - ③ ACK
<br><br>

## IP
네트워크 통신을 위한 고유주소 → 인터넷 1회선 당 1개의 IP 주소

#### 📌 IP 찾기 명령어
```ipconfig```
```nslookup [도메인]```

#### 📌 종류
- 공인 IP (Public IP)
- 사설 IP (Private IP) : 공유기를 사용하는 단말기에 부여하는 비공인 IP

#### 📌 MAC 주소 : 장치 고유 주소

#### 📌 도메인 Domain
IP주소에 이름을 부여하는 것 (naver.com -> 220.95.233.172) <br>
→ host : 도메인과 ip를 연결시켜 DNS에 가지 않고 IP 주소를 찾게 해주는 파일

#### 📌 DNS Domain Name Service
도메인에 해당하는 IP주소를 알려주는 서비스
<br><br>
- ① 컴퓨터에서 DNS 서버에 특정 도메인의 IP 주소 해석 요청
- ② DNS 서버에서 IP 주소 응답
- ③ 컴퓨터는 응답받은 IP 주소로 서버 접속
<br><br>

## Port
컴퓨터 내 프로세스로 가는 주소 (프로그램 식별 / 서버 구분)

#### 📌 종류
- FTP 21
- SSH 22
- Telnet 23
- SMTP 25
- HTTP 80
- HTTPs 443
- Tomcat 8080

#### 📌 PID : 프로세스 식별 값
- 포트의 PID 확인 명령어
```netstat -a -o [포트번호]```

- PID 죽이는 명령어
```taskkill /f /[PID]```
<br><br>

## HTTP Hypertext Transfer Protocol
서버와 클라이언트가 인터넷 상에서 데이터를 주고 받기 위한 무상태 프로토콜 방식

- 발전 과정
  - HTTP 1.0 : TCP/UDP 기반 비연결성 프로토콜 → Keep Alive 해결
  - HTTP 1.1 : FIFO 파이프라이닝 적용 → HOL Blocking 발생
  - HTTP 2.0 : 멀티 플랙싱 → 여러개의 스트림을 사용해 송수신

- 메시지
  - 구조 
    - 시작줄
    - 헤더
    - 본문
  - 메서드
    - GET
    - POST
    - PUT
    - HEAD
    - FETCH
    - TRACE
    - OPTION
    - DELETE   
<br><br>

## SSL Secure Sockets Layer
사용자가 인터넷을 통해 전송되는 정보를 보증해주는 문서

#### 📌 암호화
  - 대칭키 : 암호화와 복호화를 같은 키로 하는 암호화 기법
  - 비대칭키 : 암호화와 복호화를 다른 키로 하는 암호화 기법
	- 공개키로 암호화, 개인키로 복호화 
	- 개인키로 암호화, 공개키로 복호화 > 데이터 전달한 사람의 신원 인증

#### 📌 SSL 인증 절차
  - ① Client Hello
  - ② Server Hello
  - ③ 인증서 CA 인증
  - ④ pre master secret 생성
  - ⑤ session key 생성
<br><br>

## Cloud 
네트워크를 이용해 어디에서나 접근이 가능한 서버를 빌려주는 서비스 
