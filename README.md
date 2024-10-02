# PANDA
개발일정: 2024.06.04 ~ 2024.07.02


중고거래 플랫폼을 통해 사용자는 동네 근처에서 원하는 중고물품을 명확한 목적지를 확인한 후, 간편한 채팅을 통해 거래할 수 있습니다.  

## Team
|      시바타유니       |          정민석         |       우태형         |          이병현         |       공병현         |       김창인         |
| :-------------------: | :---------------------: | :------------------: | :---------------------: | :------------------: | :------------------: |
|   <img width="300" alt="시바타유니" src="https://github.com/user-attachments/assets/ae829d06-1fdc-44a6-9f26-8ccaea075510">    |     <img width="300" alt="정민석" src="https://github.com/user-attachments/assets/fa508cc8-eef9-46d8-a96f-0aecd1ce29da">    |    <img width="300" alt="우태형" src="https://github.com/user-attachments/assets/5c9225d1-76ba-4538-84b4-44215c2635a0">   |    <img width="300" alt="이병현" src="https://github.com/user-attachments/assets/f8381b2a-0cd3-4ae9-9734-568de6267a3e">   |    <img width="300" alt="공병현" src="https://github.com/user-attachments/assets/c4f11261-6b85-419a-b4a5-e4227771d29f">   |    <img width="300" alt="김창인" src="https://github.com/user-attachments/assets/9f3cc4a7-3224-498f-8a07-77346aa4675d">   |


## Tech Stack

