# TCP/IP 프로토콜 

## ARPANET, packet switching의 시작 

```ad-note
title: 미국 방성 (Department of Defense, AKA DoD)의 네트워크 프로젝트 

1969년, 미국 방성에서 다른 위치, 다른 플랫폼에있는 컴퓨터와 통신할 수 있는 네트워크를 통신 방법에 관해 연구를 시작했다. 일명 Advanced Research Projects Agency (ARPA)라는 에이전시에서 담당을 했는데, 이때 처음으로 **Packet Switching** 기술을 사용하게 되었다.

좀 재밌는 점은, 핵공격에 대비해서 만들어진 기술이라는거다. 데이터를 작은 단위로 나누어서 회선을 통해 여러 사용자에게 공유할 수 있고, 다양한 경로로 전송 될 수 있어, 핵 공격에도 네트워크가 계속 동작할 수 있다는 가정하에 만들어졌다. 

[자료 출처](https://www.sciencemuseum.org.uk/objects-and-stories/arpanet-internet)

Packet Switching 기술은 Paul Baran이라는 미국으로 이주하신 폴란드 분이 RAND라는 회사에 재직 중 처음 컨셉을 제시했다. Paul Baran님은 "메세지가 하나의 중심을 통해 연결되면, 전쟁중에는 다들 중심지를 공격하지 않겠냐, 그럴바에는 네트워크 노드를 분산시키자!" 하면서 "hot potato routing"이라고 쓰고 distributed communication (분산 통신)이라는 컨셉을 제시하셨다. 

생각해보면 예전 circuit switching (회선 방식)은 누군가 결국 회선을 연결시켜줘야했고, 그 연결해주는 부서가 당하면 통신이 끊겼으니. 옛날 전쟁 영화를 봐도 다들 통신팀만 먼저 치는거 보면, 최대 약점인걸로 보인다. 

영국에 Donald Davies라는 분이 매우 비슷한 시스템을 만들었는데, 그는 이 메세지 블록을 Packet이라고 불러 지금까지도 Packet이라고 불린다. 아니.. Paul Baran님이 먼저 만들었는데.. 속상하시겠다.. 

어쨌든, 1969년에 처음으로 이 "분산" 컨셉을 테스트 하기 위해 UCLA에 첫 노드를 설치하고 실험하면서, 여러 다른 대학들이 연결되어 과학분야 연구자들이 서로 정보 공유 할 수 있는 네트워크의 장이 생겼다. 

[자료 출처](https://www.rand.org/pubs/articles/2018/paul-baran-and-the-origins-of-the-internet.html)
```


## DoD 모델 

|      <br>DoD Protocol Model<br>      |
| :----------------------------------: |
|      <br>Application Layer<br>       |
| <br>Host-to-host transport layer<br> |
|   <br>Local Network Protocol Layer   |
```ad-note

DDN Protocol Handbook에 따르면, DoD Protocol Model은 원래 3개의 레이어를 갖고 있데. 

- Application Layer
- Host-to-host transport layer
- Network Access Layer 

[자료 출처](https://www.cisco.com/E-Learning/bulk/public/tac/cim/cib/using_cisco_ios_software/linked/tcpip.htm)

Host-to-host transport layer를 나누면 우리가 아는 
- Application Layer
- Transport Layer (TCP)
- Internet Layer (IP)
- Network Access Layer 가 나온다 

```




```ad-claude
title: TCP/IP 도 DoD 모델이라는데? 

네, TCP/IP 프로토콜도 흔히 'DoD 모델'이라고 불립니다. 이는 미국 국방부(Department of Defense)가 ARPANET(현재 인터넷의 전신)을 개발하면서 만든 모델이기 때문입니다.

TCP/IP DoD 모델은 4계층으로 구성되어 있습니다:

1. 네트워크 액세스 계층(Network Access Layer)

- 물리적 네트워크 하드웨어와 직접 상호작용
- 이더넷, Wi-Fi 등의 프로토콜 포함

2. 인터넷 계층(Internet Layer)

- IP(Internet Protocol)가 작동하는 계층
- 패킷 라우팅과 주소 지정 담당

1. 전송 계층(Transport Layer)

- TCP(Transmission Control Protocol)와 UDP가 작동
- 데이터의 신뢰성 있는 전송을 보장

2. 응용 계층(Application Layer)

- HTTP, FTP, SMTP 등 사용자 수준의 프로토콜
- 실제 응용 프로그램과 상호작용

이 모델은 OSI 7계층 모델보다 단순하지만, 실제 인터넷에서 더 널리 사용되고 있습니다.
```

