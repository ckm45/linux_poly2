---
layout: home
---

# SSH

# SSH

## SSH란?

Secure Sell의 약자로 원격지에 있는 컴퓨터를 안전하게 제어하기 위한 프로토콜 또는 이 프로토콜을 사용하는 프로그램들을 의미한다. SSH 클라이언트와 SSH 서버의 관계로 상호작용하면서 SSH 서버가 설치된 운영체제를 제어한다. 클라이언트와 서버 사이에는 강력한 암호화 방법을 통해서 연결되어 있기 때문에 데이터를 중간에서 가로채도 해석 할 수 없는 암호화된 문자만이 노출된다. 지금까지는 Telnet을 주로 사용했는데 이것을 대체하기 위한 통신 방법이다.

- TCP 상에 보안 채널(터널링)을 형성하여 기타 응용 프로토콜들이 안전하게 데이터를 교환
- 적은 비용으로, 비교적 쉽게 구현 가능하고, 안전하여 널리 사용됨
- 서버 접속 시 비밀번호 대신 **비대칭키**를 제출하는 방식
- 기본적(Default)으로 TCP 22번 포트를 사용하여 통신

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3c6dceba-6690-4f87-b35b-cdd80334460a/Untitled.png)

### 

## **SSH 클라이언트**

리눅스와 Mac과 같은 Unix 계열의 운영체제는 기본적으로 SSH 클라이언트가 설치 되어 있기 때문에 SSH를 이용하기 위해서 특별한 클라이언트가 필요하지 않다. 하지만 SSH 는 윈도우 운영체제에는 SSH 클라이언트가 설치되어 있지 않다. SSH 클라이언트를 설치해야 윈도우에서 Unix 계열의 운영체제를 제어 할 수 있다. 대표적인 SSH 클라이언트는 아래와 같은 것들이 있다.

- PuTTY
- Xshell

## **SSH 서버**

SSH는 Unix 계열의 운영체제를 원격에서 제어하기 위한 방법이다. 그렇기 때문에 원격지에 있는 윈도우 운영체제를 SSH로 제어 하는 것은 일반적이지 않다. 윈도우에는 클라이언트 운영체제로 사용할 수 있을 뿐이다. 유닉스 계열의 운영체제에서는 OpenSSH가 가장 많이 사용된다. OpenSSH는 SSH 클라이언트와 서버를 포함한다. Mac은 SSH 클라이언트와 서버가  이미 설치 되어 있기 때문에 SSH를 이용하기 위해서 특별한 조치는 필요하지 않다.

## 비대칭 키

### 구성

SSH 인증절차엔 **비대칭키 알고리즘**이 사용되며 두 종류의 키로 구성

| 종류 | 기능 | 위치 |
| --- | --- | --- |
| public key | 메시지 암호화 | 원격 머신 (SSH Server) |
| private key | 메시지 복호화 | 로컬 머신 (SSH Client) |

### 동작 방식

- **public key**로 암호화한 내용은 **private key**로 복호화가 가능
- **private key**로 암호화한 내용은 **public key**로 복호화가 가능
- **private key**는 자신만 가지고 있는 단일 소유권이고 **public key**는 여러 사용자가 소유할 수 있는 분산 소유권
- 공유된 **public key**로 암호화하여 단일 **private key**로 복호화
- 만일 **private key**로 암호화할 경우, 여러 사용자로부터 복호화가 가능하기에 권장되지 않음

![image](https://user-images.githubusercontent.com/127702320/234424920-07c40a07-9c90-4ecc-93f4-fc6f493f81cb.png)

## 동작 과정

### Step 1. 원격 접속 요청 ( 클라이언트 -> 서버 )

1. 클라이언트가 서버에 원격 접속하기 위해 서버의 TCP 22번 포트로 SSH 접속 요청
2. 서버는 클라이언트에게 서버가 지원하는 프로토콜의 버전을 응답
3. 클라이언트는 서버로부터 응답받은 버전 중 일치하는 것이 있다면 연결을 지속

### Step 2. Public key 전송 ( 서버 -> 클라이언트 )

1. 서버는 클라이언트로부터 SSH 접속 요청을 수신
2. 서버의 **public key**를 클라이언트에게 전송
3. 클라이언트는 서버로부터 받은 **public key**를 저장

### Step 3. 보안 채널 확립 ( 클라이언트 <-> 서버 )

1. 서버 인증 ( 클라이언트 -> 서버 )
2. 암호화 통신을 위한 세션키(대칭키) 생성
3. 클라이언트 인증 ( 서버 -> 클라이언트 )

### Step 4. 접속 성공

세션 키를 통해 클라이언트와 서버 간 네트워크 통신 진행