# 네트워크의 기초

## 네트워크의 기초

- 네트워크(Network): 노드(Node) 와 링크(Link)가 서로 연결되어 있으며 리소스를 공유하는 집합
- 링크(Link): 유선 / 무선
- 좋은 네트워크는 많은 처리량 처리 가능, 지연 시간 짧음, 장애 빈도 적음, 좋은 보안 갖춤

### 처리량(Throughput)- 노드(Node): 서버, 라우터, 스위치 등의 네트워크 장치

처리량이란 링크 내에서 성공적으로 전달된 데이터의 양으로 보통 얼만큼의 트래픽을 처리했는지 타냄<br/>

- 트래픽: 특정 시점에 링크 내에 흐르는 데이터의 양
- 단위: bps(bits per second)
- 트래픽, 네트워크 장치 간 대역폭, 네트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받음

### 지연 시간(Latency)

지연 시간이란 요청이 처리됟는 시간으로, 어떤 메시지가 두 장치 사이를 왕복하는데 걸린 시간을 의미함

- 매체 타입(유/무선), 패킷 크기, 라우터의 패킷 처리 시간에 영향을 받음

<br/><br/>

## 네트워크 토폴로지와 병목 현상

네트워크 토폴로지란 노드와 링크가 어떻게 배치되어 있는지에 대한 방식이자 연결 형태를 의미함

- 어떤 토폴로지를 갖는지, 어떤 경로로 이루어져 있는지 알아야 병목 현상을 올바르게 해결할 수 있음

### 트리 토폴로지

트리 형태로 배치된 계층형 토폴로지

- 노드의 추가, 삭제가 쉽움
- 트래픽 집중 시 하위 노드에 영향을 끼칠 수 있음

### 버스 토폴로지

중앙 통신 회선 하나에 여러개의 노드가 연결되어 공유하는 구성

- 근거리 통신망(LAN)에서 사용
- 장점: 설치 비용이 적음, 신뢰성 우수함, 중앙 통신 회선에 노드 추가, 삭제 쉬움
- 단점: 스푸핑 가능
  - 스푸핑이란 LAN 상에서 송신부의 패킷을 관련 없는 호스트에 가도록 처리하는 것을 의미함

### 스타 토폴로지

중앙에 있는 노드에 모두 연결된 네트워크 구성

- 장점: 노드 추가 쉬움, 에러 탐지 쉬움, 패킷 충돌 발생 가능성 적음, 노드에 장애가 발생해도 쉽게 에러 파악 가능, 중앙 노드만 아니면 다른 노드에 영향을 끼치는 것이 적음
- 단점: 중앙 노드에 장애가 발생하면 전체 네트워크 사용 불가능, 설치 비용이 고가

### 링형 토폴로지

각각의 노드가 양 옆의 두 노드와 연결해 전체적으로 고리처럼 하나의 연속된 길을 통해 통싱하는 구성.

- 장점: 노드 수가 증가되어도 네트워크 상의 손실이 거의 없음, 충돌 발생 가능성 적음, 노드 고장 쉽게 발견 가능
- 단점: 네트워크 구성 변경 어려움, 회선에 장애가 발생할 경우 전체 네트워크에 영향을 줌

### 메시 토폴로지(망형 토폴로지)

그물망처럼 연결되어 있는 구조

- 장점: 한 단말 장치에 장애가 발생해도 네트워크 계속 사용 가능, 트래픽 분산 처리 가능
- 단점: 노드 추가 어려움, 구축 비용 & 운용 비용 고가

<br/><br/>

## 네트워크 분류

규모를 기반으로 LAN(Local Area Network), MAN(Metropolitan Area Network), WAN(World Area Network)로 분류

### LAN(Local Area Network)

- 근거리 통신망. 같은 건물, 캠퍼스 같은 좁은 공간에서 운영
- 전송속도 빠름, 혼잡하지 않음

### MAN(Metropolitan Area Network)

- 대도시 지역 네트워크. 도시 같은 지역에서 운영
- 전송속도 평균, LAN 보다 혼잡

### WAN(World Area Network)

- 광역 네트워크. 국가 또는 대륙 같은 지역에서 운영
- 전송 속도 낮음, MAN 보다 혼잡

<br/><br/>

## 네트워크 성능 분석 명령어

- 네트워크 대역폭, 네트워크 토폴로지, 서버 CPU, 메모리 사용량, 비효율적인 네트워크 구성으로 인해 네트워크 병목현상 나타날 수 있음
- 네트워크 관련 테스트 와 네트워크 무관 테스트를 실행해, 네트워크 관련 문제점인 게 확인되면 성능 분석 시작
- ftp 를 통해 대형 파일을 전송하여 테스팅하거나 tcpdump 를 통해 노드로 오고가는 패킷을 캡쳐하는 명령어도 있음
- wireshark, netmon 등의 네트워크 분석 프로그램이 있음

### ping

네트워크 상태를 확인하려는 대상 노드를 향해 일정 크기의 패킷을 전송하는 명령어<br/>

