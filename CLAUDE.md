# CLAUDE.md

## Project

This is a fork of [open-webui/open-webui](https://github.com/open-webui/open-webui) for debugging and fixing issue [#21564](https://github.com/open-webui/open-webui/issues/21564) — "Edit" and "Continue Response" don't work properly.

## Issue Summary

- **Edit**: Clicking edit on a message doesn't apply the changes
- **Continue Response**: Generates fresh output appended to existing content instead of resuming from where text ended
- Root cause: message loading logic drops existing assistant content when building the chat payload for the LLM

## Repo Structure

- `backend/` — Python (FastAPI) backend
- `src/` — Svelte frontend
- `dev` branch — active development branch (PRs should target this)

## Dev Setup

```bash
# Backend
cd backend
pip install -r requirements.txt
bash dev.sh

# Frontend
npm install
npm run dev
```

## Prior Fix Attempts

- PR #21695 — closed by bot (missing CLA, wrong branch, wrong title format)
- PR #21810 — closed by reviewers ("tested by three, not working")

## PR Guidelines (for upstream)

- Target the `dev` branch, not `main`
- Title must use prefix: `fix:`, `feat:`, `refactor:`, etc.
- Include CLA text from CONTRIBUTOR_LICENSE_AGREEMENT
- Test thoroughly before marking ready for review
