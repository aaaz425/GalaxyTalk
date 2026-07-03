# 은하수다 (GalaxyTalk)

---

## 프로젝트 소개

우주 테마의 AI 기반 고민 유사도 점수를 활용한 1:1 매칭 화상 채팅 서비스

![logo.png](doc/logo.png)

> 외로운 별들을 위한 빛나는 만남,
> 익명의 마음들이 전하는 따스한 위로,
> 고민 속에서 서로를 발견하며 함께 힐링해요

---

## 스크린샷

| 홈 | 매칭 대기 | 화상 채팅 |
| --- | --- | --- |
| ![home](doc/screenshots/home.png) | ![match](doc/screenshots/match.png) | ![chat](doc/screenshots/chat.png) |

---

## 기술 스택

### Frontend

| 분류 | 라이브러리 |
| --- | --- |
| Core | React 19, Vite, TypeScript |
| 3D | React Three Fiber, Drei, @react-three/postprocessing |
| 화상통화 | LiveKit (livekit-client, @livekit/components-react) |
| 실시간 | STOMP.js, SockJS |
| 상태관리 | Zustand, TanStack Query v5 |
| UI | shadcn-ui, Tailwind CSS, motion |
| 모바일 | Capacitor (Android / iOS) |
| 개발 도구 | MSW, ESLint, Prettier |

### Backend / Infra

Spring Boot · MySQL · MongoDB · Redis · MSA (Gateway + Eureka) · Docker · Jenkins · Nginx

---

## 주요 기능

| 기능 | 설명 |
| --- | --- |
| 3D 우주 씬 | React Three Fiber + Drei로 행성·은하수·별자리 우주 배경 구현, Postprocessing 빛 번짐 효과 |
| WebRTC 화상 채팅 | LiveKit 기반 1:1 화상·음성 통화, 커스텀 컨트롤바·오디오 비주얼라이저·이모지 리액션 |
| 실시간 매칭 | WebSocket으로 매칭 대기·수락/거절 흐름 처리, Zustand 전역 상태 관리 |
| AI 고민 유사도 매칭 | 고민 텍스트 임베딩 유사도로 비슷한 상대와 1:1 연결 |
| 소셜 로그인 | Kakao·Naver OAuth 2.0, JWT Refresh Token Rotation |
| 마이페이지 | 받은 편지 목록, 계정 설정 |
| MSW 목업 | 전 API 핸들러 구성, BE 없이 프론트 독립 개발 가능 |

---

## 프로젝트 구조

Feature-Sliced Design(FSD) 아키텍처를 기반으로 구성했습니다.

```
Client/src/
├── app/          # 앱 진입점, 라우터, 전역 설정 및 스토어
├── pages/        # 페이지 단위 컴포넌트
│   ├── home/     # 랜딩 · 로그인 · 매칭 폼
│   ├── match/    # 매칭 대기 화면
│   ├── chatting/ # 화상 채팅 화면
│   ├── mypage/   # 마이페이지
│   └── signup/   # 회원가입
├── features/     # 도메인 기능 (user, match, feedback, letter)
├── widget/       # 3D 씬 컴포넌트 (Galaxy, Planet, SpaceWarp, SnowHouse 등)
└── shared/       # 공통 유틸, UI 컴포넌트, API 클라이언트, MSW 핸들러
```

---

## 로컬 실행

```bash
cd Client
npm install
npm run dev        # 웹 (브라우저)
npm run android    # Android 앱
npm run ios        # iOS 앱
```

---

## 아키텍처

![architecture.png](doc/architecture.png)

---

## 팀원 & 역할

| 이름 | 역할 | 개발 내용 |
| --- | --- | --- |
| 민인애 | FE | LiveKit 화상·음성·텍스트 채팅 구현 (VideoRenderer, AudioVisualizer, ReactionPanel), 채팅 UI/UX, 피드백 기능, Three.js 최적화, 3D 씬 구현 |
| 박유진 | FE | 3D 씬 구현 (React Three Fiber), 소셜 로그인 · 회원가입, 매칭 상태 관리, 마이페이지 |
| 김준형 | Infra | MSA 인프라 구축 (Docker, Jenkins CI/CD, Nginx, Gateway, Eureka) |
| 박도아 | BE | 사용자 인증·회원 API (Spring Boot, MySQL), 소셜 로그인 서버 연동 |
| 차수홍 | BE | 매칭·채팅·편지 API (Spring Boot, MongoDB, Redis) |
| 홍찬우 | BE | AI 고민 유사도 매칭 서버 (FastAPI), 임베딩 모델 연동 |