- 해당 노드의 패킷 수신 상태, 도달하기까지의 시간 등을 알 수 있음 -> 해당 노드까지 네트워크가 잘 연결됐는지 확인 가능
- TCP/IP 프로토콜 중 ICMP 프로토콜을 통해 동작 -> ICMP 프로토콜 미지원 혹은 ICMP나 traceroute 를 차단하는 경우엔 테스트 불가
- `ping [IP 주소 또는 도메인 주소]` 로 실행

### netstat

접속되어 있는 서비스들의 네트워크 상태를 표시하는데 사용

- 네트워크 접속, 라우팅 테이블, 네트워크 프로토콜 등 리스트 보여줌 -> 서비스의 포트가 열려 있는지 확인할 때 씀

### nslookup

DNS 에 관련된 내용을 확인하는데 사용. 특정 도메인에 매핑된 IP를 확인하기 위해 사용

### tracert(리눅스: traceroute)

목적지 노드까지 네트워크 경로를 확인할 때 사용하는 명령어 -> 목적지 노드까지의 구간들 중 어느 구간에서 응답 시간이 느려지는지 등 확인할 수 있음

<br/><br/>

## 네트워크 프로토콜 표준화

네트워크 프로토콜이란 다른 장치들끼리 데이터를 주고받기 위해 설정된 공통된 인터페이스를 의미함

- IEEE 또는 IETF 라는 표준화 단체가 정함
- ex. IEEE802.3 은 유선 LAN을 구축할 때 쓰는 프로토콜로 이를 통해 만든 기업이 다른 장치라도 서로 데이터를 수신할 수 있음
- ex. HTTP 프로토콜 노드들이 웹서비스를 기반으로 데이터 주고 받을 수 있음

<br/><br/><br/><br/>

# TCP/IP 4계층 모델

인터넷 프로토콜 스위트(Internet Protocol Suite)는 인터넷에서 컴퓨터들이 서로 정보를 주고받는 데 쓰이는 프로토콜의 집합으로, 이를 설명할 때 TCP/IP 4계층 또는 OSI 7계층 모델로 설명하기도 함

<br/><br/>

## 계층 구조

<table>
  <thead>
    <tr>
      <th>TCP/IP</th>
      <th>OSI 7계층</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="3">애플리케이션 계층</td>
      <td>애플리케이션 계층</td>
    </tr>
    <tr>
        <td>프레젠테이션 계층</td>
    </tr>
    <tr>
        <td>세션 계층</td>
    </tr>
    <tr>
      <td>전송 계층</td>
      <td>전송 계층</td>
    </tr>
    <tr>
      <td>인터넷 계층</td>
      <td>네트워크 계층</td>
    </tr>
    <tr>
      <td rowspan="2">링크계층</td>
      <td>데이터 링크 계층</td>
    </tr>
    <tr>
      <td>물리 계층</td>
    </tr>
  </tbody>
</table>

특정 계층이 변경되었을 때 다른 계층이 영향 받지 않도록 설계

### 애플리케이션 계층

애플리케이션 계층은 FTP, HTTP, SSH, SMTP, DNS 등 응용 프로그램이 사용되는 프로토콜 계층으로 서비스를 실질적으로 사람들에게 제공함

- FTP(File Transfer Protocol): 장치 간 파일을 전송하는 데 사용하는 통신 프로토콜
- SSH(Secure SHell): 보안되지 않은 네트워크에서 네트워크 서비스를 안전하게 우녕하기 위한 암호화 네트워크 프로토콜
- HTTP(Hypertext Transfer Protocol): World Wide Web을 위한 데이터 통신의 기초이자 웹 사이트를 이용하는 데 쓰는 프로토콜
- SMTP(Simple Mail Transfer Protocol): 전자 메일 전소응ㄹ 위한 인터넷 표준 통신 프로토콜
- DNS: 도메인 이름과 IP 주소를 매핑하여 주는 서버.<br/>
  (ex. www.naver.com 에 DNS 쿼리가 오면 [Root DNS] -> [.com DNS] -> [.naver DNS] -> [.ww DNS] 과정을 거쳐 완벽한 주소를 찾아 매핑함)

### 전송 계층

송신자와 수신자를 연결하는 통신 서비스를 제공하며 연결 지향 데이터 스트림 지원, 신뢰성, 흐름 제어를 제공함<br/>
애플리케이션과 인터넷 계층 사이에서 데이터가 전달될 때 중계 역할

| 설명           | TCP                     | UDP                       |
| -------------- | ----------------------- | ------------------------- |
| 패킷 순서 보장 | O                       | X                         |
| 패킷 교환 방식 | 가상회선 패킷 교환 방식 | 데이터그램 패킷 교환 방식 |
| 수신 여부 확인 | O                       | X                         |
| 프로토콜       | 연결지향형 프로토콜     | 비 연결지향형 프로토콜    |

