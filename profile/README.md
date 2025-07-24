# 📚 Book1lluwa
> **Book1lluwa**는 도서 판매를 위한 온라인 쇼핑몰을 MSA(Microservices Architecture) 구조로 구현한 프로젝트입니다.<br/>
실제 서비스 환경을 고려해 회원가입부터 주문, 결제, 리뷰 작성, 쿠폰 적용까지의 전자상거래 전 과정을 분산 아키텍처로 구성하였으며, JWT 인증, Redis, Toss Payments API 연동, 무중단 배포 환경 구성(CI/CD) 등 실무와 유사한 환경을 경험할 수 있도록 설계하였습니다.

프로젝트 기간: 2025.05 ~ 2025.07
## 🎯 주요 목적
- MSA 아키텍처 학습 및 적용
- CI/CD 및 무중단 배포 환경 구축 경험
- Spring Security + JWT 기반 인증 인프라 설계 및 구현
- Gateway의 인증/인가 필터 구현 및 서비스간 JWT 전달 체계 확립
- 대용량 트래픽을 고려한 서비스 구조 설계
- Toss Payments API 직접 연동 및 환불 처리 기능 구현
---
### 📖 도메인
https://book1lluwa.store

---

## 🧑‍🤝‍🧑 팀원

<table align="center" style="border-collapse: collapse; margin: 20px auto; background: #f9f9f9; border-radius: 15px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
    <tr>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/pear-c" style="text-decoration: none; color: #333;">
                <img src="https://github.com/pear-c.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="배성환"/><br/>
                <sub><b style="font-size: 14px;">배성환</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/JJungH0" style="text-decoration: none; color: #333;">
                <img src="https://github.com/JJungH0.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="최정환"/><br/>
                <sub><b style="font-size: 14px;">최정환</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/nhdor" style="text-decoration: none; color: #333;">
                <img src="https://github.com/nhdor.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="최혁"/><br/>
                <sub><b style="font-size: 14px;">최혁</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/RiveroadKim" style="text-decoration: none; color: #333;">
                <img src="https://github.com/RiveroadKim.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="김강길"/><br/>
                <sub><b style="font-size: 14px;">김강길</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/koreanguyyyy" style="text-decoration: none; color: #333;">
                <img src="https://github.com/koreanguyyyy.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="박진호"/><br/>
                <sub><b style="font-size: 14px;">박진호</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/bestofGE" style="text-decoration: none; color: #333;">
                <img src="https://github.com/bestofGE.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="최가은"/><br/>
                <sub><b style="font-size: 14px;">최가은</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/JunHyeonOh" style="text-decoration: none; color: #333;">
                <img src="https://github.com/JunHyeonOh.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="오준현"/><br/>
                <sub><b style="font-size: 14px;">오준현</b></sub>
            </a>
        </td>
        <td align="center" style="padding: 20px;">
            <a href="https://github.com/haini000" style="text-decoration: none; color: #333;">
                <img src="https://github.com/haini000.png" width="120px" style="border-radius: 50%; border: 3px solid #ddd;" alt="신찬섭"/><br/>
                <sub><b style="font-size: 14px;">신찬섭</b></sub>
            </a>
        </td>
    </tr>
</table>

---

## 🛠️ Service Introduce

> - **Book1lluwa**는 클라우드 환경을 적용한 도서 쇼핑몰 웹 애플리케이션입니다.
> - 주요 기능:
>    - **회원 관리**: 회원가입, 로그인, 권한 설정
>    - **도서 검색 및 관리**: 도서 등록, 검색, 분류, 리뷰
>    - **주문 및 결제**: 장바구니, 주문 생성 및 상태 확인
>    - **포인트 및 쿠폰**: 적립, 쿠폰 관리 및 적용
---

## 🌐 System Architecture

<p align="center">
    <img width="2537" height="1399" alt="system drawio" src="https://github.com/user-attachments/assets/afb7e0a5-a7c7-47c1-9f41-d9378ade95e1" />
</p>