## TCP/IP의 4계층

### Application 계층
- 사용자들 프로그램
- FPT< Telnet, SSH, HTTP, SMTP, SNMP 등 

### Transport 계층
- 신뢰성 있게 메세지를 전송하는 TCP 프로토콜
- 비연결형 = UDP
- TCP는 가상의 연결을 지원하고 에러처리를 실행해서 신뢰성 있게 전송한다 

### Internet 계층
![[Pasted image 20250209195956.png]]
- IP 주소를 읽어서 경로를 결정하는 routing을 한다 
- 논리적 주소인 IP 주소를 부여하고 최단 경로를 결정한다 
- IP 주소를 하드웨어 주소인 MAC 주소로 변환하는 ARP 프로토콜을 지원한다 
- 네트워크의 에러를 검사하는 ICMP 프로토콜 

### Network 계층 
- 물리적 케이블 혹은 무선 통신과 연결
- 전기적 신호 

# Internet 계층
- 경로를 정하는 계층 
- 발신지 - 목적지 경로 설정 

## 1. 논리 주소 지정 (Logical Addressing)

- 모든 장치를 구별하기 위해 IP 주소라는 고유한 논리적 주소를 할당합니다
- IPv4는 32비트, IPv6는 128비트 주소 체계를 사용합니다
- 이 주소를 통해 전 세계 어디에서든 특정 장치를 식별할 수 있습니다

### IPV4

1. 주소 구조

- 32비트 주소 체계 사용
- 8비트씩 4부분으로 구성 (예: 192.168.0.1)
- 약 43억개(2^32)의 주소 생성 가능

2. 주요 특징

- 헤더 크기: 20-60바이트 (가변적)
- Class A, B, C, D, E로 분류되는 클래스 기반 주소체계
- NAT(Network Address Translation)를 통한 주소 절약
- 체크섬 필드가 헤더에 포함되어 있음

3. 보안

- IPSec이 선택사항
- 기본적인 보안 기능 미흡

### IPV6

1. 주소 구조

- 128비트 주소 체계 사용
- 16비트씩 8부분으로 구성 (예: 2001:0db8:85a3:0000:0000:8a2e:0370:7334)
- 약 340간(2^128)의 주소 생성 가능
- 16진수로 표현

2. 주요 특징

- 헤더 크기: 40바이트 (고정)
- 클래스 없는 주소 체계
- 주소 자동 설정 기능
- 체크섬 필드 제거로 처리 속도 향상
- 플로우 레이블 필드 추가로 QoS 지원 강화

3. 보안

- IPSec이 기본으로 포함
- 향상된 보안 기능 제공

### Why IPV6?
- 주소 고갈 문제 해결
- 보안 강화
- 네트워크 구성 자동화
- 효율적인 라우팅
- QoS 지원 강화

### IPV4에서 IPV6 전환
1. 듀얼 스택 (Dual Stack)

- 정의: 하나의 장치에서 IPv4와 IPv6 프로토콜을 동시에 지원하는 방식
- 동작 방식:
    - 장치가 두 개의 스택을 모두 운영
    - IPv4 통신이 필요할 때는 IPv4 스택 사용
    - IPv6 통신이 필요할 때는 IPv6 스택 사용
- 장점:
    - 점진적인 전환이 가능
    - 기존 IPv4 서비스를 중단없이 유지
- 단점:
    - 두 프로토콜을 모두 처리해야 하므로 시스템 자원 소모가 큼
    - 두 주소 체계를 모두 관리해야 함

