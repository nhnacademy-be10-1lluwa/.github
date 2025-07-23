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

---

## 🚀 CI/CD & 운영 프로세스

<p align="center">
  <img src="/CI_CD.drawio.png" width="90%">
</p>

### 1. 이슈 및 라벨 관리
- 모든 개발/수정/테스트/문서화 작업은 반드시 **GitHub Issue**를 먼저 생성후
- 각 이슈에는 작업 목적에 맞는 **라벨**(refactor, chore, test ..등)을 지정해줍니다.
  - 예시:
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

#### 📚 **Git 협업/커밋 컨벤션 자세히 보기**
- [Git 협업 규칙 (Notion)](https://www.notion.so/Git-20cf030dd17d80e3a498ee999a201ba9?source=copy_link)
- [Git Commit Message Convention (Notion)](https://www.notion.so/Git-Commit-Message-Convention-20cf030dd17d8152ada7ee85a929403b?source=copy_link)

---

## ERD

> 전체 도메인 ERD 설계는 아래 링크에서 확인 가능합니다.

- [🌐 ERD Cloud](https://www.erdcloud.com/d/bqAZmQ8TgYuTMF3eW)


---

# 📖 주요 기능

### 🏗️ 인프라
* 담당자: 배성환

### 🖥️ 프론트(figma ,html, css)
* 담당자: 김강길

### 📮 주소
* 담당자: 최가은

### 📖 도서
* 담당자: 최혁

### 🔍 검색(Elastic Search)
* 담당자: 최혁

### ☑️ 카테고리
* 담당자: 최혁

### 🛒 장바구니
* 담당자: 신찬섭

### 🎟️ 쿠폰
* 담당자: 최정환

### 👤 회원
* 담당자: 최가은

### 📱 주문
* 담당자: 박진호

### 💳 결제
* 담당자: 배성환

### 💰 포인트
* 담당자: 최가은

### 📝 리뷰
* 담당자: 오준현

### 🏷️ 태그

### ❤️ 좋아요

---
## 📄 팀내 자료

---

## 🛠️ Stack


---

## 📬 Contact
