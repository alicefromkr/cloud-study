# 프로토콜
- 송신자와 수신자 사이에 통신을 하기 위해 서로간에 한 약속 

## 프로토콜 구성 요소

### 구문 Syntax
- 데이터 형식
- 신호 레벨
- 부호화

### 의미 Semantics
- 개체의 조정
- 에러제어 정보

### 순서 Timing
- 순서 제어
- 통신 속도 제어 

## 데이터 전송 방식

### Case 1. 비트 단위 
- HDLC (High Level Data-link Control) protocol
- SDLC (Synchronous Data-link Control) protocol 

### Case 2. 바이트 단위
- DDCM (Digital Data Communication Message) protocol 

### Case 3. 문자 단위
- BSC (Binary Synchronous Communication) protocol 

# OSI 7계층
- 개방형 시스템
- 모든 테이터 통신 기준
- 국제표준화 기구 

## Layer 7 Application 계층
- 프로그램 있는 계층
- 데이터 송신을 위해 메세지를 만든다 
- HTTP, FTP, SNMP, SMTP 

## Layer 6 Presentation 계층
- 코드화 
- 사전에 정해진 코드로 변환
- 메세지 압축 및 암호화 

## Layer 5 Session 계층
- 동기화 신호
- 세션 연결

## Layer 4 Transport 계층
- 송신자 수신자 간에 논리 연결
- End To End 연결
- TCP, UDP

## Layer 3 Network 계층
- IPV4, IPV6

## Layer 2 Data Link 계층
- 에러탐지, 흐름제어 

## Layer 1 Physical 계층
- 물리적 기계

# 에러 제어 

## 오류 검출 코드
- Hamming Code
- CRC
- Parity Bit
- FEC
- BEC