# JCHS-ALGORRITHM-Client

> 교내 온라인 저지 ALGORRITHM v2 웹 (React · Vite)

제천고등학교 코딩 동아리 코딩연구소의 교내 온라인 저지 ALGORRITHM을 2024년에 다시 작성한 웹 클라이언트다. [JCHS-ALGORRITHM-Server](https://github.com/son-daehyeon/JCHS-ALGORRITHM-Server)의 API를 사용한다. 초기 버전은 [JCHS-ALGORRITHM-Client-v1](https://github.com/son-daehyeon/JCHS-ALGORRITHM-Client-v1)에 있다.

## 주요 기능
- 회원가입·로그인 화면과 쿠키에 저장한 토큰 기반 로그인 상태 유지
- 사용자 정보 페이지(`/user/:username`)와 프로필·비밀번호 변경 모달
- 관리자 전용 사용자 관리(`/admin/user`)와 태그 생성·수정·삭제(`/admin/tag`) 화면
- 로그인 여부와 관리자 권한에 따라 페이지 접근을 막는 가드(User, Guest, Admin)
- API 오류 메시지를 토스트로 보여 주는 axios 래퍼

## 기술 스택
| 영역 | 기술 |
|---|---|
| 언어 | JavaScript (JSX) |
| 프레임워크 | React 18, Vite 5, React Router 6, Redux Toolkit, Tailwind CSS 3 |

## 구조
```
src/
  main.jsx, app/App.jsx   진입점과 라우트 정의
  pages/                  사용자·관리자·오류 페이지
  components/             헤더, 사용자·태그 테이블과 모달
  guard/                  UserGuard, GuestGuard, AdminGuard
  redux/                  사용자 상태 슬라이스
  utils/axios.js          API 호출과 오류 토스트 처리
vite.config.js            /api, Swagger 경로를 127.0.0.1:8080으로 프록시
```

## 실행
```bash
yarn install
yarn dev
```
개발 서버는 `/api` 요청을 `http://127.0.0.1:8080`의 서버로 넘긴다.

## 관련 저장소
- [JCHS-ALGORRITHM-Server](https://github.com/son-daehyeon/JCHS-ALGORRITHM-Server) — API 서버
- [JCHS-ALGORRITHM-Judge-Image](https://github.com/son-daehyeon/JCHS-ALGORRITHM-Judge-Image) — 채점용 Docker 이미지
- [JCHS-ALGORRITHM-Client-v1](https://github.com/son-daehyeon/JCHS-ALGORRITHM-Client-v1) — 초기 버전 웹

---
2024 · 개인 프로젝트 · 보관됨