### Backend
![Spring Boot](https://img.shields.io/badge/-Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)

### Frontend
![Tailwind CSS](https://img.shields.io/badge/-Tailwind%20CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![jQuery](https://img.shields.io/badge/-jQuery-0769AD?style=flat-square&logo=jquery&logoColor=white)
![HTML5](https://img.shields.io/badge/-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

### CI / CD
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Apache Tomcat](https://img.shields.io/badge/-Apache%20Tomcat-F8DC75?style=flat-square&logo=apache-tomcat&logoColor=black)
![Jenkins](https://img.shields.io/badge/-Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)
![Naver Cloud Platform](https://img.shields.io/badge/-Naver%20Cloud%20Platform-03C75A?style=flat-square&logo=naver&logoColor=white)

### Databases
![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

### Tools
![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github&logoColor=white)
![Payment](https://img.shields.io/badge/-Payment-FF4B4B?style=flat-square&logo=mastercard&logoColor=white)



## 목차
- [소개영상](#소개영상)
- [ERD](#erd)
- [Schedule](#schedule)
- [Deployment](#deployment)

## 소개영상
[<img src="https://github.com/user-attachments/assets/51aab568-af9a-4927-a700-b2a533f1e02c" alt="panda" width="300">](https://www.youtube.com/watch?v=jMFjW18qeZ4)

## ERD
<img width="300" alt="ERD" src="https://github.com/user-attachments/assets/89381c31-ef76-4de4-aee6-279970e96682">

## Schedule
<img width="300" alt="schedule" src="https://github.com/user-attachments/assets/ab2a8f02-a1d1-4dc7-b1fe-94de889e9fc8">

## CI/CD

GitHub Webhooks, Jenkins, Docker, 및 Tomcat을 사용하여 CI/CD 파이프라인을 구성하였습니다. 다음은 각 구성 요소의 역할과 설정 방법입니다.

### 1. GitHub Webhooks
GitHub Webhooks를 통해 코드 변경 사항을 자동으로 감지합니다. Main 브랜치에 푸시가 발생하면 웹훅이 트리거되어 Jenkins 서버에 알림을 보냅니다.

### 2. Jenkins
Jenkins는 CI/CD 도구로, GitHub에서 받은 웹훅 알림을 기반으로 자동 빌드를 수행합니다. Jenkins에서 설정한 파이프라인은 다음과 같은 단계로 구성됩니다:

- **코드 체크아웃**: GitHub 저장소에서 최신 코드를 가져옵니다.
- **빌드**: Maven을 사용하여 프로젝트를 빌드하고, WAR 파일을 생성합니다.
- **테스트**: 자동화된 테스트를 실행하여 코드의 품질을 확인합니다.

### 3. Docker와 Tomcat
이 프로젝트에서는 Docker를 사용하여 Tomcat 서버를 컨테이너화하였습니다. Jenkins에서 생성된 WAR 파일은 Docker로 실행 중인 Tomcat 컨테이너에 전달되어 배포됩니다. 이 과정은 다음과 같이 진행됩니다:

- **Tomcat 컨테이너 실행**: Docker를 사용하여 Tomcat 서버를 실행합니다. 이 서버는 애플리케이션을 호스팅하는 환경을 제공합니다.
- **WAR 파일 배포**: Jenkins는 빌드가 완료된 후 생성된 WAR 파일을 Docker로 실행 중인 Tomcat 컨테이너에 배포합니다. 이를 통해 최신 애플리케이션 버전이 자동으로 업데이트됩니다.

이러한 CI/CD 파이프라인을 통해 코드 변경 사항이 발생할 때마다 자동으로 빌드 및 배포가 이루어져, 개발 속도를 높이고 안정성을 향상시킬 수 있습니다.

---

### 로그인
<img width="300" alt="login" src="https://github.com/user-attachments/assets/edde22b9-4312-4203-a69e-7bda7f8f91c4">

#### 1. 로그인

##### 1-1. 이메일과 비밀번호 기반 사용자 인증
- 사용자는 이메일과 비밀번호를 통해 로그인할 수 있습니다.
- **로그인 성공 시**: `HttpSession`을 사용하여 사용자 정보를 세션에 저장합니다.
- **로그인 실패 시**: 로그인 실패 메시지가 모달 창을 통해 사용자에게 표시됩니다.

---

### 회원가입
<img width="300" alt="register" src="https://github.com/user-attachments/assets/a2052cef-b27b-458a-8996-ba24065832e4">

#### 2. 회원가입

##### 2-1. 단계별 프로세스
- 회원가입은 **2단계**로 나누어져 있습니다.
  1. **첫 번째 페이지**에서 사용자 기본 정보를 입력합니다.
  2. **두 번째 페이지**에서 프로필 이미지와 닉네임을 설정합니다.

##### 2-2. 사용자 정보 입력
- 회원가입 과정에서 사용자는 다음 정보를 입력합니다:
  - 이름
  - 전화번호
  - 주소 (카카오 주소 API 활용)
  - 이메일
  - 비밀번호
  - 생년월일

##### 2-3. 이메일 인증 시스템
- **이메일 중복 체크** 기능이 포함되어 있습니다.
- 회원가입 시, **인증 코드**가 이메일로 발송됩니다.
- **3분 타이머**가 설정되어 있으며, 해당 시간 내에 인증을 완료해야 합니다.
- 사용자는 인증 코드를 입력하여 **이메일 인증**을 완료할 수 있습니다.

##### 2-4. 비밀번호 유효성 검사 및 암호화
- **비밀번호**와 **비밀번호 확인** 필드의 일치 여부를 **실시간 체크**합니다.
- **비밀번호는 해시 함수**(예: `bcrypt`)를 사용하여 안전하게 암호화되어 저장되며, **로그인 시 복호화 없이** 입력한 비밀번호를 해시화하여 비교하는 방식으로 인증이 처리됩니다.

##### 2-5. 닉네임 설정
- 사용자는 회원가입 과정에서 **닉네임**을 설정할 수 있으며, **닉네임 중복 체크** 기능이 포함되어 있습니다.

##### 2-6. 프로필 이미지 설정
- 사용자는 **기본 프로필 이미지** 3개 중 하나를 선택할 수 있습니다.
- **사용자 지정 이미지 업로드** 기능도 제공되며, 업로드된 이미지는 **미리보기** 기능을 통해 확인할 수 있습니다.

---

### 반응형 디자인
<img width="300" alt="panda-1" src="https://github.com/user-attachments/assets/9feccfb0-ab56-4cdd-8f60-27f12c5e9b82">

- 플랫폼의 첫 인상을 결정짓는 메인 화면을 설계 및 개발하였습니다.
  - 직관적인 UI/UX를 적용하여 사용자가 쉽게 중고물품을 탐색하고 거래를 시작할 수 있도록 최적화하였습니다.
  - Tailwind CSS와 JavaScript를 사용해 사용자 친화적인 인터페이스를 구현하였습니다.
- 다양한 기기에서 일관된 사용자 경험을 제공하기 위해 Media Queries, Flexbox, CSS Grid를 사용하여 반응형 디자인을 구현하였습니다.
- Tailwind CSS를 활용하여 PC, 모바일, 태블릿 등 다양한 환경에 맞춘 직관적인 UI를 개발하였습니다.

---

### 마이페이지

- **판매 내역 및 구매 내역**: 사용자는 자신의 판매 내역과 구매 내역을 한눈에 확인할 수 있으며, 진행 중인 거래 상태를 쉽게 관리할 수 있습니다.
- **찜 목록**: 사용자는 관심 있는 상품들을 찜 목록에 추가하여 관리하고, 언제든지 빠르게 접근할 수 있습니다.
- **별점 및 리뷰 확인**: 거래가 완료된 상품에 대해 받은 **별점**과 **리뷰**를 확인할 수 있으며, 이를 바탕으로 서비스 품질을 개선할 수 있습니다.
- **개인정보 수정**: **비밀번호 확인** 절차를 거친 후, 사용자는 자신의 개인정보를 안전하게 수정할 수 있습니다.

---

### 상품 등록 및 상품 상세사항

- **상품 등록**: 상품을 등록할 때 **KakaoMap API**를 사용하여 정확한 **위치 정보**를 함께 등록할 수 있어, 상품의 위치를 명확하게 표시할 수 있습니다.
- **찜하기 기능**: 등록된 상품 페이지에서는 다른 사용자가 해당 상품을 **찜 목록**에 추가할 수 있으며, 이를 통해 상품의 인기도를 파악할 수 있습니다.
- **채팅 및 예약**: 사용자는 등록된 상품에 대해 실시간 **채팅** 기능을 통해 문의할 수 있으며, 상품을 **예약**할 수도 있어 거래 편의성이 높습니다.

### 리뷰 및 별점 부여 기능

- 거래 후 리뷰 및 별점 부여 기능을 추가하여 사용자 피드백 기반의 신뢰성을 확보하였습니다.
- 서버에서 사용자 리뷰와 별점을 저장 및 관리하며, 별점 평균을 실시간으로 계산하여 UI에 반영합니다.

---

### 1:1 채팅 기능
<img width="300" alt="chatting" src="https://github.com/user-attachments/assets/c0186ea5-4969-4900-84aa-d6f0b164fe8e">

- WebSocket을 사용하여 실시간 1:1 채팅 기능을 구현하였습니다.
  - 서버는 WebSocket을 통해 양방향 통신을 지원하며, 클라이언트와의 실시간 데이터를 주고받습니다.
  - 비동기 처리 및 Pub/Sub 패턴을 적용하여 메시지 지연을 최소화하고 성능을 최적화하였습니다.

---

### 위치 설정 (Kakaomap API)

- Kakaomap API를 사용하여 거래 장소 설정을 지원합니다.
  - 사용자는 자신의 위치 또는 거래 상대방의 위치를 지도상에서 설정하고, 거래 장소를 실시간으로 확인할 수 있습니다.

---

## WebSocket을 이용한 NCP의 CLOVA 메신저 챗봇 개발
<img width="300" alt="chatbot" src="https://github.com/user-attachments/assets/7c859424-2cea-412c-888b-c5b5238127b3">

- NCP CLOVA AI를 활용하여 실시간으로 PANDA 플랫폼 관련 정보를 제공하는 메신저 챗봇을 개발하였습니다.
  - WebSocket을 통해 사용자와 챗봇 간의 실시간 상호작용을 구현하여 사용자 문의에 대한 즉각적인 응답을 제공합니다.
  - CLOVA AI를 사용하여 자연어 처리 모델을 통해 사용자 질문에 대한 적절한 답변을 실시간으로 제공합니다.

---

## Redis 서버를 통한 SMTP 메시지 인증 개발
<img width="300" alt="pw2" src="https://github.com/user-attachments/assets/7472a2ee-8147-49c2-9b90-a7af1c0dcf86">
<img width="300" alt="pw" src="https://github.com/user-attachments/assets/5f4ea52f-9651-482b-88a9-5fde057391a1">
<img width="300" alt="email" src="https://github.com/user-attachments/assets/7d30bb5e-b525-4ba8-b6c2-c3080cab407d">

- Redis 서버를 이용하여 SMTP 기반의 메시지 인증 시스템을 개발하였습니다.
  - 빠르고 안전한 인증 메커니즘을 제공하여 사용자 계정 보호와 비밀번호 복구 기능을 지원합니다.

---

## TOSSPAYMENT API를 이용한 결제 시스템 및 Google Captcha API 연동
<img width="300" alt="toss" src="https://github.com/user-attachments/assets/266a1fe6-42ad-4be4-b0c8-de7d293a6d3a">

- TossPayment API를 통해 안전한 결제 시스템을 구축하였습니다.
  - 결제 정보는 HTTPS로 암호화되어 안전하게 처리되며, Google Captcha API를 연동하여 스팸 및 악성 봇의 접근을 방지합니다.




