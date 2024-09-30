# PANDA
개발일정: 2024.06.04 ~ 2024.07.02


중고거래 플랫폼을 통해 사용자는 동네 근처에서 원하는 중고물품을 명확한 목적지를 확인한 후, 간편한 채팅을 통해 거래할 수 있습니다.  

## Team
|      시바타유니       |          정민석         |       우태형         |          이병현         |       공병현         |       김창인         |
| :-------------------: | :---------------------: | :------------------: | :---------------------: | :------------------: | :------------------: |
|   <img width="225" alt="시바타유니" src="https://github.com/DevCampUs-FiveGuys/main/assets/147224562/b21dec68-d37a-47de-aa23-dc9da9662415">    |     <img width="225" alt="정민석" src="https://github.com/DevCampUs-FiveGuys/main/assets/147224562/c8f378a7-8775-485a-a394-5c68b328c06c">    |    <img width="225" alt="우태형" src="https://github.com/DevCampUs-FiveGuys/main/assets/147224562/104bfaf5-3399-40c2-80f0-4b7e41704ea3">   |    <img width="225" alt="이병현" src="https://github.com/DevCampUs-FiveGuys/main/assets/147224562/83339d9e-3dcb-444a-9fea-3869257879a5">   |    <img width="225" alt="공병현" src="https://github.com/DevCampUs-FiveGuys/main/assets/147224562/63fc823e-d3d8-46a1-b445-40356c614827">   |    <img width="225" alt="김창인" src="https://github.com/DevCampUs-FiveGuys/main/assets/147224562/63fc823e-d3d8-46a1-b445-40356c614827">   |


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
- [Function](#function)

## 소개영상
[![YouTube Video](<img src="/src/main/resources/static/image/panda.png" width="370" height="370">
)](https://www.youtube.com/watch?v=jMFjW18qeZ4)

## ERD
작업중

## Schedule
작업중

## Deployment
### CI/CD
이미지가 들어갈 공간(2)
- NCP를 이용해 배포
  - CI : Main branch로 push또는 pull request처리가 이루어지면 repository의 내역을 토대로 build를 실행. 빌드 성공시 Dockerfile을 토대로 Docker Image를 제작하여 네이버 클라우드의 Container Reqistry로 이미지를 전송
  - CD : 네이버 클라우드 CLI를 통하여 현 깃허브 액션 실행서버에서 배포 서버로의 접근 권한 부여 후 ssh 접속을 통한 원격 접속. 이후 네이버 클라우드 Container Registry에서 신규 이미지를 pull한 후 현재 사용중인 컨테이너를 정지하고 새로 pull한 이미지를 바탕으로 새 컨테이너 실행. 작업 완료 후 불필요한 이미지 버젼 제거 및 서버 접근권한 제거

## ERD
작업중

## Schedule
작업중

## Deployment

### CI/CD
![이미지 들어갈 공간(2)](https://via.placeholder.com/370)
- NCP(Naver Cloud Platform)를 이용해 배포하였습니다.
  - **CI**: Main branch로 push 또는 pull request가 발생하면, GitHub Actions를 통해 repository의 내역을 기반으로 자동 빌드가 실행됩니다. 빌드 성공 시, Dockerfile을 바탕으로 Docker Image를 생성하고, 네이버 클라우드의 Container Registry에 이미지를 업로드합니다.
  - **CD**: 네이버 클라우드 CLI를 사용해 배포 서버에 접근 권한을 부여하고, SSH를 통해 서버에 원격 접속 후 새로운 이미지를 pull하여 기존 컨테이너를 교체합니다. 컨테이너 업데이트 후 불필요한 이미지 버전을 삭제하고, 보안을 위해 접근 권한을 제거합니다.

---

### 로그인
![이미지 들어갈 공간(3)](https://via.placeholder.com/370)

#### 1. 로그인

##### 1-1. 이메일과 비밀번호 기반 사용자 인증
- 사용자는 이메일과 비밀번호를 통해 로그인할 수 있습니다.
- **로그인 성공 시**: `HttpSession`을 사용하여 사용자 정보를 세션에 저장합니다.
- **로그인 실패 시**: 로그인 실패 메시지가 모달 창을 통해 사용자에게 표시됩니다.

---

### 회원가입
![이미지 들어갈 공간(3)](https://via.placeholder.com/370)

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

##### 2-4. 비밀번호 유효성 검사
- **비밀번호**와 **비밀번호 확인** 필드의 일치 여부를 **실시간 체크**합니다.

##### 2-5. 닉네임 설정
- 사용자는 회원가입 과정에서 **닉네임**을 설정할 수 있으며, **닉네임 중복 체크** 기능이 포함되어 있습니다.

##### 2-6. 프로필 이미지 설정
- 사용자는 **기본 프로필 이미지** 3개 중 하나를 선택할 수 있습니다.
- **사용자 지정 이미지 업로드** 기능도 제공되며, 업로드된 이미지는 **미리보기** 기능을 통해 확인할 수 있습니다.

---

### 반응형 디자인
![이미지 들어갈 공간(3)](https://via.placeholder.com/370)
- 플랫폼의 첫 인상을 결정짓는 메인 화면을 설계 및 개발하였습니다.
  - 직관적인 UI/UX를 적용하여 사용자가 쉽게 중고물품을 탐색하고 거래를 시작할 수 있도록 최적화하였습니다.
  - Tailwind CSS와 JavaScript를 사용해 사용자 친화적인 인터페이스를 구현하였습니다.
- 다양한 기기에서 일관된 사용자 경험을 제공하기 위해 Media Queries, Flexbox, CSS Grid를 사용하여 반응형 디자인을 구현하였습니다.
- Tailwind CSS를 활용하여 PC, 모바일, 태블릿 등 다양한 환경에 맞춘 직관적인 UI를 개발하였습니다.

---

### 리뷰 및 별점 부여 기능
![이미지 들어갈 공간(4)](https://via.placeholder.com/370)
- **GameRoom**에 리뷰 및 별점 부여 기능을 추가하여 사용자 피드백 기반의 신뢰성을 확보하였습니다.
- 서버에서 사용자 리뷰와 별점을 저장 및 관리하며, 별점 평균을 실시간으로 계산하여 UI에 반영합니다.

---

### 1:1 채팅 기능
![이미지 들어갈 공간(5)](https://via.placeholder.com/370)
- WebSocket과 STOMP 프로토콜을 사용하여 실시간 1:1 채팅 기능을 구현하였습니다.
  - 서버는 WebSocket을 통해 양방향 통신을 지원하며, 클라이언트와의 실시간 데이터를 주고받습니다.
  - 비동기 처리 및 Pub/Sub 패턴을 적용하여 메시지 지연을 최소화하고 성능을 최적화하였습니다.

---

### NCP 챗봇 지원
![이미지 들어갈 공간(Chatting)](https://via.placeholder.com/370)
- WebSocket 기반으로 NCP CLOVA 챗봇을 구축하여 실시간으로 사용자의 질문에 대응할 수 있는 환경을 개발하였습니다.
  - CLOVA AI를 사용하여 자연어 처리 모델을 통해 사용자 질문에 대한 적절한 답변을 실시간으로 제공합니다.

---

### 위치 설정 (Kakaomap API)
![이미지 들어갈 공간(7)](https://via.placeholder.com/370)
- Kakaomap API를 사용하여 거래 장소 설정을 지원합니다.
  - 사용자는 자신의 위치 또는 거래 상대방의 위치를 지도상에서 설정하고, 거래 장소를 실시간으로 확인할 수 있습니다.

---

### 결제 시스템 (TossPayment API)
![이미지 들어갈 공간(7)](https://via.placeholder.com/370)
- TossPayment API를 통해 안전한 결제 시스템을 구축하였습니다.
  - 결제 정보는 HTTPS로 암호화되어 안전하게 처리되며, Google Captcha API를 연동하여 스팸 및 악성 봇의 접근을 방지합니다.

---

## WebSocket을 이용한 NCP의 CLOVA 메신저 챗봇 개발
- NCP CLOVA AI를 활용하여 실시간으로 PANDA 플랫폼 관련 정보를 제공하는 메신저 챗봇을 개발하였습니다.
  - WebSocket을 통해 사용자와 챗봇 간의 실시간 상호작용을 구현하여 사용자 문의에 대한 즉각적인 응답을 제공합니다.

---

## Redis 서버를 통한 SMTP 메시지 인증 개발
- Redis 서버를 이용하여 SMTP 기반의 메시지 인증 시스템을 개발하였습니다.
  - 빠르고 안전한 인증 메커니즘을 제공하여 사용자 계정 보호와 비밀번호 복구 기능을 지원합니다.

---

## TOSSPAYMENT API를 이용한 결제 시스템 및 Google Captcha API 연동
- TOSSPAYMENT API를 활용하여 안전하고 간편한 결제 시스템을 구축하였습니다.
  - Google Captcha API를 연동하여 보안을 강화하고, 결제 과정에서 악성 요청을 방지합니다.





