# 🐶 ZOOZOO CLUB | 관리자 회원 관리 기능 포트폴리오
> 이루강 | 반려동물 커뮤니티 & 쇼핑몰 웹사이트 팀 프로젝트  
> 담당 파트: **회원조회 / 회원등급관리 / 회원게시물관리**

---

## 🌱 프로젝트 개요
**ZOOZOO CLUB**은 반려동물 보호자를 위한 커뮤니티형 쇼핑몰 웹사이트입니다.  
반려인들이 소통하고, 상품을 구매하며, 체험단과 리뷰를 공유할 수 있는 플랫폼입니다.

---

## 💡 프로젝트의 목적
> “반려동물과 함께 사는 사람들을 위한  
> 커뮤니티 기반의 쇼핑몰 및 정보 공유 플랫폼 구축”

---

## ⚙️ 제공하는 기능
- **회원조회** : 회원 정보 조회, 관리자 권한 부여/회수  
- **회원등급관리** : 게시글 수 기반 등급 자동 산정  
- **회원게시물관리** : 게시글 공개/비공개 제어 및 통계 확인  
- **포인트/쿠폰 시스템** : 활동에 따른 포인트 적립 및 쿠폰 발급  
- **체험단 모집** : 사용자 참여형 리뷰 & 상품 체험 신청 기능  

---

## 👩‍💻 담당 기능 상세

| 기능명 | 설명 | 기술 포인트 |
|--------|------|-------------|
| 회원조회 | 다중 회원 선택 및 관리자 여부 변경 | jQuery 체크박스 제어 / Form 동적 전송 |
| 회원등급관리 | 게시글 수 기반 자동 등급 산정 | SQL JOIN + NVL 처리 / MyBatis 매핑 |
| 회원게시물관리 | 게시물 공개/비공개 Ajax 처리 | 비동기 요청 중복 방지 / 실시간 UI 갱신 |

---

## 🧱 ERD
<img src="./img/erd.png" width="700"/>

> 주요 테이블: `USER`, `BOARD`, `POINT`, `ATTACHMENT`, `EXPERIENCE_GROUP`  
> 사용자-게시글 관계를 기반으로 등급, 포인트, 쿠폰, 체험단 연동 관리.

---

## 🖼️ 주요 화면

### 👥 회원조회
<img src="./img/member_list.png" width="700"/>

### 🏅 회원등급관리
<img src="./img/member_grade.png" width="700"/>

### 🗂️ 회원게시물관리
<img src="./img/member_post_manage.png" width="700"/>



---

## 🧩 코드리뷰 
```javascript
$('#updateAdminBtn').on('click', function () {
  const checked = $('.row-check:checked');
  if (checked.length === 0) return alert('수정할 회원을 선택하세요.');
  if (!confirm('관리자 여부를 변경하시겠습니까?')) return;

  const form = $('#memberForm');
  form.attr('action', '/admin/updateAdminStatus')
      .attr('method', 'POST')
      .submit();
});
✅ jQuery 기반 다중 회원 선택 및 동적 Form 전송 로직 구현
✅ confirm + 예외처리로 사용자 UX 개선

🧰 기술 스택
분류	기술
Frontend	HTML5, CSS3, JavaScript, jQuery
Backend	Spring Boot 3.x, MyBatis
Database	Oracle 11g
Tools	STS, DBeaver, SourceTree, GitHub



💬 프로젝트 소감
관리자 기능을 직접 구현하며 데이터 흐름 제어와 Ajax 통신의 중요성을 배웠습니다.
단순한 CRUD를 넘어서, 사용자 경험 중심의 기능 설계를 고민할 수 있었습니다.
팀 협업 과정에서 깃 충돌 해결과 커뮤니케이션의 중요성을 깨달았습니다.

🧠 핵심 역량
Spring Boot + MyBatis 기반 백엔드 설계

SQL JOIN 및 데이터 집계 최적화

jQuery 이벤트 제어 및 Ajax 비동기 로직 구현

Git 브랜치 병합 및 협업 경험
