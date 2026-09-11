# Voting Decentralisation Backend

Node.js + Express + MongoDB authentication API.

## Setup

```bash
npm install
cp .env.example .env
```

Set `MONGODB_URI` in `.env` to a local MongoDB instance (`mongodb://127.0.0.1:27017/voting_auth`) or an Atlas connection string. Replace `JWT_SECRET` with a long random string.

```bash
npm run dev
```

## Smoke tests

Register:

```bash
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"name":"Ada Lovelace","email":"ada@example.com","password":"secret12"}'
```

Login:

```bash
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"ada@example.com","password":"secret12"}'
```

Current user (use the token from register or login):

```bash
curl http://localhost:5000/api/auth/me \
  -H "Authorization: Bearer YOUR_JWT_HERE"
```

Health check:

```bash
curl http://localhost:5000/health
```
