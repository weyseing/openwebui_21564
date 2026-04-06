# CLAUDE.md

## Project

Fork of [open-webui/open-webui](https://github.com/open-webui/open-webui) for bug fixes and contributions.

## Repo Structure

- `backend/` — Python (FastAPI) backend
- `src/` — Svelte frontend
- `progress/` — Fix tracking logs

## Dev Setup

```bash
# Frontend (requires Node 22)
export PATH="/opt/homebrew/opt/node@22/bin:$PATH"
npm install && npm run build

# Docker (Ollama + Open WebUI)
docker compose up -d

# Hot-swap frontend into running container (no rebuild)
docker cp ./build/. open-webui:/app/build/ && docker restart open-webui
```

## PR Guidelines (for upstream)

- Fork: `weyseing/open-webui`
- Target the `dev` branch, not `main`
- Title prefix: `fix:`, `feat:`, `refactor:`, etc.
- Include CLA from CONTRIBUTOR_LICENSE_AGREEMENT
- Request bot review: comment `@pr-validator-bot thorough review`