- 가상회선 패킷 교환 방식: 각 패킷에는 가상회선 식별자가 포함되고, 모든 패킷 전송 시 가상회선이 해제되고 패킷이 전송된 **순서대로** 도착하는 방식
- 데이터그램 패킷 교환 방식: 패킷이 독립적으로 최적의 경로를 선택하여 이동, 하나의 메시지에서 분할된 여러 패킷이 서로 다른 경로로 전송될 수 있고 도착 순서가 **다를 수** 있음

#### TCP 연결 성립 과정

신뢰성 확보를 위해 **3-way handshake** 라는 작업 진행

1. SYN 단계(클라이언트->서버): 클라이언트 ISN(TCP 연결의 첫번째 패킷에 할당된 임의의 시퀀스 번호, 장치마다 다를 수 있음)을 담아 SYN 을 보냄.
2. SYN + ACK 단계(서버-> 클라이언트): SYN 수신 후 서버의 ISN을 보내며, 승인 번호로 (클라이언트 ISN + 1) 값 전송
3. ACK 단계(클라이언트->서버): 승인번호로 (서버 ISN + 1) 값을 전송

#### TCP 연결 해제 과정

4-way-handshake 과정이 발생

1. 클라이언트->서버: FIN 세그먼트 전송. 클라이언트는 `FIN_WAIT_1` 상태로 들어가 서버 응답 대기
2. 서버->클라이언트: ACK 승인 세그먼트 전송. 서버는 `CLOSE_WAIT` 상태로 들어가고 클라이언트는 세그먼트를 받아 `FIN_WAIT_2` 상태에 들어감
3. 서버->클라이언트: 서버는 ACK를 보낸 뒤 일정 시간이 지나면 FIN 세그먼트 전송
4. 클라이언트->서버: 클라이언트는 `TIME_WAIT` 상태가 되고 다시 서버로 ACK 전송. 서버는 ACK 를 받으면 `CLOSED` 상태가 되고 클라이언트는 일정 시간 대기 후 연결이 닫히며 둘 사이 모든 자원 연결이 해제됨

TIME_WAIT 을 통해 지연 패킷으로 인한 데이터 무결성 문제가 발생하는 경우를 대비하고, 두 장치 연결이 닫혔는지를 확인함

### 인터넷 계층

인터넷 계층은 장치로부터 받은 네트워크 패킷을 IP 주소로 지정된 목적지까지 전송하기 위해 사용하는 계층을 말함

- 패킷을 수신해야할 상대의 주소를 지정해 데이터 전달
- 상댇방의 수신 여부를 보장하지 않음(비연결형적 특징)
- ex. IP, ARP, ICMP

### 링크 계층

링크 계층은 전선, 광섬유, 무선 등으로 실직적으로 데이터를 전달하며 장치 간의 신호를 주고 받는 **규칙** 을 정하는 계층

- 물리 계층과 데이터 링크 계층으로 나누기도 함.
  - 물리 계층: 무선 LAN 과 유선 LAN 을 통해 0과 1로 이루어진 데이터를 보내는 계층
  - 데이터 링크 계층: 이더넷 프레임을 통해 에러 확인, 흐름 제어, 접근 제어를 담당하는 계층

#### 유선 LAN(IEEE802.3)

유선 LAN 을 이루는 이더넷은 IEEE802.3 프로토콜을 따르고 전이중화 통신을 사용

- 전이중화(Full duplex) 통신

  - 송신로와 수신로로 나눠서 데이터를 주고받아 양쪽 장치가 동시에 송수신할 수 있는 방식
  - 현대의 고속 이더넷이 이 방식을 기반으로 통신

- CSMA/CD(Carrier Sense Multiple Acceess with Collision Detection)

  - 반이중화 통신 중 하나로, 한 경로로 데이터를 송수신 함
  - 데이터를 보낸 이후 충돌 발생 시, 일정 시간 후 재전송하는 방식

- 유선 LAN 케이블 종류<br/>
  TP 케이블이라고 하는 케이블이 대표적임
  - 트위스트 페어 케이블: 하나의 케이블처럼 보이지만, 여덟개의 구리선을 두개씩 꼬아 묶은 케이블로 구리선을 실드처리 하지 않고 덮은 UTP 케이블과 실드 처리하고 덮은 STP로 분리됨.
  - 광섬유 케이블: 광섬유로 만든 케이블로 레이저로 통신해 장거리 및 고속 통신이 가능함. 밀도 차를 만들어 빛의 굴절률 차로 인해 빛이 계속해서 반사되는 원리를 이용해 제작 됐음

### 무선 LAN(IEEE802.11)

수신과 송신에 같은 채널을 사용하기 때문에 반이중화 통신을 사용

- 반이중화(Half duplex) 통신

  - 양쪽 장치는 서로 통신할 수 있지만 한 번에 한 방향만 통신할 수 있음
  - 둘 이상의 장치가 동시 전송 시, 충돌이 발생하므로 충돌 방지 시스템이 필요

