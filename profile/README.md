<div align="center">
  <img src="./assets/ijiklog-logo.png" width="320" alt="이직로그" />

  <h3>이직한 사람들의 진짜 경험을 나누는 커리어 커뮤니티</h3>

  <p>
    면접부터 연봉 협상, 퇴사와 새로운 회사 적응까지<br />
    검색으로 찾기 어려운 이직 경험을 함께 나눕니다.
  </p>
</div>

## 이직로그

이직로그는 이직을 준비하거나 직접 경험한 사람들이 익명으로 고민과 경험을 공유하는 커뮤니티입니다.
학생 개발자들이 기획부터 디자인, 프론트엔드와 백엔드까지 직접 만들어가고 있습니다.

## 프로젝트

| 저장소 | 설명 |
| --- | --- |
| [ijiklog-web](https://github.com/ijiklog/ijiklog-web) | Next.js 기반 이직로그 웹 프론트엔드 |
| [ijiklog-api](https://github.com/ijiklog/ijiklog-api) | NestJS 기반 이직로그 백엔드 API |

```text
사용자
  └─ ijiklog-web (localhost:3000)
       └─ ijiklog-api (localhost:3001)
            └─ PostgreSQL
```

## 기술 스택

**Frontend** · Next.js 16 · React 19 · TypeScript · Tailwind CSS · Cloudflare

**Backend** · NestJS 11 · Fastify · Prisma 7 · PostgreSQL 17 · Swagger/OpenAPI

**Security** · Argon2id · HttpOnly database sessions

## 만들고 있는 기능

- 익명 기반 이직 경험 공유
- 게시글, 댓글, 공감과 북마크
- 검색, 정렬, 필터와 페이지네이션
- 알림, 신고, 차단과 관리자 운영 도구
- 이메일 인증과 안전한 세션 관리

## 개발 상태

현재 이직로그는 **로컬 MVP 개발 단계**입니다. 프론트엔드와 백엔드는 분리된 저장소로 관리하며,
기능 개발은 각 저장소의 `develop` 브랜치를 중심으로 진행합니다.

| 영역 | 현재 제공 범위 |
| --- | --- |
| 계정 | 이메일 회원가입·로그인, 세션, 프로필 |
| 커뮤니티 | 게시글, 댓글·답글, 공감, 북마크 |
| 탐색 | 검색, 정렬, 필터, 페이지네이션 |
| 운영 | 알림, 신고, 차단, 관리자 도구 |
| 개발 도구 | Swagger 문서, 테스트, 데이터베이스 시드 |

## 로컬에서 시작하기

Node.js 22 이상과 Docker가 필요합니다.

### 1. API 실행

```bash
git clone https://github.com/ijiklog/ijiklog-api.git
cd ijiklog-api
cp .env.example .env
docker compose up -d postgres
npm install
npm run prisma:generate
npm run db:migrate
npm run db:seed
npm run dev
```

- API: `http://localhost:3001`
- 상태 확인: `http://localhost:3001/health`
- Swagger: `http://localhost:3001/docs`

### 2. 웹 실행

```bash
git clone https://github.com/ijiklog/ijiklog-web.git
cd ijiklog-web
cp .env.example .env.local
npm install
npm run dev
```

웹은 `http://localhost:3000`에서 확인할 수 있습니다. `.env.local`의 API 주소는 다음과 같이 설정합니다.

```env
NEXT_PUBLIC_API_URL=http://localhost:3001
```

## 함께 개발하기

1. 작업은 `develop` 브랜치에서 새 기능 브랜치를 만들어 시작합니다.
2. 프론트엔드는 `npm test`와 `npm run build`를 확인합니다.
3. 백엔드는 `npm run lint`, `npm test`를 확인합니다.
4. 변경 목적과 검증 결과를 적어 Pull Request를 엽니다.

버그와 기능 제안은 관련 저장소의 Issues에서 남겨주세요.

---

<div align="center">
  <strong>모든 이직에는 저마다의 이유가 있으니까.</strong>
</div>
