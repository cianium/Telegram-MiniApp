<div align="center">

# Telegram Downloader Mini App

**TgDownBot — an experimental Telegram Mini App and bot MVP**

**FastAPI · Python · React · TypeScript · Telegram Bot API**

![Status](https://img.shields.io/badge/Status-Experimental%20MVP-F59E0B)
![Distribution](https://img.shields.io/badge/Distribution-Source%20ZIP-64748B)
![Release](https://img.shields.io/badge/GitHub%20Release-Not%20Published-64748B)

[Download the source archive](TgDownBot-MVP-v1.1-Music-Search.zip) · [GitHub repository](https://github.com/cianium/Telegram-MiniApp)

</div>

> **Project status:** A prototype source package, **not a verified or deployed production service**. The repository root currently contains a README and **one ZIP archive**, not an extracted application source tree. The ZIP has been inspected for its file inventory and included development documentation; the code has **not been independently executed, security-audited, or deployed** as part of this documentation review.

## Overview

**TgDownBot** explores a Telegram bot and mobile-first Mini App interface for handling permitted media files, with a separate Python API, task worker and browser frontend. The project also contains an experimental music-search design that distinguishes recording metadata from artist-authorized downloadable tracks.

**Use only media you own or have permission to download and distribute.** The project is not a service for bypassing access controls, DRM or copyright restrictions. Platform compatibility and availability are not guaranteed.

## What's inside the ZIP?

The archive **`TgDownBot-MVP-v1.1-Music-Search.zip`** contains **37 entries**, under a top-level `TgDownBot/` directory.

| Part | Paths inside the archive | Purpose |
| :-- | :-- | :-- |
| **Frontend** | `frontend/src/`, `frontend/package.json` | React / TypeScript Mini App with Vite |
| **Backend API** | `backend/app/` | FastAPI routes, authentication, state and metadata processing |
| **Telegram bot** | `backend/bot.py` | Telegram bot entry point |
| **Worker** | `backend/worker/` | Background jobs and delivery architecture |
| **Automated tests** | `backend/tests/` | API, security and music-related tests |
| **Local/deployment configuration** | `.env.example`, `compose.yaml`, `backend/Dockerfile` | Configuration template and container scaffold |
| **Project documentation** | `docs/ARCHITECTURE.md`, `MVP_SCOPE.md`, `MUSIC_SEARCH.md`, `TEST_REPORT.md` | Design, boundaries, feature scope and test claims |

The ZIP contains source files, not just screenshots or compiled binaries. However, GitHub cannot conveniently display or review those files individually until they are extracted and committed to the repository.

## Functionality described by the packaged source

- **Mini App UI:** mobile-oriented frontend with link entry, preview, status/history interface and Persian/English presentation.
- **Telegram bot:** command handler with `/start` and `/help`, plus optional Mini App launch configuration.
- **Backend:** Telegram signed authentication, short-lived sessions, user-scoped jobs and administrative status endpoints.
- **Background processing:** development-mode task execution and Redis/RQ-based worker scaffolding.
- **Music discovery:** metadata search through MusicBrainz and an artist-authorized download flow through Jamendo, subject to provider availability and licensing conditions.
- **Local demo:** simulated metadata and harmless test output, without real media delivery.

These are **code/documentation claims**, not independent confirmation that all workflows succeed on current platforms.

## Local development — simulated demo only

According to the packaged documentation, the intended local development environment uses **Python 3.12+**, **Node.js 22+** and, for some workflows, FFmpeg. Do not put API tokens or real credentials in Git.

Extract the archive in a disposable development directory:

```bash
unzip TgDownBot-MVP-v1.1-Music-Search.zip
cd TgDownBot
cp .env.example .env
```

The included example configuration is intended to start in **development and simulated-download mode**. Review its settings before running any service.

For the backend, the packaged guide specifies installing `backend/requirements-dev.txt` and running the FastAPI application locally. The frontend uses the usual Vite development commands from `frontend/`:

```bash
cd frontend
npm install
npm run dev
```

This is a **documentation example, not an executed installation test**. Consult the more complete `TgDownBot/README.md` inside the ZIP for backend setup and platform-specific prerequisites.

## Tests and verification status

The ZIP includes **`docs/TEST_REPORT.md` dated 2026-10-17**, which reports:

| Check | Reported status |
| :-- | :-- |
| Python syntax compilation | Passed in its original development environment |
| Backend test suite | **29 tests reported as passed** |
| Frontend TypeScript syntax transpilation | Reported as syntax-only check |
| Complete `npm run build` | **Not verified** |
| Real provider queries, conversions and Telegram delivery | **Not verified** |
| Redis/PostgreSQL/Docker end-to-end flow | **Not verified** |
| Production security and load testing | **Not completed** |

**No tests have been rerun during this repository-documentation update.** The reports are useful historical evidence but are not current CI results.

## Key security and deployment limitations

Before public use, independent verification is required for:

- Telegram initialization-data validation, user authentication and authorization.
- Input/URL validation and SSRF/network isolation for any external media processing.
- Robust concurrent job quotas, storage cleanup, worker limits and recovery after errors.
- Safe management of bot tokens, application secrets and user data.
- End-to-end functional tests with permitted content and current provider APIs.
- TLS/HTTPS configuration, observability and backup/restore procedures.

The packaged `docs/ARCHITECTURE.md` explicitly describes unresolved production-hardening requirements. Do **not** expose development/demo authentication to public users or assume a successful Python test suite is production certification.

## Repository and release status

- **Default branch:** `main`
- **Distribution today:** source ZIP checked into the repository root
- **ZIP filename:** `TgDownBot-MVP-v1.1-Music-Search.zip` — a **package label**, not a GitHub Release tag
- **GitHub Releases:** none
- **Git version tags:** none
- **GitHub Actions CI:** none detected

### Before publishing a versioned release

1. Extract source into separately reviewable `backend/`, `frontend/` and `docs/` folders.
2. Add a clear `.gitignore`, safe `.env.example` and contributor-facing setup instructions at repository root.
3. Pin or lock tested dependencies, implement automated tests and verify the frontend build.
4. Review external-provider policies, permitted content handling and runtime security boundaries.
5. Tag the reviewed source commit, include changes and limitations in release notes, and attach the ZIP as a proper GitHub Release asset.

**No stable `v1.0.0` or `v1.1.0` release should be claimed solely from the ZIP filename.**

## License

No project-wide `LICENSE` was found in the repository root or the inspected ZIP manifest. Public availability does not grant permission to redistribute or reuse the code or any third-party assets. Contact the maintainer for licensing terms.

---

<div align="center">

**TgDownBot — a packaged Telegram Mini App proof of concept, pending reproducible build and security review.**

</div>
