---
layout: home
--- 

# WAS(웹 어플리케이션 서버, Web Application Server)

## 🔶 Web Server(웹 서버)

웹서버란 `HTTP 프로토콜을 기반`으로 클라이언트가 웹브라우저에서 어떠한 요청을 하면 그 요청을 받아 정적 콘텐츠를 제공하는 서버

→ 정적 컨텐츠는 원래 서버 컴퓨터에 저장, 이 서버의 특정 폴더, 디렉토리에 이 컨텐츠들을 넣어 놓으면 이 폴더를 외부에서 접근 가능하도록 개방해서 서버에 지정된 웹사이트 주소롤 접속하면 이것들을 받아갈 수 있도록 하는 것이 웹서버의 기본적인 역할

ex) 정적 콘텐츠: 단순 HTML 문서, CSS, 이미지, 파일 등 즉시 응답 가능한 컨텐츠

<aside>
📌 **HTTP (Hypertext Transfer Protocol)**

인터넷에서 데이터를 전송하기 위한 프로토콜 중 하나입니다. 주로 웹 브라우저와 웹 서버 간의 통신에 사용

HTTP는 클라이언트(웹 브라우저)와 서버(웹 서버) 간에 일종의 약속
웹 브라우저가 서버에게 데이터를 요청하면, 서버는 요청에 대한 데이터를 보내줍니다. 이때 데이터는 일반적으로 텍스트 형식으로 이루어져 있고, 요청과 응답은 HTTP 헤더와 본문으로 구분

HTTP는 TCP/IP 프로토콜을 기반으로 동작하기 때문에, 클라이언트와 서버 사이에서 데이터를 안전하고 신속하게 전송 가능

</aside>

→ 이때, 웹 서버가 정적 컨텐츠가 아닌 동적 컨텐츠를 요청 받으면 WAS에게 해당 요청을 넘겨주고, WAS에서 처리한 결과를 클라이언트에게 전달하는 역할

ex) 웹서버: Apache, NginX

위의 프로그램들로 컨텐츠가 저장되어 있는 한 폴더를 개방해 그 안에 들어있는 HTML 파일들로 웹사이트 제공

→ 서버에 정해진 사이트 주소로 접속을 하면 그 파일들을 꺼내서 웹 사이트를 꺼내게끔!

→ 그런데 정적 웹을 꺼내는 것.(블로그 페이지나 회사 소개 페이지처럼 안의 내용이 바뀔 일이 없는 웹페이지를 고정된 HTML, CSS, 자바스크립트로 제공)
<br/><br/><br/>

## 🔶 WAS

DB조회 혹은 다양한 로직 처리를 요구하는 동적 컨텐츠를 제공하기 위해 만들어진 Application 서버

HTTP 프로토콜을 기반으로 사용자 컴퓨터나 장치에 애플리케이션을 수행해주는 미들웨어로 주로, 데이터베이스 서버와 같이 수행

이러한 WAS는 웹 서버의 기능들을 구조적으로 분리하여 처리하고자 하는 목적으로 제시됨

분산 트랜잭션, 보안, 메시징, 쓰레드 처리 등의 기능을 처리하는 분산 환경에서 사용 

WAS는 프로그램 실행 환경과 DB 접속 기능을 제공하고, 여러 개의 트랜잭션을 동시에 관리할 수 있으며, 비즈니스 로직을 처리할 수 있습니다. 이러한 기능들을 제공함으로써, WAS는 웹 애플리케이션을 보다 안정적이고 확장 가능한 방식으로 운영할 수 있게 해줌
<br/><br/><br/>

<aside>
📌 **분산환경**

분산 환경이란, 여러 대의 컴퓨터가 네트워크를 통해 연결되어, 하나의 큰 시스템처럼 동작하는 환경을 의미합니다. 이러한 분산 환경에서는 여러 대의 컴퓨터에서 수행되는 작업들이 복잡해지기 때문에, 분산 트랜잭션, 보안, 메시징, 쓰레드 처리 등의 기능들이 필요합니다.

