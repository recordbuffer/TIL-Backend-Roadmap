# 네트워크 기본 
![image](https://user-images.githubusercontent.com/76642597/210188967-9d22dd50-49d0-4c9d-b12f-dd667b39a8e4.png)
래퍼런스 : https://roadmap.sh/backend
<br><br>

## 인터넷 Internet
컴퓨터들이 계층 구조를 이루어 연결되어 있는 것 "Most popular computer network" <br>
TCP/IP 프로토콜 통신을 통해 연결된 컴퓨터 네트워크 통신망

## WWW (World Wide Web)
인터넷으로 연결된 정보 공간

## 프로토콜 Protocol
통신을 위해 정해놓은 절차

## IP
네트워크 통신을 위한 고유주소 → 인터넷 1회선 당 1개의 IP 주소

#### IP 찾기 명령어
```ipconfig```
```nslookup [도메인]```

#### 종류
- 공인 IP (Public IP)
- 사설 IP (Private IP) : 공유기를 사용하는 단말기에 부여하는 비공인 IP

#### MAC 주소 : 장치 고유 주소

#### 도메인 Domain
IP주소에 이름을 부여하는 것 (naver.com -> 220.95.233.172) <br>
→ host : 도메인과 ip를 연결시켜 DNS에 가지 않고 IP 주소를 찾게 해주는 파일

#### DNS (Domain Name Service)
도메인에 해당하는 IP주소를 알려주는 서비스
<br><br>
- ① 컴퓨터에서 DNS 서버에 특정 도메인의 IP 주소 해석 요청
- ② DNS 서버에서 IP 주소 응답
- ③ 컴퓨터는 응답받은 IP 주소로 서버 접속

## Port
컴퓨터 내 프로세스로 가는 주소 (프로그램 식별 / 서버 구분)

#### 종류
- FTP 21
- SSH 22
- Telnet 23
- SMTP 25
- HTTP 80
- HTTPs 443
- Tomcat 8080

#### PID : 프로세스 식별 값


## SSL (Secure Sockets Layer)
사용자가 인터넷을 통해 전송되는 정보를 보증해주는 문서

#### 암호화
  - 대칭키 : 암호화와 복호화를 같은 키로 하는 암호화 기법
  - 비대칭키 : 암호화와 복호화를 다른 키로 하는 암호화 기법
	- 공개키로 암호화, 개인키로 복호화 
	- 개인키로 암호화, 공개키로 복호화 > 데이터 전달한 사람의 신원 인증

#### SSL 인증 절차
  - 1. Client Hello
  - 2. Server Hello
  - 3. 인증서 CA 인증
  - 4. pre master secret 생성
  - 5. session key 생성


## Cloud 
네트워크를 이용해 어디에서나 접근이 가능한 서버를 빌려주는 서비스 