2. 터널링 (Tunneling)

- 정의: IPv6 패킷을 IPv4 네트워크를 통해 전송하는 방식
- 동작 방식:
    - IPv6 패킷을 IPv4 패킷으로 캡슐화
    - IPv4 네트워크를 통해 전송
    - 목적지에서 다시 IPv6 패킷으로 디캡슐화
- 주요 터널링 방식:
    - 6to4: 자동 터널링 방식
    - ISATAP: 사이트 내부 자동 터널링
    - Teredo: NAT 통과를 위한 터널링
- 장점:
    - 기존 IPv4 인프라 활용 가능
    - 독립된 IPv6 네트워크 간 연결 가능
- 단점:
    - 추가적인 오버헤드 발생
    - 관리와 설정이 복잡할 수 있음

1. 주소 변환 (Translation)

- 정의: IPv6 주소와 IPv4 주소 간의 변환을 수행하는 방식
- 주요 변환 기술:
    - NAT64: IPv6 네트워크에서 IPv4 서버 접근
    - DNS64: IPv6 주소와 IPv4 주소 간의 DNS 변환
- 동작 방식:
    - IPv6 전용 클라이언트가 IPv4 전용 서버와 통신할 때 주소 변환
    - 변환 테이블을 유지하며 패킷 헤더 변환
- 장점:
    - IPv6 전용 네트워크에서 IPv4 서비스 접근 가능
    - 기존 애플리케이션 수정 불필요
- 단점:
    - 일부 애플리케이션에서 호환성 문제 발생 가능
    - 변환 과정에서 성능 저하 가능


## 2. 주소 변환 (Address Transformation)

- MAC 주소(물리 주소)와 IP 주소(논리 주소) 간의 변환을 담당합니다
- ARP(Address Resolution Protocol)를 사용하여 IP 주소를 MAC 주소로 변환합니다
- RARP(Reverse ARP)를 사용하여 MAC 주소를 IP 주소로 변환합니다

### ARP 
1. ARP (Address Resolution Protocol)

- 목적: IP 주소를 물리적 주소(MAC)로 변환
- 동작 과정:
    - ARP Request: 브로드캐스트로 목적지 IP 주소에 대한 MAC 주소 요청
    - ARP Reply: 해당 IP 주소를 가진 호스트가 자신의 MAC 주소 응답
    - ARP Cache: 변환된 주소 정보를 임시 저장하여 재사용
- 주요 특징:
    - 브로드캐스트 기반 동작
    - ARP Cache를 통한 성능 최적화
    - Gratuitous ARP: IP 주소 중복 감지에 사용

### RARP 

- 목적: 물리적 주소(MAC)를 IP 주소로 변환
- 사용 환경:
    - 디스크가 없는 워크스테이션
    - 서버로부터 IP 주소를 할당받아야 하는 경우
- 동작 과정:
    - RARP Request: MAC 주소를 포함한 요청을 브로드캐스트
    - RARP Reply: RARP 서버가 해당 MAC 주소에 대한 IP 주소 응답
- 한계점:
    - IP 주소만 제공 가능
    - 추가 정보(서브넷 마스크, 게이트웨이 등) 제공 불가
    - 현재는 DHCP로 대체됨

### ARP의 보안 이슈

- ARP Spoofing/Poisoning:
    - 거짓 ARP Reply를 통한 MAC 주소 위조
    - 중간자 공격 가능성
- 대응 방안:
    - 정적 ARP 엔트리 사용
    - ARP 감시 도구 활용
    - VLAN 분리

### ARP Cache 관리

- 동적 엔트리:
    - 통신 과정에서 자동으로 생성
    - 일정 시간 후 자동 삭제
- 정적 엔트리:
    - 수동으로 설정
    - 시스템 재시작까지 유지
- 관리 명령어:
    - arp -a: 캐시 테이블 조회
    - arp -d: 캐시 엔트리 삭제
    - arp -s: 정적 엔트리 추가

