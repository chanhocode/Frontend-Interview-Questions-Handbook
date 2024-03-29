# 네트워크 정리

- [HTTP 프로토콜이란?](#http-프로토콜이란)
- [SSH (Secure Shell Protocol)](#ssh-secure-shell-protocol)
- [SMTP (Simple Mail Transfer Protocol)](#smtp-simple-mail-transfer-protocol)
- [www.google.com을 검색할 때](#wwwgooglecom을-검색할-때)
- [TCP/IP 5계층 & OSI 7계층](#tcpip-5계층--osi-7계층)
- [TCP & UDP](#tcp--udp)
- [로컬 스토리지 & 세션 스토리지 & 쿠키 비교](#로컬-스토리지--세션-스토리지--쿠키-비교)
- [JWT](#jwt)
- [IPv4 & IPv6](#ipv4--ipv6)
- [대칭키 & 비대칭키 암호화 방식](#대칭키--비대칭키-암호화-방식)

---

## HTTP 프로토콜이란?

> HTTP(Hypertext Transfer Protocol)은 처음에는 `서버와 브라우저간에 데이터를 주고 받기 위해서 설계된 프로토콜`이지만 지금은 서버와 서버간의 통시에도 많이 사용된다.

\*\* 프로토콜이란? 송수신 메시지의 형식, 순서와 메시지 송수신시 동작을 정의한다.

- HTTP는 헤더를 통한 확장이 쉽다.
- HTTP는 stateless 하다. : 동일한 연결에서 연속적으로 수행되는 두 요청 사이에 연속적인 상태값은 없다.

### HTTP와 HTTPS의 차이점

> HTTPS는 암호화를 통해 `보안성`을 강화한 반면, HTTP는 비암호화 통신으로 보안 취약점이 있습니다. HTTPS는 암호화와 해독 과정으로 인해 HTTP보다 약간 느릴 수 있습니다. 그러나 최신 기술의 발전으로 이 차이는 점점 줄어들고 있다.

- SSL(Secure Socket Layer) : 인터넷을 통해 전달되는 정보를 보호하기 위해 개발한 통신 규약
- HTTP: 80번 포트
- HTTPS: 443번 포트

### HTTP 상태코드

- 1xx(정보)
  > 서버가 요청을 잘 받았으며 해당 프로세스를 계속 이어가며 처리하는 것을 의미한다.
- 2xx(성공)
  > 서버가 요청을 잘 받았고 이를 기반으로 클라이언트에게 성공적으로 데이터를 보낸 것을 의미한다.
- 3xx(리다이렌션)
  > 서버가 클라이언트의 요청에 대해 완료를 위해 추가 작업 조치가 필요하다.
- 4xx(클라이언트 오류)
  > 클라이언트가 요청에 페이지를 제공할 수 없거나 클라이언트의 요청이 잘못되어 요청을 처리할 수 없음을 의미한다.
- 5xx(서버 오류)
  > 서버가 클라이언트의 요청을 처리하지 못하는 상태이다.

### GET과 POST의 차이점

> `GET` 은 URL을 기반으로 데이터를 요구하며 URL을 기반으로 요청을하기 때문에 2000자 미만이라는 `길이 제한`을 가지고 있다. 또한 `캐싱이 가능`하여 사용자 이름, 비밀번호 등 민감한 정보를 전달할 때 사용하지 않는다. `POST`는 URL이 아닌 HTTP message body를 통해 데이터를 전달하므로 `길이 제한이 없다`. `캐싱이 불가`하여 사용자 이름, 비밀번호 등 민감한 정보를 전달할 때 사용한다.

### PUT과 PATCH의 차이

> PUT은 업데이트 하고자하는 데이터의 전체를 전달하고 PATCH는 업데이트 하고자 하는 데이터의 일부를 전달한다.

---

## SSH (Secure Shell Protocol)

> 보안되지 않은 네트워크에서 네트워크 서비스를 안전하게 운영하기 위한 암호화 네트워크 프로토콜이다.

---

## SMTP (Simple Mail Transfer Protocol)

> 인터넷을 통해 메일을 보낼 때 사용되는 프로토콜이다.

---

## www.google.com을 검색할 때

> `리다이렌트->캐싱->DNS->IP라우팅 & ARP->TCP연결 구축을 거쳐 요청, 응답이 일어나는 TTFB(Time to First Byte)가 시작되고 이 후 컨텐츠를 다운받게 되고 이 후 브라우저 렌더링과정을 거쳐 화면에 출력한다.`

1. 사용자가 브라우저에 URL을 입력
2. DNS서버에 도메인 네임으로 서버의 IP주소를 찾는다.
3. IP주소로 웹서버에 TCP 연결을 한다.
4. 클라이언트는 웹 서버로 HTTP 요청 메시지를 보낸다.
5. 웹 서버는 HTTP 응답 메시지를 보낸다.
6. 도착한 HTTP응답 메시지는 웹 페이지 데이터로 변환되고, 웹 브라우저에의해 출력된다.

---

## TCP/IP 5계층 & OSI 7계층

### Internet Protocol Stack

- 애플리케이션(응용) 계층
  - 네트워크 애플리케이션을 지원
  - HTTP, SMTP, IMAP
- 트랜스포트( 전송 ) 계층
  - 프로세스 간 데이터 전송
  - TCP, UDP
- 네트워크 계층
  - 발신지에서 수신지까지 데이터 그램을 라우팅
  - IP, 라우팅 프로토콜
- 링크 계층
  - 경로 상의 인접한 노드 간 데이터 전송
  - Ethernet, WIFI
- 물리 계층
  - 물리 매체를 통해 비트를 전송

### OSI 7계층

- 애플리케이션 ( 응용 ) 계층
  > 사용자에게 통신을 위한 서비스 제공, 인터페이스 역할
- 표현 계층
  > 데이터의 형식을 정의하는 계층
- 세션 계층
  > 컴퓨터끼리 통신을 하기 위해 세션을 만드는 계층
- 트랜스포트 ( 전송 ) 계층
  > 최종 수신 프로세스로 데이터의 전송을 담당하는 계층
- 네트워크 계층
  > 패킷을 목적지까지 가장 빠른 길로 전송하기 위한 계층
- 데이터링크 계층
  > 데이터의 물리적인 전송과 에러 검출, 흐름 제어를 담당하는 계층
- 물리 계층
  > 데이터를 전기 신호로 바꾸어주는 계층

---

## TCP & UDP

> `TCP`는 `높은 신뢰성`을 보장하지만 `속도가 비교적 느리다`는 단점을 가지고 있으며 `UDP`는 `신뢰성이 떨어지지만` `속도가 빠르다`는 장점을 가지고 있다.

| 프로토콜          | TCP                  | UDP                    |
| ----------------- | -------------------- | ---------------------- |
| 패킷교환방식      | 가상회선패킷교환방식 | 데이터그램패킷교환방식 |
| 신뢰성            | O                    | X                      |
| 오류검사          | 재전송, 체크섬       | 체크섬                 |
| 패킷의 순서보장   | O                    | X                      |
| 헤더 길이         | 20~60바이트 가변     | 8바이트 고정           |
| 연결 보장         | O                    | X                      |
| 브로드 캐스트지원 | X                    | O                      |
| 속도              | 느림                 | 빠름                   |

### TCP의 3-way handshake

> TCP 네트워크에서 통신하는 장치가 연결이 되어있는지 확인하는 방법

1. SYN 단계: 클라이언트는 서버에 클라이언트 ISN을 담아 SYN을 보낸다.
2. SYN + ACK 단계: 서버는 클라이언트의 SYN을 수신하고 서버의 ISN을 보내며 승인번호로 클라이언트의 ISN + 1을 보낸다.
3. ACK 단계: 클라이언트는 서버의 ISN + 1한 값인 승인번호를 담아 ACK를 서버에 보낸다.

### TCP의 4-way handshake

> TCP 네트워크에서 통신하는 장치의 연결을 해제하는 방법

1. 클라이언트가 연결을 닫으려면 FIN으로 설정된 세그먼트를 전송한다. 그리고 해당 클라이언트는 FIN_WAIT_1 상태로 들어가고 서버의 응답을 기다린다.
2. 서버는 클라이언트로 ACK라는 승인 세그먼트를 보내고 CLOSE_WAIT 상태에 들어간다. 클라이언트가 세그먼트를 받으면 FIN_WAIT_2 상태에 들어간다.
3. 서버는 LAST_ACK상태가 되며 일정 시간 이후에 클라이언트에 FIN이라는 세그먼트를 보낸다.
4. 클라이언트는 TIME_WAIT 상태가 되고 다시 서버로 ACK를 보내서 CLOSED상태가 되며 이후 클라이언트는 어느정도 시간을 대기(2\*MSL(최대 패킷 수명))한 후 연결이 닫힌다.

---

## 로컬 스토리지 & 세션 스토리지 & 쿠키 비교

- 공통점
  1.  브라우저에 캐싱을 하여 서버에 대한 요청을 줄이고 서버부하를 방지 할 수 있다.
  2.  캐싱으로 인해 다운로드 하는 컨텐츠를 줄여 웹사이트의 컨텐츠의 빠른 다운로드가 가능하다.
  3.  사이트 기본설정을 저장하거나 로그인 상태를 유지할 때 사용될 수 있다.
- 차이점

|                                  | 쿠키            | 로컬 스토리지 | 세션 스토리지  |
| -------------------------------- | --------------- | ------------- | -------------- |
| 최대 저장용량                    | 4KB             | 5MB           | 5MB            |
| 접근 범위                        | 창              | 창            | 탭             |
| 만료 기한                        | 수동 설정       | 영구적        | 탭 닫으면 종료 |
| 설정할 수 있는 주체              | 클라이언트+서버 | 클라이언트    | 클라이언트     |
| 요청과 함께 서버에 자동전송 유무 | O               | X             | X              |

### 쿠키(Cookie)와 세션(Session)의 차이점

> 쿠키는 사용자의 컴퓨터에 저장하는 작은 기록 정보 파일이며, HTTP에서 클라이언트의 상태정보를 PC에 저장했다가 필요시 정보를 참조하거나 재사용할 수 있다. 세션은 일정시간 동안 같은 사용자로부터 들어오는 일련의 요구를 하나의 상태로 보고, 그 상태를 유지시키는 기술이다.

---

## JWT

> JWT(JSON Web Token)은 헤더, 페이로드, 서명으로 이루어져 있으며 JSON 객체로 인코딩되며 메시지 인증 및 암호화에 사용한다.

- 장점
  1.  사용자 인증에 필요한 모든 정보는 토큰 자체에 포함하기 때문에 별도의 인증 저장소가 필요없다.
  2.  다른 유형의 토큰과 비교했을 때 경량화 되어 있다.
  3.  디코딩했을때 JSON이 나오기 때문에 JSON을 기반으로 쉽게 직렬화, 역직렬화가 가능하다.
- 단점
  1.  토큰이 비대해질 경우 서버 과부하에 영향을 줄 수 있다.
  2.  토큰을 탈취당할 경우 디코딩했을 때 데이터를 볼 수 있다.

---

## IPv4 & IPv6

- IPv4: 32비트로 표현되는 주소체계로 2^32개의 주소(약 42억)를 표현할 수 있다. 8비트 단위로 점을 찍어 4개로 구분해서 표현하며 보통 8비트를 10진수로 표현해서 말한다.
- IPv6: 128비트로 표현되는 주소체계이며 2^128개의 주소를 표현한다.

### IPv6 달라진 점

- IPSes이 내장되었다.
- 헤더포맷이 단순하므로 보다 빠른 처리가 가능하다.
- IPv4는 체크섬이 있지만 IPv6는 체크섬이 없다.

> IPv6는 IPv4 보다 많은 주소를 표현할수 있으며, 불필요한 헤더가 제거되어 빠르고 기본적으로 IPSec(네트워크 보안 제품군)이 포함되어 보안 측면에서 더 좋다.

---

## 대칭키 & 비대칭키 암호화 방식

> 대칭키와 비대칭키는 `양방향 암호화 방식`이다.

- 대칭키: 암호화와 복호화에 같은 암호 키를 쓰는 알고리즘
  > 이는 중간에 누군가 암호 키를 가로채면 암호화된 정보가 유출될 수 있다는 단점이 있다.
- 비대칭키: 암호화와 복호화할때 서로 다른 키를 사용하는 암호화 알고리즘
  > 타인에게 노출되어서는 안되는 개인키와 공개적으로 개방되어 있는 공개키를 쌍으로 이룬 형태

---

[맨 위로](#네트워크-정리)

|

[처음으로](../README.md)