> ###### 1. 클라이언트의 요청은 Cloud Flare와 Nginx를 거쳐 Front 서버로 전달됩니다.
> ###### 2. 로그인은 Payco OAuth2 방식을 지원하여 확장성과 외부 인증 연계를 고려하였으며, Spring Boot 애플리케이션 실행 시:
> ###### &nbsp;&nbsp;&nbsp;&nbsp; – 베스트셀러 도서 정보는 알라딘 Open API를 통해 조회 후 Redis에 캐싱하고, <br/> &nbsp;&nbsp;&nbsp;&nbsp; – 도서 카테고리 정보는 DB에서 조회한 뒤 일정 시간 동안 Redis에 저장합니다.
> ###### 3. Eureka Server는 각 서비스를 중앙에서 관리하고 연결하기 위한 서비스 디스커버리 역할을 수행합니다.
> ###### 4. 모든 서비스는 이중 인스턴스로 구성되어 Eureka에 등록되며, Gateway는 이를 기반으로 로드밸런싱 및 라우팅을 수행합니다.
> ###### 5.  Gateway는 Eureka를 통해 각 서비스로 클라이언트 요청을 라우팅하며, 내부 요청 시 JWT 토큰을 검증하고, <br/> &nbsp;&nbsp;&nbsp;&nbsp; 사용자 정보를 헤더에 담아 다운스트림 서비스로 전달하는 역할도 수행합니다.
> ###### 6. Auth Service는 사용자 인증, JWT 토큰 발급 및 재발급을 담당하며, 발급된 토큰은 Front에 전달된 후 쿠키에 저장되어 인증 수단으로 활용됩니다.
> ###### 7. 회원, 상품, 결제, 주문 등 주요 도메인의 데이터는 MySQL을 통해 저장 및 관리됩니다.
> 
---

## 🚀 CI/CD & 운영 프로세스

<p align="center">
  <img width="1881" height="419" alt="CI_CD drawio" src="https://github.com/user-attachments/assets/f6243c1d-b8cb-4f29-8beb-f016bf996e96" />
</p>

### 1. 이슈 및 라벨 관리
- 모든 개발/수정/테스트/문서화 작업은 반드시 **GitHub Issue**를 먼저 생성후
- 각 이슈에는 작업 목적에 맞는 **라벨**(feat, refactor, chore, test ..등)을 지정해줍니다.
  - 예시:
    - feat (기능 구현)
    - refactor (리팩토링)
    - chore (설정, 기타 작업)
    - test (테스트)

### 2. 브랜치 네이밍 규칙
- **[라벨]/[이슈번호]-[작업명]** 형태로 브랜치를 생성합니다.
  - 예:
    - feature/123-coupon-policy-api
    - bug/345-coupon-fix

### 3. 커밋/PR 컨벤션
- 커밋 메시지와 PR 제목/본문에는 **이슈번호**를 반드시 포함합니다.
  - 예:
    - `feat: 로그인 API 구현 (#123)`
    - `fix: 주문 날짜 버그 수정 (#345)`

### 4. 자동화(CI/CD) 및 품질 관리

#### 4-1. **배포 자동화 (Deploy Workflow)**
- 각 도메인별 `.github/workflows/deploy.yml` 파일로 관리합니다.
- **main 브랜치에 PR이 머지될 때마다**
  - Maven 빌드
  - 서버에 jar 업로드
  - 서비스 재시작이 자동으로 실행됩니다.

#### 4-2. **코드 품질 분석 (SonarQube Workflow)**
- `.github/workflows/sonarQube.yml`로 코드 품질과 테스트 커버리지 분석을 자동화합니다.
- **develop 브랜치로 PR을 생성할 때마다**
  - 빌드, 테스트, 커버리지 리포트 생성
  - SonarQube 품질 분석이 자동으로 수행됩니다.
 
#### 4-3. **무중단 배포 (SonarQube Workflow)**
- 각 서비스는 **두 개의 인스턴스(서로 다른 포트)** 로 구성되어 Eureka에 이중 등록되어 있습니다.
- 배포 시, 쉘 스크립트를 통해 인스턴스를 하나씩 교체하며
  - 먼저 한 인스턴스를 종료 후 재시작하고,
  - **헬스 체크가 통과되면 다음 인스턴스를 교체**하는 방식으로 진행합니다.
- 이를 통해 사용자 요청에 영향을 주지 않는 **롤링 방식의 무중단 배포**를 실현하였습니다.