- CSMA/CA

  - 반이중화 통신 중 하나로, 데이터를 보내기 전에 가능한 충돌을 방지할 수 있도록 사전 작업을 하는 방식
  - 과정
    1. 데이터 송신 전, 무선 매체 살핌
    2. 캐리어 감지: 회선이 비었는지 판단
    3. IFS(Inter FrameSpace): 랜덤값을 기반으로 정해진 시간만큼 대기. 무선 매체가 사용중이면 그 간격을 점차 늘리면서 기다림
    4. 이후 데이터 송신

- 주파수<br/>
  비유도 매체인 공기에 주파수를 쏘아 무선 통신망을 구축하는데, 대역은 2.4GHz, 5GHz 중 하나를 사용함. 2.4GHz 는 장애물에 강하지만 전파 간섭이 일어나는 경우가 많고, 5GHz 는 채널 수도 많고 동시 사용이 가능해서 보다 깨끗한 전파 환경을 구축할 수 있음

- 와이파이<br/>

  - 전자기기들이 무선 LAN 신호에 연결할 수 있게 하는 기술
  - 무선 접속 장치(AP, Access Point)가 필요하고 이를 주로 공유기라고 함.
  - 유선 LAN 신호를 무선 LAN 신호로 바꿔 신호가 닿는 범위 내에서 무선 인터넷 사용이 가능함
  - 와이파이 외에도 지그비, 블루투스 등이 무선 LAN을 이용한 기술

- BSS(Basic Service Set)

  - 단순히 공유기를 통해 네트워크에 접속하는 것이 아니라 동일 BSS 내에 있는 AP 장치들이 서로 통신 가능한 구조를 말함
  - 근거리 무선 통신 제공
  - 하나의 AP만을 기반으로 구축이 되어 있어 사용자가 자유롭게 이동하며 네트워크에 접속하는 것은 불가능함

- ESS(Extended Service Set)

  - 하나 이상의 연결된 BSS 그룹
  - 장거리 무선 통신 제공
  - BSS 보다 더 많은 가용성과 이동성 지원 -> 이동하면서 연결 가능

- 이더넷 프레임<br/>
  데이터 링크 계층은 이더넷 프레임을 통해 전달 받은 데이터의 에러를 검출하고 캡슐화함

  <img src="https://blog.kakaocdn.net/dn/c9n9cv/btrF9GNov8z/h3bO3dyPDOGcknoDLseFL0/img.png"/>

  - Preamble(7바이트): 이더넷 프레임이 시작임을 알림
  - SFD(1바이트): Start Frame Delimiter의 약자. 다음 바이트부터 MAC 주소 필드가 시작됨을 알림
  - DMAC(6바이트), SMAC(6바이트): 수신, 송신 MAC 주소
  - EtherType(Length, 2바이트): 데이터 계층 위의 계층인 IP 프로토콜 정의. (ex.IPv4, IPv6)
  - Payload: 전달 받은 데이터
  - CRC(4바이트): 에러 확인 비트. FCS는 이더넷 프레임에서만 사용하는 용어이고 CRC 는 네트워킹 외에 여러 기술에서도 사용하는 용어

### 계층 간 데이터 송수신 과정

(송신 장치) 애플리케이션 계층 -> 링크 계층 -> (수신 장치) 링크 계층 -> 애플리케이션 계층. 송신부의 요청 값들이 캡슐화 과정을 거쳐 전달되고, 수신부에서 전달된 값을 비캡슐화함

#### 캡슐화 과정

상위 계층의 헤더와 데이터를 하위 계층의 데이터 부분에 포함시키고 해당 계층의 헤더를 삽입하는 과정

- 세그먼트/데이터그램화(애플리케이션 계층 -> 전송 계층): TCP(L4) 헤더 + 데이터
- 패킷화(전송 계층 -> 인터넷 계층): IP(L3) 헤더 + TCP(L4) 헤더 + 데이터
- 프레임화(인터넷 계층 -> 링크 계층): 프레임 헤더 + IP(L3) 헤더 + TCP(L4) 헤더 + 데이터 + 프레임 트레일러

#### 비캡슐화 과정

하위 계층에서 상위 계층으로 가며 각 계층의 헤더 부분을 제거하는 과정(캡슐화 역순)으로 최종적으로 사용자에게 애플리케이션의 PDU(Protocol Data Unit)인 메시지로 전달됨

<br/><br/>

## PDU(Protocol Data Unit)

네트워크 계층 사이 데이터가 전달될 때 한 덩어리의 단위를 의미함. 제어 관련 정보가 포함된 **헤더**, 데이터를 의미하는 **페이로드** 로 구성되어 있고 계층별 명칭이 다름

- 계층별 PDU 명칭
  - 애플리케이션: 메시지
  - 전송: 세그먼트(TCP), 데이터그램(UDP)
  - 인터넷: 패킷
  - 링크: 프레임(데이터 링크 계층), 비트(물리 계층)
- 모든 PDU 중 비트로 송수신 하는 것이 가장 빠르고 효율성이 높지만 애플리케이션 계층에서는 헤더의 확장을 용이하기 위해 문자열을 기반으로 송수신함

<br/><br/><br/><br/>

# 네트워크 기기