### 현대 네트워크에서의 위치

- ARP: 여전히 IPv4 네트워크의 필수 프로토콜
- RARP: DHCP, BOOTP 등으로 대체
- IPv6에서는:
    - NDP(Neighbor Discovery Protocol) 사용
    - ICMPv6 기반 동작

## 3. 데이터그램 생성

- 상위 계층에서 받은 데이터에 IP 헤더를 추가합니다
- IP 헤더에는 출발지 IP, 목적지 IP, 프로토콜 번호 등의 정보가 포함됩니다
- 이렇게 만들어진 패킷을 데이터그램이라고 합니다

### IP Header

```ad-claude
IP 헤더 구조의 각 필드를 중요도와 관련성에 따라 정리해서 설명해드리겠습니다.

1. 기본 정보 필드

- Version (4비트)
    - IP 프로토콜의 버전 표시
    - IPv4는 4, IPv6는 6 값을 가짐
- Header Length (4비트)
    - IP 헤더의 길이를 32비트 단위로 표시
    - 최소값 5 (20바이트), 최대값 15 (60바이트)
- Total Length (16비트)
    - IP 패킷 전체 길이 (헤더 + 데이터)
    - 최대 65,535바이트까지 표현 가능

2. 서비스 관련 필드

- Type of Service/ToS (8비트)
    - 패킷의 우선순위와 서비스 특성 정의
    - 현재는 QoS(Quality of Service)를 위해 사용
    - DSCP(6비트)와 ECN(2비트)로 구분

1. 패킷 식별 및 분할 필드

- Identification (16비트)
    - 각 패킷을 구분하는 고유 번호
    - 분할된 패킷들은 같은 ID 값을 가짐
- Flags (3비트)
    - 패킷의 분할 여부를 제어
    - Bit 0: 예약됨 (항상 0)
    - Bit 1: DF (Don't Fragment)
    - Bit 2: MF (More Fragments)
- Fragment Offset (13비트)
    - 분할된 조각의 원래 위치를 8바이트 단위로 표시
    - 최대 값: 8,191 (13비트)

2. 제어 및 신뢰성 필드

- TTL (Time To Live, 8비트)
    - 패킷의 생존 시간을 홉(hop) 단위로 표시
    - 라우터를 지날 때마다 1씩 감소
    - 0이 되면 패킷 폐기
- Protocol (8비트)
    - 상위 계층 프로토콜 식별
    - 예: TCP(6), UDP(17), ICMP(1)
- Header Checksum (16비트)
    - 헤더의 오류 검출을 위한 검사합
    - 라우터마다 재계산 (TTL 변경 때문)

3. 주소 필드

- Source IP Address (32비트)
    - 출발지 IP 주소
- Destination IP Address (32비트)
    - 목적지 IP 주소

이러한 필드들이 모여 IPv4 헤더의 기본 구조를 이루며, 각각의 필드는 패킷의 전송, 분할, 재조립, 오류 검출 등 다양한 네트워크 기능을 지원합니다.
```

### IP Fragmentation

