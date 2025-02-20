# NIC (Network Interface Card)

```ad-note
title: Network Interface Card

- 호스트에서 네트워크와의 연결을 담당한 인터페이스 역할을 하는 장치 -> LAN 카드
- NIC 내부에는 RAM, DSP 칩, 호스트 버스 인터페이스 등으로 이루어져 있다. -> 데이터링크 계층용 프로토콜 구현 

자료 출처: [KT 정보통신기술용어해설](http://www.ktword.co.kr/test/view/view.php?nav=2&no=980&sh=nic)
```

```ad-claude
title: NIC 구성요소 


| 구성 요소 | 설명 |
|-----------|-------------|
| RAM (Random Access Memory) | - 네트워크 데이터의 임시 저장소로 사용 |
| DSP (Digital Signal Processor) 칩 | - 디지털 신호 처리를 담당<br>- 네트워크 데이터의 인코딩/디코딩 수행 |
| 호스트 버스 인터페이스 | - 컴퓨터의 메인보드와 NIC를 연결하는 인터페이스<br>- PCI, PCIe 등의 형태로 구현 |
| MAC (Media Access Control) | - 데이터 링크 계층의 주소 지정과 접근 제어 담당<br>- 물리적 주소(MAC 주소) 관리 |
| PHY (Physical Layer) 칩 | - 물리적 계층의 신호 변환 담당<br>- 디지털 신호를 전기/광 신호로 변환하거나 그 반대 수행 |
| ROM (Read Only Memory) | - NIC의 펌웨어와 MAC 주소 등 기본 설정 저장<br>- 부팅 시 초기화 정보 제공 |
| LED 표시등 | - 네트워크 연결 상태와 활동 상태를 시각적으로 표시 |

```


```ad-summary
title: NIC에 대해서 설명해보세요. 

NIC는 컴퓨터에서 네트워크와의 연결을 담당하는 인터페이스 역할을 합니다. 물리적인 LAN 카드를 데이터 링크 계층의 프로토콜을 실행하기 위해 호스트 버스 인터페이스가 있습니다.

NIC는 baseband를 사용해서 디지털 신호를 변환하는데요. baseband는 디지털 신호를 변조 없이 직접 전송하는 방식입니다. 이는 한 번에 하나의 디지털 신호만 전송할 수 있지만, 신호의 왜곡이 적고 구현이 간단하다는 장점이 있습니다.

NIC 카드 마다 MAC주소가 할당 되어 있습니다. MAC 주소 할당은 데이터 링크 계층에서 실행되며, MAC 주소의 상위 24비트는 제조사 번호입니다. 하위 24비트는 제조사가 부여한 고유 일련번호로, 이렇게 총 48비트로 구성됩니다. 예를 들어 '00:1B:44:11:3A:B7'처럼 16진수로 표현되죠.

NIC는 고성능의 데이터 처리를 위해 DMA(Direct Memory Access) 컨트롤러를 사용합니다. DMA 컨트롤러는 CPU의 개입 없이 시스템 메모리와 NIC 사이에서 직접 데이터를 주고받는 역할을 합니다. 이렇게 함으로써 시스템의 전체적인 성능을 향상시키고 CPU의 부하를 줄일 수 있습니다.

```

## NIC 카드 종류 

```ad-claude
title: NIC 카드 종류 

| 종류 | 표준 | 속도 | 호환성 | 사용 케이블 |
|------|------|------|---------|------------|
| Token Ring | IEEE 802.5 | 4/16 Mbps | Token Ring 전용 | STP Type 1/6 |
| ATM LAN | ATM Forum | 155/622 Mbps | ATM 네트워크 | UTP Cat 5, 광섬유 |
| 이더넷 (10BASE-T) | IEEE 802.3 | 10 Mbps | 이더넷 | UTP 케이블 Cat 3/5 |
| 패스트 이더넷 (100BASE-TX) | IEEE 802.3u | 100 Mbps | 이더넷, 10BASE-T | UTP 케이블 Cat 5/5e |
| 기가비트 이더넷 (1000BASE-T) | IEEE 802.3ab | 1 Gbps | 이더넷, 100BASE-TX, 10BASE-T | UTP 케이블 Cat 5e/6 |
| 10 기가비트 이더넷 (10GBASE-T) | IEEE 802.3an | 10 Gbps | 이더넷, 1000BASE-T | UTP 케이블 Cat 6a/7 |
| 기가비트 이더넷 (1000BASE-SX) | IEEE 802.3z | 1 Gbps | 이더넷 | 다중모드 광섬유 |
| 기가비트 이더넷 (1000BASE-LX) | IEEE 802.3z | 1 Gbps | 이더넷 | 단일모드 광섬유 |
| 무선 LAN (Wi-Fi 5) | IEEE 802.11ac | 최대 3.5 Gbps | 802.11a/b/g/n | 해당 없음 |
| 무선 LAN (Wi-Fi 6) | IEEE 802.11ax | 최대 9.6 Gbps | 802.11a/b/g/n/ac | 해당 없음 |
| 무선 LAN (Wi-Fi 6E) | IEEE 802.11ax | 최대 9.6 Gbps | 802.11a/b/g/n/ac/ax | 해당 없음 |

```

