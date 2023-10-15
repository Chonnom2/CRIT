# CRIT
[https://crithub.shop/](https://crithub.shop/)

## 프로젝트 개요

---

SSAFY 9기 2학기 공통 프로젝트

2023-07-04 ~ 2023-08-18

## 프로젝트 기획 배경

CRIT은 단순한 챌린지 서비스를 넘어, 참가자들이 '함께' 성장하는 커뮤니티를 제공합니다. 기존에 '혼자'서 미션을 수행하고 사진으로 인증하던 챌린져스의 방식은 소통의 아쉬움을 더했습니다. 그 아쉬움과 무료한 인증의 루틴을 깨기 위해, CRIT은 강화된 ‘소셜 기능’을 중심으로 숏폼과 다양한 게시글을 통해 참가자들 간의 소통을 가능하게 합니다.

또한, 실시간 인증 시스템은 단순히 사진을 찍고 잠에 드는 루틴을 벗어나, 참가자들이 그 순간의 진정한 변화와 성취감을 실시간으로 공유하고 함께 즐길 수 있습니다. 이를 통해 참가자들은 일상의 소중한 순간을 모아 점차 '갓생'을 살 수 있도록 하고, CRIT 커뮤니티와 함께 더 큰 성장을 추구할 수 있습니다. CRIT에서 함께하는 챌린지는 단순한 목표 달성이 아닌, 함께 나누며 성장하는 경험이 될 것입니다.

## 서비스명 & 로고

---

![crit1](https://github.com/D201-Crit/CRIT/assets/110797992/0bbc27f5-d2ef-43ae-ab75-ae710686aad6)

- C : Create Goals(목표를 설정하세요)
- R : Realize your Goals(목표를 거머쥐세요)
- I : Improve yourself everyday(매일 자신을 개선하세요)
- T : Try again when you fail(실패하면 다시 시도하세요)

## 주요 기능

---

## 챌린지

- 등록되어 있는 챌린지에 도전하세요
- 만약 맘에 드는 챌린지가 없으면 직접 만들고 사람을 모으세요
- 챌린지가 시작하면 인증방식에 맞는 인증방법을 사용하세요
    - **실시간 AI화상인증**
        - 화면에 나오는 얼굴을 AI가 인식하여 챌린지에 집중하는지 확인합니다.
        - 만약 자리를 이탈하면 경고창이 나옵니다.
        - 챌린지를 마치고 화상회의방에서 나오면 자리에 있었던 시간을 보여줍니다.
        - 자리에 있는 시간이 85%미만이면 인증 실패 처리가 됩니다.
    - **사진인증**
        - 챌린지가 진행이 되는 시간 안에 챌린지를 진행하고 있는 사진을 첨부해서 올리면 인증이 됩니다.
- 참여내역을 통해 현재까지 진행한 기록을 볼 수 있습니다.
- 오늘의 한 마디로, 챌린지에 참여하는 모든 분들과 함께 힘을 모아 달려봅시다.

## 커뮤니티 & 소셜

- **쇼츠 컨텐츠**
    - 직접 촬영한 챌린지 과정을 공유해 보세요
    - 챌린지 꿀팁을 공유해 보세요
- **개인 피드 작성**
    - 하루하루 성장하는 모습을 기록하세요
- **다양한 커뮤니티 게시판**
    - 게시판에서 다양한 사람들과 소통해보세요
- **다양한 사람들과 팔로잉 & 팔로우**
    - 다음 챌린지를 같이하고 싶은 사람과 인연을 맺으세요

## CRIT 기능 소개

---
### 시작페이지 & 회원가입 & 로그인
![회원가입](https://github.com/D201-Crit/CRIT/assets/110797992/82188ac5-34c6-4f2b-966f-042fa8e8207d)

### 메인페이지 & 커뮤니티
![메인페이지](https://github.com/D201-Crit/CRIT/assets/110797992/931f9b3b-9f2a-4775-8bda-c5c1de93ab68)

### 프로필 & 메시지
![프로필](https://github.com/D201-Crit/CRIT/assets/110797992/2be628a5-ae4f-400d-9da7-7ece3b8fdc0c)

### 챌린지
![챌린지](https://github.com/D201-Crit/CRIT/assets/110797992/94b784b6-804d-425f-ba6f-eb94c0dc9377)

## 기술 차별점

---

### Spring Security

Spring Security에서 제공하는`UsernamePasswordAuthenticationFilter`와 Access Token을 이용하여 인증이 완료된 사용자의 정보를 `HttpServletRequest`에 담아줍니다. 이를 통해 로그인 한 사용자의 정보를 URL에 노출하지 않고 식별할 수 있습니다.

### Web RTC, OpenVidu 라이브러리를 사용

OpenVidu라이브러리를 사용하여 kurento-midea-server를 거쳐 서로 영상정보를 송수신할 수 있는 시스템을 구축 및 적용했습니다. 챌린지를 설정할 때 특정 인원수만큼 들어 올 수 있게 설정하였고 해당 인원수에 도달하면 챌린지가 시작할 수 있게 하였습니다.

### Docker, Jenkins를 이용한 CI/CD구축 및 SSL인증서 적용

`Docker image` `Jenkins`의 `pipeline`을 이용하여 자동 배포를 구축했습니다. `Gitlab webhook`을 설정하여 Jenkins에 빌드 트리거를 설정했으며 Gitlab에서 master 브랜치에 push하면 자동으로 배포될 수 있도록 구축하여 개발하는 과정에서 배포로 인한 시간 낭비를 줄였습니다.

- `frontend`, `Vue js`에서는 `Nginx`와 함께 ec2서버에서 빌드한 후 배포
- `backend`, `springBoot`에서는 `docker image`로 빌드한 후 배포
- `nginx`와 `letsencrypt`를 통해 `ssl` 인증서를 적용했고 `frontend`에서는 `/`로 `80(http)`, `443(https)` 로 프록시를 분리시켰고, `backend`에서는 `/api`로 `80(http)`, `443(https)` 로 프록시를 분리

### aws S3, cloudfront를 이용한 파일업로드

쇼츠(Shorts) 컨텐츠 및 커뮤니티 기능을 제공함으로써 사용자들에게 풍부한 미디어 경험을 제공하고자 합니다. 이에 따라 예상되는 대량의 이미지와 동영상 파일을 효율적으로 관리하기 위해 Amazon S3 스토리지 솔루션을 채택하였습니다. 이 선택은 대용량 미디어 파일을 안정적으로 저장하고 확장 가능한 구조를 확보하기 위함입니다.

뿐만 아니라, 사용자들이 이러한 미디어 컨텐츠를 빠르게 접근할 수 있도록 하기 위해 Amazon CloudFront 콘텐츠 전송 네트워크를 통해 S3와 연동하였습니다. 이렇게 함으로써 미디어 파일들은 전 세계 다양한 위치의 사용자들에게 저지연으로 제공될 수 있게 되었으며, 이는 웹 페이지의 로딩 속도를 현격하게 개선시켰습니다. CloudFront의 캐싱 및 가속화 기능을 활용함으로써 사용자 경험의 품질을 높이고, 더 나아가 서비스의 성과를 향상시키는 데 기여하였습니다.

## 개발 환경

---

### 1.1 Frontend

- Node js 18.19.0
- React 18.2.0
- axios 1.4.0
- jquery 3.7.0
- swiper 10.1.0

### **1.2 Backend**

- Java 11
    - java OpenJDK
    - Spring Boot
        - Spring Data JPA
        - Spring Security
        - oauth2
        - JUnit
        - Lombok
        - Swagger
    - Gradle 1.0.10
    - drewnoakes 2.18.0

### 1.3 Server

- Ubuntu 20.04.3
- Nginx 1.18.0
- Docker 24.0.4
- Docker-Compose 2.20.2
- OpenVidu 2.28.0
- Jenkins 2.401.3

### 1.4 Database

- mariaDB 2.4.1

### 1.5 UI/UX

- Figma

### 1.6 IDE

- Visual Studio Code
- IntelliJ IDEA

### 1.7 형상 / 이슈관리

- Gitlab
- Jira

### 1.8 기타 툴

- Sonarqube 4.6.2
- S3 2.2.6
- Cloudfront
- mattermost 7.8.6
- jasypt 2.14.2
- postman 10.17.0
- teachable machine 0.8.5

## 아키텍처

---
![수정한_아키텍쳐2__1_](https://github.com/D201-Crit/CRIT/assets/110797992/cc7ec62d-ec67-42af-8ab6-ef1550d83488)

## ERD

---
![erd](https://github.com/D201-Crit/CRIT/assets/110797992/78e831a1-bcbd-4073-8cd7-19565497d583)

## 협업 툴

---

- GitLab
- Jira
- Notion
- Mattermost