```ad-claude

IP Fragmentation, MTU, ifconfig에 대해 순차적으로 설명해드리겠습니다.

1. IP Fragmentation (IP 단편화)

- 정의: 큰 IP 패킷을 작은 단위로 나누는 과정
- 발생 원인:
    - 패킷 크기가 네트워크의 MTU보다 클 때
    - 서로 다른 네트워크 환경을 통과할 때
- 동작 방식:
    - 원본 패킷을 여러 조각으로 분할
    - 각 조각에 fragmentaion offset 지정
    - 목적지에서 재조립
- 식별 방법:
    - Identification 필드로 같은 패킷의 조각들 구분
    - Fragment Offset으로 순서 확인
    - More Fragment(MF) 플래그로 마지막 조각 확인

2. MTU (Maximum Transmission Unit)

- 정의: 네트워크에서 전송할 수 있는 최대 패킷 크기
- 일반적인 MTU 크기:
    - 이더넷: 1500 바이트
    - PPP: 576 바이트
    - IPv6: 1280 바이트 이상
- MTU 관련 기능:
    - Path MTU Discovery: 경로상의 최소 MTU 탐색
    - Jumbo Frame: 9000바이트 이상의 큰 MTU 지원
- MTU 설정의 중요성:
    - 네트워크 성능에 영향
    - 분할과 재조립 오버헤드 감소
    - 효율적인 대용량 데이터 전송

1. ifconfig (Interface Configuration)

- 정의: 네트워크 인터페이스 설정 및 확인 명령어
- 주요 기능:
    - 인터페이스 활성화/비활성화
    - IP 주소 설정
    - 넷마스크 설정
    - MTU 크기 설정
- 주요 명령어:
    - ifconfig: 모든 활성 인터페이스 정보 표시
    - ifconfig eth0: 특정 인터페이스 정보 표시
    - ifconfig eth0 up/down: 인터페이스 활성화/비활성화
    - ifconfig eth0 mtu 1500: MTU 크기 설정
- 현대 리눅스에서의 대체 도구:
    - ip 명령어 (iproute2 패키지)
    - nmcli (NetworkManager)
    - 하지만 여전히 ifconfig 사용 가능

2. Fragmentation과 MTU의 관계

- MTU가 작을 경우:
    - 더 많은 fragmentation 발생
    - 네트워크 오버헤드 증가
    - 패킷 손실 가능성 증가
- MTU가 클 경우:
    - 더 적은 fragmentation
    - 효율적인 대용량 데이터 전송
    - 단일 패킷 손실 시 영향이 큼

```

### IP Class 구조 

| Class | First Octet Range | First Octet Binary | Default Subnet Mask | Network/Host Portion  | Max Networks | Max Hosts per Network |
| ----- | ----------------- | ------------------ | ------------------- | --------------------- | ------------ | --------------------- |
| A     | 1-126             | 0xxxxxxx           | 255.0.0.0 (/8)      | N.H.H.H               | 126          | 16,777,214            |
| B     | 128-191           | 10xxxxxx           | 255.255.0.0 (/16)   | N.N.H.H               | 16,384       | 65,534                |
| C     | 192-223           | 110xxxxx           | 255.255.255.0 (/24) | N.N.N.H               | 2,097,152    | 254                   |
| D     | 224-239           | 1110xxxx           | N/A                 | Multicast Address     | N/A          | N/A                   |
| E     | 240-255           | 1111xxxx           | N/A                 | Reserved for Research | N/A          | N/A                   |

추가 설명:
1. Class A
- 대규모 네트워크용
- 첫 비트는 항상 0
- 127은 루프백 주소로 예약됨
- Network ID(8비트) + Host ID(24비트)

2. Class B
- 중형 네트워크용
- 첫 두 비트는 10
- Network ID(16비트) + Host ID(16비트)

1. Class C
- 소규모 네트워크용
- 첫 세 비트는 110
- Network ID(24비트) + Host ID(8비트)

2. Class D
- 멀티캐스트용
- 첫 네 비트는 1110
- 그룹 통신에 사용

3. Class E
- 연구/실험용으로 예약
- 첫 네 비트는 1111
- 일반적으로 사용되지 않음

참고:
- 각 클래스별 최대 호스트 수는 2^n - 2 (네트워크 주소와 브로드캐스트 주소 제외)
- 현대 네트워크에서는 CIDR(Classless Inter-Domain Routing)을 주로 사용

## 4. 경로 설정 (Routing)

- 목적지까지 가는 최적의 경로를 결정합니다
- 라우팅 테이블을 참조하여 다음 홉(next hop)을 결정합니다
- 정적 라우팅이나 동적 라우팅 프로토콜을 사용합니다

### 정적 라우팅 vs 동적 라우팅 
| 특성 | 정적 라우팅 (Static Routing) | 동적 라우팅 (Dynamic Routing) |
|--------|---------------------------|----------------------------|
| **정의** | 수동으로 라우팅 테이블 설정 | 라우팅 프로토콜을 통한 자동 경로 설정 |
| **구성 방식** | 관리자가 직접 경로 입력 | 라우터 간 라우팅 정보 교환 |
| **프로토콜 예시** | - | RIP, OSPF, BGP, EIGRP |