## ISA (Industry Standard Architecture)

```ad-note
title: ISA (Industry Standard Architecture)

**설명:**
- 초기 PC인 IBM PC의 XT 및 AT에서 사용하던 8 bit 또는 16 bit 구조 방식 
- 버스폭 16bit 단위, 최대 전송속도 8MB/s 

**호환성:**
- 2000년 이후의 컴퓨터 메인보드에서는 ISA 슬롯을 사용하지 않는다. 

자료 출처: [KT 정보통신기술용어해설](http://www.ktword.co.kr/test/view/view.php?nav=2&no=732&sh=isa)

```

```ad-note
title: DMA Controller 

**설명:**
- CPU의 도움 없이, 주변장치 들이 직접 메모리에 읽고 쓸 수 있는 방식이다. 
- 이와 반대되는 경우가 PIO (Programmed I/O)이다. 
- CPU의 I/O 작업을 덜어주기 위해 DMA 방식을 사용한다.

**단점:** 컴퓨터 버스 상에 여러 장치들이 서로 경쟁하게 만들어, 이를 조정해야한다. 

**호환성:** 
- PC에서의 DMA는 **ISA** 형태의 버스에서만 존재한다.

**한줄 설명:** 각 장치들은 DMA에 의해 PC 에인 버스를 통해 CPU를 거치지 않고 직접 데이터를 메인 메모리에 전달하는 것이 가능하다. 

자료 출처: [KT 정보통신기술용어해설](http://www.ktword.co.kr/test/view/view.php?nav=2&no=981&sh=dma)
```

## PCI (Peripheral Component Interconnect)
```ad-note
title: PCI (Peripheral Component Interconnect)

**설명:**
- Intel에서 만든 컴퓨터 주변장치와의 연결을 위한 47핀 짜리 고속 버스 방식에 대한 규격명 

**PCI 2.0**
- 1993년 3월 개발 
- 33MHz 전송속도 지원 
- 32bit 버스 폭 

**PCI 2.1**
- 1955년 2월 개발
- 66MHz 전송속도 지원 
- 64bit 버스 폭 

**PCI-X**
- IBM, 컴팩, HP 등에서 공동으로 규격 제작 
- 초당 1GB 속도로 자료 전송

자료 출처: [KT 정보통신기술용어해설](http://www.ktword.co.kr/test/view/view.php?nav=2&no=2538&sh=pci)

```

```ad-note
title: PCIe (PCI Express)

**설명:** 
- 2003년에 Intel, Dell, HP, IBM에서 합작해서 PCI 후속 인터페스로 개발했다 
- 2004년부터 규격을 사용했다 
- 기존 PCI의 병렬 버스 방식은 신호 왜곡, 다수 기기 간 동기화 문제 등 발생해서 보다 높은 고속 데이터 전송의 한계에 도달해 새로 개발했다. 
- PCI Express는 Point to Point 프로토콜 방식으로 동작한다. 

**PCI Express 1.0**
- 2003년 
- 2 Gbps 

**PCI Express 2.0**
- 2007년 
- 4 Gbps

**PCI Express 3.0**
- 2010년
- 8 Gbps

**PCI Express 4.0**
- 2019년
- 16 Gbps 

자료 출처: [KT 정보통신기술용어해설](http://www.ktword.co.kr/test/view/view.php?nav=2&no=3582&sh=PCI%2FPCIe)

```

```ad-claude
title: 버스 마스터링 

1. 정의
- 주변장치가 버스의 제어권을 가져와 직접 시스템 버스를 제어할 수 있는 기능
- CPU의 개입 없이 주변장치가 독립적으로 데이터를 전송할 수 있음

2. 작동 방식

[일반적인 데이터 전송]
주변장치 → CPU에 요청 → CPU가 버스 제어 → 메모리에 데이터 전송

[버스 마스터링]
주변장치가 버스 제어권 요청 → 승인 받으면 직접 메모리와 데이터 전송


1. 특징
- 여러 장치가 버스 마스터가 될 수 있음
- 장치들 간의 우선순위 조정 가능
- DMA 컨트롤러 없이도 직접 메모리 접근 가능
- PCI/PCIe 버스에서 표준으로 지원

2. 장점
- CPU 부하 감소
- 시스템 성능 향상
- 데이터 전송 효율성 증가
- 실시간 데이터 처리에 유리

3. 사용 예
- NIC에서 네트워크 데이터 전송
- 그래픽 카드의 화면 데이터 처리
- 하드디스크의 대용량 데이터 전송

버스 마스터링은 현대 컴퓨터 시스템에서 고성능 데이터 전송을 위한 핵심 기술이라고 할 수 있습니다.
```

## Microsoft Windows NIC 

```ad-note
title: NIC 카드 확인 

윈도우 장치 관리자 > 네트워크 어댑터 > NIC 카드 확인 가능 
```

# VLAN 

- 하나의 물리적인 스위치를 여러 개의 논리적 환경으로 구성해서 각기 다른 설정과 관리르 할 수 있는 네트워크 가상기술 
- IEEE 802.10 

## RAID 

