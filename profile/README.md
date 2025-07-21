# 📚 Book1lluwa
> **Book1lluwa**는 도서 판매를 위한 온라인 쇼핑몰을 MSA(Microservices Architecture) 구조로 구현한 프로젝트입니다.<br/>
실제 서비스 환경을 고려해 회원가입부터 주문, 결제, 리뷰 작성, 쿠폰 적용까지의 전자상거래 전 과정을 분산 아키텍처로 구성하였으며, JWT 인증, Redis, Toss Payments API 연동, 무중단 배포 환경 구성(CI/CD) 등 실무와 유사한 환경을 경험할 수 있도록 설계하였습니다.

프로젝트 기간: 2025.05 ~ 2025.07

개발 인원: 8명

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

## 🚀 CI/CD

---
## ERD

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