| 장점 | 정적 라우팅 | 동적 라우팅 |
|-----|------------|-------------|
| 보안성 | 높음 (경로가 고정됨) | 중간 (인증 메커니즘 필요) |
| 리소스 사용 | 적음 | 많음 (정보 교환, 계산 필요) |
| 설정 복잡도 | 간단 (소규모 네트워크) | 복잡 (초기 설정 필요) |
| 신뢰성 | 높음 (예측 가능) | 높음 (자동 우회 경로 설정) |

| 단점    | 정적 라우팅       | 동적 라우팅         |
| ----- | ------------ | -------------- |
| 확장성   | 낮음           | 높음             |
| 장애 대응 | 수동 대응 필요     | 자동 대응 가능       |
| 관리 부담 | 많음 (수동 업데이트) | 적음 (자동 업데이트)   |
| 초기 비용 | 낮음           | 높음 (장비, 설정 비용) |

| 사용 환경 | 정적 라우팅 | 동적 라우팅 |
|----------|------------|-------------|
| 네트워크 규모 | 소규모 (End point) | 중대규모 (백본 네트워크) |
| 토폴로지 변화 | 거의 없음 | 자주 발생 |
| 구성 예시 | 가정용 네트워크<br>소규모 사무실<br>스터브 네트워크 | 기업 네트워크<br>ISP 네트워크<br>대학 캠퍼스 네트워크 |
| 대역폭 요구 | 낮음 | 높음 |

| 적용 시나리오 | 정적 라우팅 | 동적 라우팅 |
|-------------|------------|-------------|
| 기본 게이트웨이 설정 | ✓ | |
| 백업 경로 구성 | ✓ | ✓ |
| 인터넷 연결 | ✓ | |
| 복잡한 기업 네트워크 | | ✓ |
| 다중 경로 환경 | | ✓ |

추가 고려사항:
1. 하이브리드 구성
   - 대부분의 기업에서는 두 방식을 혼합하여 사용
   - 중요한 경로는 정적으로 구성
   - 나머지는 동적 라우팅으로 처리

2. 비용 효율성
   - 소규모: 정적 라우팅이 비용 효율적
   - 대규모: 동적 라우팅이 관리 비용 절감

3. 장애 복구
   - 정적: 수동 감지 및 복구
   - 동적: 자동 감지 및 복구

4. 성능 고려사항
   - 정적: 일관된 성능
   - 동적: 네트워크 상황에 따라 변동

### Routing Protocol 

먼저 각 라우팅 프로토콜을 설명하겠습니다.

1. Floating Static Routing
- 백업 경로로 사용되는 정적 라우팅
- 기본 경로보다 높은 관리 거리(AD) 값 설정
- 주 경로 실패 시 자동으로 백업 경로 활성화

2. RIP (Routing Information Protocol)
- Distance Vector 방식 사용
- 최대 홉 카운트 15
- 30초마다 전체 라우팅 테이블 교환
- 소규모 네트워크에 적합

1. OSPF (Open Shortest Path First)
- Link State 방식 사용
- Dijkstra 알고리즘으로 최단 경로 계산
- 영역(Area) 기반 계층적 구조
- 대규모 네트워크에 적합

2. BGP (Border Gateway Protocol)
- Path Vector 방식 사용
- 인터넷 백본에서 사용되는 표준 프로토콜
- AS(Autonomous System) 간의 라우팅
- 정책 기반 라우팅 지원

3. EIGRP (Enhanced Interior Gateway Routing Protocol)
- Cisco 프로토콜
- Advanced Distance Vector 방식
- DUAL(Diffusing Update Algorithm) 사용
- 빠른 수렴 시간

4. IGP (Interior Gateway Protocol)
- 단일 AS 내부의 라우팅
- RIP, OSPF, EIGRP 등이 해당
- 상대적으로 단순한 구조