- 분산 트랜잭션: 여러 대의 컴퓨터에서 수행되는 트랜잭션을 관리하는 기능입니다. 분산 트랜잭션은 모든 컴퓨터에서 트랜잭션의 일관성을 유지하고, 문제 발생 시 롤백하는 기능을 제공합니다.
- 보안: 분산 환경에서는 데이터의 안전성이 중요합니다. 따라서 WAS는 인증, 권한 부여, 암호화 등의 보안 기능을 제공하여 데이터를 안전하게 처리할 수 있도록 합니다.
- 메시징: 분산 환경에서는 여러 대의 컴퓨터 간에 데이터를 전달하고 처리해야 합니다. 이를 위해 WAS는 메시징 기능을 제공하여, 메시지를 전송하고 처리할 수 있도록 합니다.
- 쓰레드 처리: 분산 환경에서는 여러 대의 컴퓨터에서 동시에 작업을 처리해야 합니다. 이를 위해 WAS는 쓰레드 처리 기능을 제공하여, 여러 작업을 동시에 처리할 수 있도록 합니다.

이러한 기능들을 제공함으로써, WAS는 분산 환경에서 안정적이고 확장 가능한 서비스를 제공할 수 있게 됩니다.

</aside>
<br/><br/><br/>
ex) was: Tomcat, JBoss, WebSphere

→ 요즘에는 스프링 부트에 톰캣이 내장되기 때문에 직접은 많이 접하지 않지만 

자바랑 JSP로 만든 웹 또는 API 어플리케이션을 실행할 때 톰캣과 같은 WAS(Web Application Server)가 사용
<br/><br/><br/>

## 🔶 Web 서버와 WAS
![Web 서버와 WAS](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F8iqqs%2FbtryJjFiSeI%2Feck3RcimeMDNA3K2aNJ7n0%2Fimg.webp)

WAS는 Web Server와 Web Container의 역할을 모두 할 수 있는데 WAS의 웹서버 또한 정적인 컨텐츠를 처리하는데는 성능상 큰 차이가 없다!

그렇다면 WAS가 웹 서버의  기능까지 모두 수행하면 될까?

→ 다음과 같은 이유로 웹서버와 WAS를 분리하는 것이 좋다!

1. 서버 부하 방지: WAS는 DB 조회나 다양한 로직을 처리하고, 단순한 정적 컨텐츠는 웹 서버에서 처리해 주어야 한다. 정적 컨텐츠까지 WAS가 처리한다면 부하가 커지게 되고, 수행 속도가 느려지기 때문
2. 보안 강화: SSL에 대한 암호화, 복호화 처리에 웹서버를 사용 가능
3. 여러대의 WAS 연결 가능: 로드 밸런싱을 위해 웹 서버를 사용할 수 있다. 여러 개의 서버를 사용하는 대용량 웹 어플리케이션의 경우 웹 서버와 WAS를 분리하여 무중단 운영을 위한 장애 극복에 쉽게 대응 가능
4. 여러 웹 어플리케이션 서비스 가능: 하나의 서버에서 php, JAVA 애플리케이션을 함께 사용할 수 있다.
<br/><br/><br/>
## 🔶 Web Service **Architecture**

웹서비스는 아래와 같이 다양한 구조를 가질 수 있다. 

1. Client → Web Server → DB
2. Client → WAS → DB
<br/><br/>
3. Client →  Web Server → WAS  → DB
![Client →  Web Server → WAS  → DB구조](https://blog.kakaocdn.net/dn/COYM9/btryI3bxOeM/7kDfuTH2HxaQGAHjeFquS1/img.webp)
<br/>
→ 3번 구조: 클라이언트가 웹 서버에서 HTTP요청을 보내면 웹 서버는 정적인 컨텐츠 요청은 바로 응답하고, 동적인 콘텐츠 요청은 WAS에게 넘겨서 처리하고 결과를 WAS에게 받아 다시 클라이언트에게 넘겨주는 구조 