## 네트워크 기기의 처리 범위

- 계층 별로 처리 범위 분리가 가능함
- 상위 계층 처리 기기는 하위 계층을 처리할 수 있지만 반대는 불가함(애플리케이션(상) -> 물리(하))
- 계층별 처리 장치
  - 애플리케이션: L7 스위치
  - 인터넷: 라우터, L3 스위치
  - 데이터 링크: L2 스위치, 브리지
  - 물리 계층: NIC, 리피터, AP

<br/><br/>

## 애플리케이션 계층 처리 기기

### L7 스위치

여러 장비를 연결하고 데이터 통신을 중재하며 목적지가 연결되 ㄴ포트로만 전기 신호를 보내 데이터를 전송하는 통신 네트워크 장비

- 로드밸런서라고도 함. 서버 부하를 분산해 시스템이 처리할 수 있는 트래픽 증가를 목표로함
- URL, 서버, 캐시, 쿠키를 기반으로 트래픽 분산
- 바이러스, 불필요한 외부데이터 등을 걸러내는 필터링 기능 수행
- 응용 프로그램 수준의 트래픽 모니터링 가능
- 정기적 헬스 체크를 이용하여 감시하면서 장애 발생한 서버를 분산 대상에서 제외시킴

### L7 스위치 vs L4 스위치

둘다 로드 밸런서로 사용됨

| 설명                               | L7스위치                        | L4스위치                   |
| ---------------------------------- | ------------------------------- | -------------------------- |
| 계층                               | 애플리케이션 계층               | 전송 계층                  |
| 트래픽 분산 기반                   | IP, 포트, URL, 서버, 캐시, 쿠키 | IP, 포트                   |
| 로드밸런싱 컴포넌트                | ALB(Application Load Balancer)  | NLB(Network Load Balancer) |
| 스트리밍 관련 서비스에서 사용 가능 | O                               | X                          |

### 헬스 체크

전송 주기와 재전송 횟수 등을 설정해 반복적으로 서버에 요청을 보내는 것을 말하며 L7, L4 스위치 모두 헬스체크를 통해 정상적인 서버를 판별함

### 로드밸런서를 이용한 서버 이중화

- 서비스를 안정적으로 운영하기 위해서는 2대 이상의 서버는 필수(1대가 종료되어도 서비스가 안정적으로 운영)
- 로드밸런서는 2대 이상의 서버를 기반으로 가상 IP를 제공함

<br/><br/>

## 인터넷 계층 처리 기기

### 라우터(Router)

- 여러 개의 네트워크를 연결, 분할, 구분시켜주는 역할로 라우팅을 하는 장비
- 라우팅: 다른 네트워크에 존재하는 장치끼리 데이터 송수신 시 패킷 소모를 최소화하고 경로를 최적화하여 최소 경로를 찾아내는 것

### L3 스위치

- L2 스위치의 기능과 라우팅의 기능을 갖춘 장비
- L3 스위치를 라우터라고 해도 무방
- 라우터는 소프트웨어 기반의 라우팅과 하드웨어 기반의 라우팅으로 나뉘는데, L3 스위치가 하드웨어 기반의 라우팅을 담당함

<br/><br/>

## 데이터 링크 계층을 처리하는 기기

### L2 스위치

- MAC 주소를 MAC 주소 테이블을 통해 관리하고 연결된 장치로부터 패킷이 왔을 때 패킷 전송을 담당함
- IP 주소를 이해하지 못해, IP 주소 기반 라우팅은 불가능.
- 목적지가 MAC 주소 테이블에 없다면 전체 포트에 전달하고 MAC 주소 테이블의 주소는 일정시간 이후 삭제하는 기능이 있음

### 브리지

- 두 개의 LAN 을 상호작용할 수 있도록 하는 통시망 연결 장치
- 장치에서 받아온 MAC 주소를 MAC 주소 테이블로 관리
- 통신망 범위를 확장하고, 서로 다른 LAN 등으로 이루어진 **하나의** 통신망을 구축하는데 사용

<br/><br/>

## 물리 계층을 처리하는 기기

### NIC(Network Interface Card)

- LAN 카드(고유 식별 번호인 MAC 주소가 있음)
- 2대 이상의 컴퓨너 네트워크를 구성하는데 사용
- 빠른 속도로 데이터 송수신할 수 있도록 컴퓨터 내에 설치하는 확장 카드

### 리피터(Repeater)

- 약해진 신호정도를 증폭하여 다른쪽으로 전달하는 장치
- 광케이블 보급 이후 잘 안쓰임

### AP(Access Point)

- 패킷을 복사하는 기기
- AP에 유선 LAN 을 연결한 후 다른 장치에서 무선 LAN 기술을 사용해 무선 네트워크 연결을 할 수 있게 함

<br/><br/><br/><br/>

# IP주소

- 인터넷에서 사용하는 네트워크 주소이기 때문에 동 또는 구까지 위치 추적이 가능함

## ARP(Address Resolution Protocol)

