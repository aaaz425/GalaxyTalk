# 은하수다 — Client

은하수다 프론트엔드 애플리케이션입니다. React 19 + Vite + TypeScript 기반으로 구성되어 있으며, Capacitor를 통해 Android/iOS 앱으로도 빌드할 수 있습니다.

---

## 시작하기

```bash
npm install
npm run dev
```

---

## 스크립트

| 명령어 | 설명 |
| --- | --- |
| `npm run dev` | 개발 서버 실행 |
| `npm run build` | 프로덕션 빌드 |
| `npm run lint` | ESLint 실행 |
| `npm run android` | Android 앱 빌드 및 실행 |
| `npm run ios` | iOS 앱 빌드 및 실행 |

---

## 프로젝트 구조

Feature-Sliced Design(FSD) 아키텍처를 기반으로 구성했습니다.

```
src/
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

## 주요 기술 스택

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

---

## 환경 변수

`.env` 파일을 루트에 생성하고 아래 항목을 설정합니다.

```
VITE_API_URL=
VITE_LIVEKIT_URL=
VITE_KAKAO_CLIENT_ID=
VITE_NAVER_CLIENT_ID=
```