#### 📚 **Git 협업/커밋 컨벤션 자세히 보기**
- [Git 협업 규칙 (Notion)](https://www.notion.so/Git-20cf030dd17d80e3a498ee999a201ba9?source=copy_link)
- [Git Commit Message Convention (Notion)](https://www.notion.so/Git-Commit-Message-Convention-20cf030dd17d8152ada7ee85a929403b?source=copy_link)

---

## ERD
<img width="4790" height="2476" alt="BookStore #2" src="https://github.com/user-attachments/assets/45ebd4e3-66de-4cea-afef-e7ec3aa14225" />

> 전체 도메인의 자세한 설계는 아래 링크를 통해 확인 가능합니다.
- [🌐 ERD Cloud](https://www.erdcloud.com/d/bqAZmQ8TgYuTMF3eW)

---

# 📖 주요 기능

### 🏗️ 인프라
* 담당자: 배성환
  - MSA 기반 아키텍처 설계 및 도메인 운영
  - GitHub Actions 기반 CI/CD 자동화 및 무중단 배포 스크립트 구현
  - Spring Cloud Config Server를 통한 설정 중앙 관리
  - Swagger 적용 및 API 문서 자동화 설정
  - Logback 설정을 통한 서비스별 로그 관리 및 포맷 통일


### 🖥️ 프론트(figma ,html, css)
* 담당자: 김강길
  - 피그마 설계 및 구조 설계
  - html 레이아웃 템플릿 제작
  - 공통 css 구현
  - Thymeleaf를 이용한 서버사이드 랜더링 및 예외처리
  - OpenFeign통신 클라이언트 설계 및 예외처리
  - WireMock, Mockito, WebMvcTest를 이용한 테스트 환경 설계

### 📮 주소
* 담당자: 최가은
  - 회원별 다중 배송지(주소) CRUD 구현
  - 외부 주소 API연동으로 실제 주소 검증
  - 주문 결제시 기본/선택 주소 지정
  
### 📖 도서
* 담당자: 최혁
  - 도서 CRUD 구현
  - 알라딘 API 사용하여 도서 정보를 등록
  - MinioStorage를 통한 이미지 등록
  - Pagenation 추가

### 🔍 검색(Elastic Search)
* 담당자: 최혁
  - Elasticsearch을 이용한 도서 통합 검색
  - QueryDsl로 동적/복합 쿼리 자동 생성 및 관리
  - 검색 결과 Pagenation 처리

### ☑️ 카테고리
* 담당자: 최혁
  - 카테고리 CRUD 구현
  - 3계층으로 카테고리 분류

### 🛒 장바구니
* 담당자: 신찬섭
  - 장바구니 CRUD 구현

### 🎟️ 쿠폰
* 담당자: 최정환

### 👤 회원
* 담당자: 배성환, 최가은
  - 회원 CRUD 구현
  - PAYCO를 통한 로그인(OAuth2) 지원
  - DooraySender를 통한 휴먼회원 해제
  - 비회원 로그인 구현 (주문번호를 기반으로 로그인)
  - JWT 기반 회원 인증/인가 체계 구현
  - 회원 상태(정상/휴먼/탈퇴) 관리
  - DB 비밀번호 암호화(BCrypt 적용)

### 📱 주문
* 담당자: 박진호
  - 주문 CRUD 구현
  - SpringBatch를 활용한 대량 데이터 업데이트 처리
  - 회원/비회원 주문/조회 기능구현
  - 주문 플로우 (다양한 흐름 지원)
  - 포장 옵션 선택
  - 배송비 정책
  - 주문 상태 관리
  - 주문 처리(관리자)
  - 반품/환불 처리 및 결제 취소 구현

### 💳 결제
* 담당자: 배성환
  - Toss Payments API 사용
  - 결제 시 쿠폰, 포인트 정책을 기반으로 사용 적용
  - 결제 결과 주문 상태와 연동
 

### 💰 포인트
* 담당자: 최가은
  - 회원 적립금(포인트) CRUD 구현
  - 결제시 포인트 사용/적립 로직 구현
  - 포인트 소멸/유효기간 확인(마이페이지)
  - 등급에 따른 적립율 구현

### 📝 리뷰
* 담당자: 오준현
  - 리뷰 CRUD 구현
  - 사용자가 주문한 도서에 한하여 리뷰 작성기능 구현
  - 별점, 사진 첨부 등 다양한 리뷰 유형 지원

### 🏷️ 태그
* 담당자: 최혁
  - 도서/카테고리별 자유 태그 추가 및 검색 지원

### ❤️ 좋아요
* 담당자: 오준현
  - 좋아요 CRUD 구현
  - 회원별 좋아요 목록 저장 및 조회
---
## 📄 팀내 자료
- 🎨 [Figma Design](https://www.figma.com/community/file/1514522679983172396)

---

## 🛠️ Stack

> CI/CD & 품질 관리
<div>
  <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=GitHub+Actions&logoColor=FFFFFF" alt="GitHubActions"/>
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white" alt="GitHub"/>
  <img src="https://img.shields.io/badge/SonarQube-4E9BCD?style=for-the-badge&logo=sonarqube&logoColor=white" alt="SonarQube"/>
    <img src="https://img.shields.io/badge/Spring%20Cloud-00ADEF?style=for-the-badge&logo=Spring&logoColor=FFFFFF" alt="SpringCloud"/>
  <img src="https://img.shields.io/badge/Apache%20Maven-C71A36?style=for-the-badge&logo=Apache+Maven&logoColor=FFFFFF" alt="ApacheMaven"/>
</div>

> Backend / Framework
<div>
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=Spring&logoColor=FFFFFF" alt="Spring"/>
  <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=Spring+Boot&logoColor=FFFFFF" alt="SpringBoot"/>
  <img src="https://img.shields.io/badge/JPA-6DB33F?style=for-the-badge&logo=spring&logoColor=white" alt="JPA"/>
    <img src="https://img.shields.io/badge/OpenFeign-0089BF?style=for-the-badge&logo=OpenFeign&logoColor=white" alt="OpenFeign"/>
    <img src="https://img.shields.io/badge/Spring%20Batch-6DB33F?style=for-the-badge&logo=Spring&logoColor=FFFFFF" alt="Spring Batch"/>
    <img src="https://img.shields.io/badge/Swagger-222222?style=for-the-badge&logo=Swagger&logoColor=85EA2D" alt="Swagger"/>
</div>

> Front
<div>
    <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=Figma&logoColor=FFFFFF" alt="Figma"/>
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=HTML5&logoColor=FFFFFF" alt="HTML5"/>
    <img src="https://img.shields.io/badge/CSS-663399?style=for-the-badge&logo=CSS&logoColor=FFFFFF" alt="CSS"/>
    <img src="https://img.shields.io/badge/JavaScript-222222?style=for-the-badge&logo=JavaScript&logoColor=F7DF1E" alt="JavaScript"/>
</div>

> Database / Data
<div>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=MySQL&logoColor=FFFFFF" alt="MySql"/>
  <img src="https://img.shields.io/badge/Redis-FF4438?style=for-the-badge&logo=Redis&logoColor=FFFFFF" alt="Redis"/>
  <img src="https://img.shields.io/badge/Elasticsearch-005571?style=for-the-badge&logo=Elasticsearch&logoColor=FFFFFF" alt="ElasticSearch"/>
  <img src="https://img.shields.io/badge/Logstash-005571?style=for-the-badge&logo=Logstash&logoColor=FFFFFF" alt="LogStash"/>
  <img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=RabbitMQ&logoColor=FFFFFF" alt="RabbitMq"/>
</div>

> Security / API
<div>
  <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=for-the-badge&logo=Spring+Security&logoColor=FFFFFF" alt="SpringSecurity"/>
  <img src="https://img.shields.io/badge/JSON%20Web%20Tokens-000000?style=for-the-badge&logo=JSON+Web+Tokens&logoColor=FFFFFF" alt="JWT"/>
</div>

> Web Server / Infra
<div>
  <img src="https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=NGINX&logoColor=FFFFFF" alt="Nginx"/>
</div>

> Test Code
<div>
    <img src="https://img.shields.io/badge/JUnit5-25A162?style=for-the-badge&logo=JUnit5&logoColor=FFFFFF" alt="Junit5"/>
    <img src="https://img.shields.io/badge/WireMock-7B4AE2?style=for-the-badge&logo=wiremock&logoColor=white" alt="WireMock"/>
    <img src="https://img.shields.io/badge/Mockito-4CAF50?style=for-the-badge&logo=mockito&logoColor=white" alt="Mockito"/>
</div>

---

## 📬 Contact