IP 주소로부터 MAC 주소를 구하는 IP 와 MAC 주소의 다리역할을 하는 프로토콜

- 과정
  1. (장치A) ARP Request 브로드캐스트 보냄 -> IP 주소에 해당하는 MAC 주소 찾음
  2. (일치한 장치B) ARP Reply 유니캐스트 보냄 -> MAC 주소 반환
- RARP 를 통해 MAC -> IP 변환을 진행하기도 함

<br/><br/>

## 홉바이홉 통신

홉바이홉 통신이란 통신 장치에 있는 라우팅 테이블의 IP를 통해 시작 주소부터 시작하여 다음 IP 로 계속해서 이동하는 라우팅 과정을 거쳐 패킷이 최종 목적지까지 도착하는 통신을 의미함

### 라우팅 테이블

- 라우터에 들어있는 목적지 정보들과 그 목적지로 가기 위한 방법이 들어있는 리스트를 의미함
- 게이트웨이와 모든 목적지에 대해 해당 목적지에 도달하기 위해 거쳐야할 다음 라우터의 정보를 담고 있음

### 게이트웨이

서로 다른 통신망, 프로토콜을 사용하는 네트워크 간의 통신을 가능하게 하는 관문 역할을 하는 컴퓨터나 소프트웨어를 의미함

<br/><br/>

## IP 주소 체계

- IPv4: 32비트를 8비트 단위로 점을 찍어 표기
- IPv6: 64비트를 16비트 단위로 점을 찍어 표기
- IPv4 -> IPv6 추세지만 가장 많이 쓰이는 주소 체계는 Ipv4

### 클래스 기반 할당 방식(Classful network addressing)

A, B, C, D,E 다섯 개의 클래스로 구분하는 방식. 앞에 있는 부분을 네트워크 주소, 그 뒤에 있는 부분을 컴퓨터에 부여하는 주소인 호스트 주소로 놓아 사용함

- A: 일대일 통신용. 0.0.0.0 ~ 127.255.255.255 의 범위(구분비트: 0)
- B: 일대일 통신용 128.0.0.0 ~ 191.255.255.255 의 범위(구분비트: 10)
- C: 일대일 통신용 192.0.0.0 ~ 223.255.255.255 의 범위(구분비트: 110)
- D: 멀티캐스트 통신
- E: 앞으로 사용할 예비용
- 네트워크의 첫번째 주소는 네트워크 구별 주소, 마지막 주소는 브로트캐스트 용 주소<br/>
  (ex. 12.0.0.0 의 네트워크를 부여 받으면 12.0.0.0 은 네트워크 구별 주소, 12.255.255.255 는 브로드캐스트 주소)
- 사용하는 주소보다 버리는 주소가 더 많다는 단점 -> DHCP, IPv6, NAT 으로 극복하려고함

### DHCP(Dynamic HOst Configuration Protocol)

IP 주소 및 기타 통신 매개변수를 **자동**으로 할당하기 위한 네트워크 관리 프로토콜

- 인터넷에 접속할 때마다 자동으로 IP 주소를 할당할 수 있음
- 가정용 네트워크에서 사용

### NAT(Network Address Translation)

패킷이 라우팅 장치를 통해 전송되는 동안 패킷의 IP 주소 정보를 수정하여 IP 주소를 다른 주소로 매핑하는 방법

- IPv4로 많은 주소들을 감당하지 못한다는 단점을 NAT을 통해 공인 IP 와 사설 IP 로 나눠서 많은 주소를 처리함
- 공인 IP <-> 사설 IP 를 하는데 사용
- NAT 을 가능하게 하는 소프트웨어: ICS, RRAS, Netfilter 등
- 내부 네트워크에서 사용하는 IP 주소와 외부에 드러나는 IP 주소를 다르게 유지할 수 있어 내부 네트워크에 대한 어느 정도의 보안이 가능
- 목적: 주로 여러대의 호스트가 하나의 공인 IP 주소를 사용해 인터넷에 접속하기 위해 사용함(공유기에 NAT 탑재되어있음)
- 단점: 여러명이 동시에 접속하기 때문에 접속 속도 느려질 수 있음

<br/><br/><br/><br/>

# HTTP

애플리케이션 계층에서 웹 서비스 통신에 사용됨

## HTTP/1.0

- 한 연결당 하나의 요청을 처리하도록 설계 -> 서버로부터 파일을 가져올 때마다 TCP 3-way handshake 를 계속해서 열어야 함 -> RTT 증가를 불러옴

### RTT 증가 해결 법

1. 이미지 스플리팅: 많은 이미지가 합쳐져 있는 하나의 이미지를 다운로드 하고 이를 기반으로 background-image 의 position 을 이용하여 이미지를 표기하는 방식
2. 코드 압축: 개행 문자, 빈칸을 없애서 코드의 크기를 최소화 하는 방법
3. 이미지 Base64 인코딩: 이미지 파일을 64진법으로 이루어진 문자열로 인코딩하는 방법.

