# Task Flow

입고된 물품을 카드로 등록하고, 카드마다 지금 어떤 상태인지 한눈에 보는 물류관리 웹 앱. 현재는 기본 구조(M0)만 있고 카드 기능과 데이터베이스는 아직 구현하지 않았다. 설계 문서는 PRD.md, ARCHITECTURE.md, DECISIONS.md 를 본다.

## 구조

```
backend/   FastAPI (uv)
frontend/  React · Vite
```

## 실행

두 서버를 각각 다른 터미널에서 실행한다.

```
cd backend
uv run uvicorn main:app --port 8000
```

```
cd frontend
npm install
npm run dev
```

브라우저에서 http://localhost:5173 을 연다.
