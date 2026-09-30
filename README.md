# Fluent180 — AI English & Career Coach

A 180-day adaptive English coach for adult learners (A2–B1 → professional English and interview readiness).
It runs entirely in the browser: one `index.html`, no server, no build step.

## Features
- Profile setup and a placement test (grammar, vocabulary, reading, listening, writing, speaking)
- 180-day plan in six phases, with a weekly review every 7th day and a monthly assessment every 30th
- Daily tasks: vocabulary, grammar, listening, speaking, writing, AI conversation
- AI scoring with a required rewrite when a writing or speaking score is under 85
- Learning decision engine: **Advance / Practice more / Repeat / Change method**, decided per skill
- Personal error bank and spaced-repetition review (1 → 2 → 4 → 7 → 14 → 30 → 60 learning days)
- Topic mastery across four contexts (recognise, practise, write, speak)
- Progress charts, streaks, achievements, weekly reports
- Interview simulator and Work English tools (professional rewrites, emails, reports, roleplays)

## Run it
**Option A — on your computer:** download `index.html` and double-click it (Chrome or Edge recommended).

**Option B — as a website with GitHub Pages (recommended; works on phones):**
1. Create a new repository on GitHub, e.g. `fluent180`.
2. Upload all files from this folder (keep `.nojekyll`).
3. Go to **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After about a minute the site is live at `https://<your-username>.github.io/fluent180/`.
5. On a phone, open that link and use **Add to Home Screen** to install it like an app.

## AI coaching (API key)
AI feedback uses Anthropic's Claude API. Each learner pastes an API key in **Settings → AI coaching**
(get one at https://console.anthropic.com).

- The key is stored **only in the learner's browser** (localStorage) and sent only to `api.anthropic.com`.
- **Never put an API key in this repository** — the repo is public on the free GitHub plan.
- Set a monthly spending limit in the Anthropic console.
- Models used: `claude-sonnet-5-5` for lessons and scoring, `claude-haiku-4-5-20251001` for quick replies.
  Change them in `aiDirect()` inside `index.html` if needed.

Without a key, the placement grammar/vocabulary test, word review, error bank and progress pages still work.

## Data and privacy
- Progress is saved in the browser (localStorage) on the device where it is used. Use the same browser each day.
- **Settings → Download my data** exports a JSON backup.
- Clearing browser data deletes progress, so keep backups.

## Honest limits
- Speaking uses the browser's speech recognition (best in Chrome/Edge). If the microphone is unavailable, speaking is typed and fluency is not scored.
- Pronunciation is shown as "Not measured" (needs a pronunciation-scoring service).
- CEFR levels are AI estimates, not an official certificate.
- Coach/partner view needs a shared backend; in this static version it is not available.

## Roadmap
See [`docs/BUILD_SPECIFICATION.md`](docs/BUILD_SPECIFICATION.md) for the full production specification
(Next.js + PostgreSQL + speech-to-text + pronunciation scoring + coach dashboard).