- 장점: 서버와의 연결을 열고 서버에 대한 HTTP 요청을 할 필요가 없음
- 단점: 37% 정도 크기가 더 커짐

## HTTP/1.1

HTTP/1.0 에서 발전한 형태로, 매번 TCP 연결을 하는 것이 아닌 한 번 TCP 초기화를 한 후에 keep-alive 옵션을 통해 여러개의 파일을 송수신할 수 있도록 변경한 버전<br/>

- HTTP/1.0 에도 keep-alive 는 있었지만 표준화가 되어있지 않았고 HTTP/1.1 부터 표준화가 되어 기본 옵션으로 설정됨
- 장점: 3-way handshake 발생한 후엔 발생하지 않음
- 단점
  - 문서 안에 포함된 다수의 리소스를 처리하려면, 리소스 개수에 비례해 대기 시간이 길어짐
  - HOL Blocking: 네트워크에서 같은 큐에 있는 패킷이 그 첫번째 패킷에 의해 지연될 때 발생하는 성능 저하 현상
  - 헤더에 쿠키 등과 같은 많은 메타데이터가 들어가 있고 압축이 되지 않아 무거웠음

### HTTP/2

HTTP/2 는 SPDY 프로토콜에서 파생된 HTTP/1.x보다 지연시간을 줄이고 응답시간을 더 빠르게 할 수 있으며 멀티플렉싱, 헤더 압축, 서버 푸시, 요청의 우선순위 처리를 지원하는 프로토콜을 의미함

#### 멀티플렉싱

- 여러 개의 스트림을 사용하여 송수신하는 것을 의미함 -> 특정 스트림의 패킷이 손실되어도 해당 스트림에만 영향을 미치고 나머지 스트림은 멀쩡하게 동작<br/>
- HTTP/1.1에서는 하나의 연결에 대해 여러 데이터를 순차적으로 하나씩 보내거나, 여러개의 TCP connection 을 만들어서 데이터 전송을 시도했지만, HTTP/2부터는 하나의 TCP 연결에서 병렬로 여러 요청을 받을 수 있어 HOL Blocking 문제를 해결할 수 있음

#### 헤더 압축

HTTP/2 에서는 허프만 코딩 압축 알고리즘을 사용하는 HPACK 압축 형식을 가짐

- 허프만 코딩(Huffman coding): 문자열을 문자 단위로 쪼개 빈도수를 세어, 빈도가 높은 정보는 적은 비트 수를 사용해 표현하고, 빈도가 낮은 정보는 비트 수를 많이 사용하여 표현해 전체 데이터의 표현에 필요한 비트의 양을 줄이는 방식

#### 서버 푸시

HTTP/1.1 에서는 클라이언트가 서버에 요청을 해야 파일을 다운로드 할 수 있었지만, HTTP/2는 클라이언트 요청 없이 서버가 바로 리소스를 푸시할 수 있음

### HTTPS

애플리케이션과 전송 계층 사이에 신뢰 관계인 SSL/TLS 계층을 넣은 신뢰할 수 있는 HTTP 요청을 의미함

- HTTP/2 는 HTTPS 위에서 동작함
- 직접 CA에서 구매한 인증키를 기반으로 구축하거나, HTTPS 를 제공하는 로드밸런서를 두거나, HTTPS를 제공하는 CDN을 둬서 구축함

#### SSL(Secure Socket Layer)/TLS(Transport Layer Security Protocol)

- SSL 1.0 부터 시작서 SSL 2.0 -> SSL 3.0 -> TLS 1.0 -> TLS 1.3 까지 버전이 올라가며 TLS 로 명칭이 변경됐으나 SSL/TLS 로 합쳐서 많이 부름
- 전송 계층에서 보안을 제공하는 프로토콜로 클라이언트와 서버가 통신할 때 제3자가 메시지를 도청하거나 변조하지 못하도록 함

- 보안 세션을 기반으로 데이터를 암호화하며 보안 세션이 만들어질 때 인증 메커니즘, 키 교환 암호화 알고리즘, 해싱 알고리즘이 사용됨

- 보안 세션: 보안이 시작되고 끝나는 동안 유지되는 세션.

  - SSL/TLS 는 핸드셰이크를 통해 보안 세션을 생성하고 상태 정보 등을 공유함.
  - 클라이언트와 서버와 키를 공유하고 이를 기반으로 인증, 인증 확인 등의 작업이 일어나는 1-RTT 가 생긴 후 데이터를 송수신함
  - TLS 1.3 에서는 이전에 방문한 사이트를 재방문할때 보안 세션을 만들 때 걸리는 통신을 안해도됨(0-RTT)
  - 클라이언트에서 사이퍼 슈트를 서버에 전달하면, 서버는 사이퍼 슈트의 암호화 알고리즘 리스트 제공을 할 수 있는지 확인하고, 제공할 수 있다면 서버에서 클라이언트로 인증서를 보내는 인증 메커니즘이 시작되어 이후 해싱 알고리즘 등으로 암호화된 데이터의 송수신이 시작됨

  - 사이퍼 슈트: 프로토콜, AEAD 사이퍼 모드, 해싱 알고리즘이 나열된 규약을 말하며 다섯 개가 존재함 <br/>
    ex. GCM_SHA256: TLS 프로토콜, AES_128_GCM AEAD 사이퍼 모드, SHA256 해싱 알고리즘

  - AEAD(Authential Encryption with Associated Data) 사이퍼 모드: 데이터 암호와 알고리즘
    ex. AES_128_GCM: 128비트의 키를 사용하는 표준 블록 암호화 기술과 병렬 계산에 용이한 암호화 알고리즘 GCM 이 결합된 알고리즘

