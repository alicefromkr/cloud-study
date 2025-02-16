
# Internet Information Server
- 웹서버 
- .Net Frame work
- Active Server Page (Script)

## Installation
- 서버 관리자
- 관리 메뉴, 역할 및 기능 추가 메뉴 
- 단일 서버 = 역할 기반 또는 기능 기반 
- 서버풀 = 서버 스토리지 

## Function
- HTTP Redirection
- HTTP STATUS
- HTTP Logging
- ASP + .NET
- SSL
- ISAPI + CGI 지원
- ISAPI 필터 
- MIME 형식 지원 

```ad-claude
각각의 개념을 설명해드리겠습니다:

1. ISAPI + CGI 지원

- ISAPI(Internet Server Application Programming Interface)는 IIS에서 웹 애플리케이션을 만들기 위한 Microsoft의 API입니다
- CGI(Common Gateway Interface)는 웹 서버가 외부 프로그램과 통신하기 위한 표준 프로토콜입니다
- IIS에서 이 두 기술을 모두 지원하여 동적 웹 콘텐츠를 생성할 수 있습니다

2. ISAPI 필터

- 웹 서버로 들어오고 나가는 모든 요청과 응답을 가로채서 처리할 수 있는 DLL입니다
- 주요 용도:
    - URL 재작성
    - 사용자 인증
    - 요청/응답 데이터 압축
    - 로깅
    - 보안 기능 추가

1. MIME 형식 지원

- MIME(Multipurpose Internet Mail Extensions)은 파일 형식을 식별하는 표준입니다
- IIS는 다양한 MIME 타입을 지원하여 서버가 다양한 유형의 파일을 올바르게 전송할 수 있게 합니다
- 예시:
    - text/html: HTML 파일
    - image/jpeg: JPEG 이미지
    - application/pdf: PDF 문서
    - application/javascript: JavaScript 파일

이러한 기능들은 IIS가 더 유연하고 확장 가능한 웹 서버로 동작할 수 있게 해주는 핵심 구성요소들입니다. 특히 동적 콘텐츠 생성과 다양한 파일 형식 처리에 중요한 역할을 합니다.
```

### 가상 디렉터리 
- 앱을 가상 디렉터리에 넣어서 보안성 추가 