5. EGP (Exterior Gateway Protocol)
- AS 간의 라우팅
- 주로 BGP가 사용됨
- 복잡한 정책 적용 가능

| 특성 | Distance Vector | Link State |
|------|----------------|------------|
| **동작 방식** | 이웃 라우터와 전체 라우팅 테이블 교환 | 네트워크 전체 토폴로지 정보 교환 |
| **알고리즘** | Bellman-Ford | Dijkstra |
| **수렴 시간** | 느림 | 빠름 |
| **대역폭 사용** | 주기적 업데이트로 많음 | 변화 시에만 업데이트 |
| **메모리 사용** | 적음 | 많음 |
| **CPU 사용** | 적음 | 많음 |
| **확장성** | 제한적 | 높음 |
| **프로토콜 예시** | RIP, EIGRP(하이브리드) | OSPF, IS-IS |
| **업데이트 주기** | 주기적 | 변화 발생 시 |
| **네트워크 규모** | 소규모 | 대규모 |
| **문제점** | Count to Infinity | 복잡한 설정 |
| **장점** | 구현 간단<br>적은 리소스 사용 | 빠른 수렴<br>효율적인 경로 선택 |
| **단점** | 느린 수렴<br>비효율적인 경로 | 높은 리소스 사용<br>복잡한 구성 |

이러한 라우팅 프로토콜들은 네트워크의 규모, 요구사항, 정책에 따라 적절히 선택하여 사용됩니다. 대부분의 대규모 네트워크에서는 여러 프로토콜을 함께 사용하는 하이브리드 접근 방식을 채택합니다.

## 5. Point to Point 패킷 전달

- 결정된 경로를 따라 각 라우터는 패킷을 다음 라우터로 전달합니다
- 각 홉(hop)에서 패킷의 헤더를 검사하고 목적지를 확인합니다
- 최종 목적지에 도달할 때까지 이 과정을 반복합니다

### Multicast vs IGMP 
멀티캐스트와 IGMP에 대해 상세히 설명해드리겠습니다.

1. 멀티캐스트(Multicast)
- 정의
  * 하나의 송신자가 특정 그룹의 수신자들에게 데이터를 동시 전송
  * 1:N 통신 방식
  * Class D IP 주소 사용 (224.0.0.0 ~ 239.255.255.255)

- 특징
  * 네트워크 대역폭 효율적 사용
  * 송신자는 패킷을 한 번만 전송
  * 라우터가 필요한 경로에만 복제하여 전달
  * 실시간 스트리밍, 화상회의 등에 적합

2. IGMP (Internet Group Management Protocol)
- 정의
  * 호스트와 라우터 간의 멀티캐스트 그룹 관리 프로토콜
  * IPv4 멀티캐스트 통신에서 사용

- 버전별 특징
  * IGMPv1
    - 기본적인 가입과 탈퇴 기능
    - Query와 Report 메시지만 존재
  
  * IGMPv2
    - Leave Group 메시지 추가
    - 그룹 탈퇴 처리 개선
  
  * IGMPv3
    - 소스 필터링 기능 추가
    - 특정 송신자로부터만 데이터 수신 가능

- 주요 메시지 유형
  1. Membership Query
     * 라우터가 호스트의 그룹 멤버십 확인
     * General Query와 Group-Specific Query

  2. Membership Report
     * 호스트가 그룹 가입 의사 전달
     * 그룹 멤버십 유지 확인

  3. Leave Group
     * 호스트가 그룹 탈퇴 시 전송
     * 빠른 대역폭 해제 가능

1. 멀티캐스트 라우팅 프로토콜
- PIM (Protocol Independent Multicast)
  * Dense Mode (PIM-DM)
  * Sparse Mode (PIM-SM)
  * Source-Specific Multicast (PIM-SSM)

- DVMRP (Distance Vector Multicast Routing Protocol)
  * 초기 멀티캐스트 라우팅 프로토콜
  * 현재는 거의 사용되지 않음