- 인증 메커니즘: CA(Certificate Authorities)에서 발급한 인증서를 기반으로 이루어짐<br/>

  - 클라이언트에게 공개키를 제공하고, 사용자가 접속한 서버가 신뢰할 수 있는 서버임을 보장함
  - 인증서: 서비스 정보, 공개키, 지문, 디지털 서명 등으로 이루어짐
  - CA 발급 과정: 사이트 정보와 공개키를 CA에 제출 -> CA가 공개키를 해시한 값인 지문을 사용하는 CA의 비밀키 등을 기반으로 인증서 발급

- 암호화 알고리즘
  - 디피-헬만 키 교환 알고리즘(Diffie-Hellman key exchange): `y = g^x mod p`에서 y,g,p만 안다면 x 를 구하기 어렵다는 원리에서 기반한 암호키 교환 방식
  - 해싱 알고리즘: 데이터를 추정하기 힘든 더 작고 섞여 있는 조각으로 만드는 알고리즘. 해시 함수 결과값의 크기에 따라 결과값이 256비트인 SHA-256 가 있음

#### SEO(Search Engine Optimization)

사용자들이 검색엔진으로 웹 사이트 검색 시, 결과를 페이지 상단에 노출시켜 많은 사람들이 볼 수 있도록 최적화 하는 방법

- 구글 기준 모든 사이트 내 요소가 동일할 경우 HTTPS 서비스를 하는 사이트가 SEO 순위가 높음
- 캐노니컬 설정, 메타 설정, 페이징 속도 개선, 사이트 맵 관리 등이 있음

#### 구축 방법

### HTTP/3

- **QUIC** 이라는 계층에서 돌아감
- TCP 가 아닌 UDP 기반으로 돌아감
- 멀티플렉싱을 가지고 있음
- 초기 연결 설정 시연 시간 감소라는 장점이 있음(3-way handshake 미사용으로 인해 감소됨) -> 1-RTT 소요
- QUIC 은 순방향 오류 수정 메커니즘(FEC, Forword Error Correction)이 적용되어 전송한 패킷이 손실되었다면, 수신측에서 에러를 검출하고 수정하는 방식. 열악한 네트워크 환경에서도 낮은 패킷 손실률 자랑

<br/><br/><br/><br/>

# 용어

- 대역폭: 주어진 시간 동안 네트워크 연결을 통해 흐를 수 있는 최대 비트 수
- 스푸핑: LAN 상에서 송신부의 패킷을 관련 없는 호스트에 가도록 처리하는 것
- 병목(Bottleneck) 현상: 전체 시스템의 성능이나 용량이 하나의 구성 요소로 인해 제한 받는 현상
- SYN: SYNchronization 의 약자. 연결 요청 플래그
- ACK: ACKnowledgement 의 약자. 응답 플래그
- ISN: Initial Sequence Number 의 약자. 초기 네트워크 연결 시, 할당된 32비트 고유 시퀀스 번호
- TIME_WAIT: 소켓이 바로 소멸되지 않고 일정 시간 유지하는 상태. 지연 패킷 등의 문제점 해결을 위해 사용됨. CentOS6, 우분투는 60초로 설정되어 있고 윈도우는 4분으로 설정되어 있음
- 데이터 무결성(Data Integrity): 데이터의 정확성과 일관성을 유지하고 보증하는 것
- MAC 주소: 각 장치에 네트워크에 연결하기 위한 장치(LAN카드)가 있는데, 이를 구별하기 위한 식별 변호. 6바이트로 구성됨
- 브로드캐스트: 송신 호스트가 전송한 데이터가 네트워크에 연결된 모든 호스트에 전송되는 방식
- 유니캐스트: 고유 주소로 식별된 하나의 네트워크 목적지에 1:1로 데이터를 전송하는 방식
- 라우팅: IP 주소를 찾아가는 과정
- RTT: 패킷 왕복 시간(패킷이 목적지에 도달하고 나서 다시 출발지로 돌아오기까지 걸리는 시간)
- 인코딩: 정보의 형태나 형식을 표준화, 보안, 처리 속도 향상, 저장 공간 절약 등을 위해 다른 형태나 형식으로 변환하는 처리 방식
- 세션: 운영체제가 어떠한 사용자로부터 자신의 자산 이용을 허락하는 일정한 기간을 뜻함. 즉 사용자는 일정 시간 동안 응용 프로그램, 자원 등을 사용할 수 있음
