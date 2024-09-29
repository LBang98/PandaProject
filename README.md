# PANDA
개발일정: 2024.6 ~ 2024.7


중고거래 플랫폼을 통해 사용자는 동네 근처에서 원하는 중고물품을 명확한 목적지를 확인한 후, 간편한 채팅을 통해 거래할 수 있습니다.  

## Team
| Name | Role | Github |
| :--- | :---: | :--- |
| ㅇㅇ | ㅇㅇ |  |
| ㅇㅇ | ㅇㅇ |  |
| 이병현 | ㅇㅇ |  |
| ㅇㅇ | ㅇㅇ |  |
| ㅇㅇ | ㅇㅇ |  |
| ㅇㅇ |ㅇㅇ |  |


## Tech Stack
### Frontend

### Backend
![Spring Boot](https://img.shields.io/badge/-Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)

### DevOps

### Databases

### Tools


## 목차
- [소개영상](#소개영상)
- [ERD](#erd)
- [Schedule](#schedule)
- [Deployment](#deployment)
- [Main Application](#main-application)
- [API 명세서](#api-명세서)

## 소개영상
[![YouTube Video](https://private-user-images.githubusercontent.com/133863078/371852448-457b3030-85ee-4c2e-9a6a-bc70ee3bf98e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3Mjc2MTE2OTcsIm5iZiI6MTcyNzYxMTM5NywicGF0aCI6Ii8xMzM4NjMwNzgvMzcxODUyNDQ4LTQ1N2IzMDMwLTg1ZWUtNGMyZS05YTZhLWJjNzBlZTNiZjk4ZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwOTI5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDkyOVQxMjAzMTdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1kMDQ1N2QzYmY4YjI3MGNhOTNmNTk3NTM1ZWIxMGI0MTdkM2Q3NGY2ZDQ3MjFjZjI2NTI5Mjk0MGQwNmYwZmU5JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.ZOmSmu0x03be_uAMkh8yfVbEl4uNM2OLM2LSCAnY0WI)](https://www.youtube.com/watch?v=jMFjW18qeZ4)

## ERD
작업중

## Schedule
작업중

## Deployment
### Servers
이미지가 들어갈 공간(1)

- DNS/SSL
  - 가비아 네이밍 서버를 통한 DNS 구축
  - 네이버 Certificate Manager를 통하여 SSL 인증서 발급
- Load Balancer
  - 네이버 클라우드의 Application Loadbalancer를 사용
  - Path분기를 통하여 서비스별로 분기점 설정
    - /api  : CRUD및 로그인/로그아웃 로직을 실행
    - /ws   : 채팅 및 메인게임의 웹소켓 통신을 담당
    - /nws  : 미니게임들이 구현된 서버
    - /     : 클라이언트 페이지
- Servers
    - 총 두개의 서버를 사용하여 각 서버에서 복수의 Docker Container활용

### CI/CD
이미지가 들어갈 공간(2)
- Github Action를 활용한 CI/CD 프로세스 구축
  - CI : Main branch로 push또는 pull request처리가 이루어지면 repository의 내역을 토대로 build를 실행. 빌드 성공시 Dockerfile을 토대로 Docker Image를 제작하여 네이버 클라우드의 Container Reqistry로 이미지를 전송
  - CD : 네이버 클라우드 CLI를 통하여 현 깃허브 액션 실행서버에서 배포 서버로의 접근 권한 부여 후 ssh 접속을 통한 원격 접속. 이후 네이버 클라우드 Container Registry에서 신규 이미지를 pull한 후 현재 사용중인 컨테이너를 정지하고 새로 pull한 이미지를 바탕으로 새 컨테이너 실행. 작업 완료 후 불필요한 이미지 버젼 제거 및 서버 접근권한 제거
- 총 4개의 Repository를 이용하여 각 Repository별로 각개의 서비스를 구축
  - JoseonpaldoFront  : NextJS 14 기반의 프론트엔드 서버
  - JoseonpaldoBack   : 로그인 인증 및 CRUD들이 이루어지는 SpringBoot 기반의 백엔드 서버
  - maingmaews        : 메인 게임의 웹소켓 통신 및 채팅기능을 처리하는 Springboot 기반의 백엔드 서버
  - minigamews        : 미니게임들의 웹소켓 통신 및 SSE를 처리하는 ExpressJS 기반의 백엔드 서버

### 로그인
이미지 들어갈 공간(3)
이미지 들어갈 공간(3)
- 사용자 로그인
  -   RESTful 방식을 사용하여 로그인 데이터를 안전하게 데이터베이스에 저장하며, 사용자에게 간편한 플랫폼 접근성을 제공합니다.


### 반응형 디자인
이미지 들어갈 공간(3)
이미지 들어갈 공간(3)
- 사용자 로그인
  -   다양한 기기에서 일관된 화면을 제공하여 사용자 경험을 향상시킵니다.  
  -   사용자가 PC, 태블릿, 모바일 등 다양한 환경에서도 최적화된 화면을 경험할 수 있습니다.
 
### 리뷰 및 별점 부여 기능
이미지 들어갈 공간(4)
- GameRoom
  - 거래가 완료된 후, 구매자는 판매자에게 리뷰를 남기고 별점을 부여할 수 있어 신뢰할 수 있는 거래 환경을 조성합니다.
  - 진행여부에 따라 조사 가능
  - 방장의 이름 또는 방의 제목을 통한 검색기능 제공

### 1:1 채팅 기능
이미지 들어갈 공간(5)
- 실시간 1:1 채팅을 통해 판매자와 구매자가 편리하게 중고물품 거래를 진행할 수 있습니다.
  - 거래 내역을 플랫폼 내에서 관리할 수 있어 거래 기록도 남습니다.

### NCP 챗봇 지원
이미지 들어갈 공간(Chatting)
- WebSocket 기반의 서버를 구축
- NCP 챗봇을 통해 거래 방법, 절차에 대한 질문에 빠르고 간단한 답변을 받을 수 있습니다.
- 사용자는 복잡한 과정을 거치지 않고도 필요한 정보를 쉽게 얻을 수 있습니다.


## API 명세서
이미지 들어갈 공간(7)
- swagger와 spring docs를 이용하여 작성
- authorize 기능을 이용하여 spring security로 보호된 엔드포인트도 테스트 가능