2. 멀티캐스트 응용 사례
- 실시간 스트리밍 서비스
- IPTV 서비스
- 화상 회의 시스템
- 증권 시세 정보 전송
- 소프트웨어 업데이트 배포

3. 장단점
- 장점
  * 네트워크 대역폭 절약
  * 서버 부하 감소
  * 효율적인 그룹 통신

- 단점
  * 라우터 지원 필요
  * 구성이 복잡
  * QoS 보장의 어려움

4. 구현 시 고려사항
- 네트워크 장비의 멀티캐스트 지원 여부
- 적절한 TTL 값 설정
- 대역폭 관리
- 보안 정책 수립
- 안정성 확보 방안

## NAT 
NAT와 관련 기술들에 대해 상세히 설명해드리겠습니다.

1. NAT (Network Address Translation)
- 정의
  * 사설 IP 주소를 공인 IP 주소로 변환
  * 내부 네트워크와 외부 네트워크 간의 통신 지원
  * IP 주소 부족 문제 해결

- 주요 기능
  * IP 주소 절약
  * 내부 네트워크 보안
  * 유연한 네트워크 설계

2. Static NAT
- 정의
  * 1:1 고정 주소 변환
  * 내부 사설 IP와 외부 공인 IP가 항상 동일하게 매핑

- 사용 사례
  * 웹 서버, 메일 서버 등 고정 IP 필요
  * 외부에서 내부 서버 접근 필요
  * 특정 서비스 상시 운영

- 특징
  * 보안성 낮음
  * 설정 간단
  * IP 주소 낭비 가능성

1. Dynamic NAT
- 정의
  * N:M 동적 주소 변환
  * 사설 IP 풀과 공인 IP 풀 간의 동적 매핑

- 특징
  * 필요할 때만 주소 할당
  * 주소 풀에서 자동 할당
  * 미사용 시 주소 반환

- 단점
  * 공인 IP 부족 시 연결 불가
  * Static NAT보다 복잡한 설정

2. PAT (Port Address Translation)
- 다른 이름
  * NAPT (Network Address Port Translation)
  * NAT Overload

- 동작 방식
  * 여러 사설 IP를 하나의 공인 IP로 변환
  * 포트 번호로 각 연결 구분
  * TCP/UDP 포트 번호 활용

- 장점
  * 가장 효율적인 IP 주소 사용
  * 많은 내부 사용자 수용
  * 비용 효율적

- 제한사항
  * 포트 번호 부족 가능성
  * 일부 애플리케이션 호환성 문제
  * 서버 운영의 어려움

3. NAT 구현 시 고려사항
- 보안
  * NAT 자체가 기본적인 보안 기능 제공
  * 내부 네트워크 구조 은닉
  * 추가 보안 정책 필요

- 성능
  * 주소 변환 오버헤드
  * 메모리 사용량
  * 처리 지연 발생 가능

- 애플리케이션 호환성
  * FTP, VoIP 등 특수 프로토콜 고려
  * ALG(Application Level Gateway) 필요
  * 엔드포인트 식별 문제

4. 일반적인 사용 시나리오
- 소규모 사무실
  * PAT 주로 사용
  * 단일 공인 IP로 운영

- 기업 네트워크
  * Static NAT와 PAT 혼용
  * 서버는 Static NAT
  * 일반 사용자는 PAT

- IDC 환경
  * Static NAT 주로 사용
  * 서버 접근성 보장
  * 고정 IP 매핑

## 인터넷 계층 플로우 요약 

5. 상위 계층(전송 계층)에서 데이터를 받습니다
6. 받은 데이터에 IP 헤더를 추가하여 데이터그램을 생성합니다
7. 목적지 IP 주소를 확인하고 라우팅 테이블을 참조합니다
8. 다음 홉을 결정하고 ARP를 통해 MAC 주소를 얻습니다
9. 하위 계층(네트워크 접근 계층)으로 데이터그램을 전달합니다
10. 각 라우터에서 이 과정을 반복하며 최종 목적지까지 전달됩니다