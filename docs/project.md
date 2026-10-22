# project.md

## What
**Paisa Wrapped** (working name): upload your UPI statement, get a swipeable, shareable "year in payments" story. All processing happens in the browser. Nothing is uploaded.

## Problem
UPI apps show a transaction list but no insight. People are curious where their money went, but statements are messy PDFs. A Wrapped-style story makes it fun and shareable.

## Users
Indian 18-35 UPI users who like Spotify Wrapped style recaps and care about privacy.

## MVP scope
Upload PhonePe PDF statement -> parse -> categorize -> ~8 story cards -> download share image (1080x1920, domain watermark).

## Non-goals (for now)
Accounts, backend, bank linking, SMS access, budgeting/advice, AI/LLM calls, multi-language.
Parking lot: GPay, Paytm, generic CSV, friend compare, Hinglish copy toggle.

## Stack (verify versions at install time)
- Next.js (App Router, static export) + TypeScript (strict) + Tailwind
- pdfjs-dist inside a Web Worker for PDF text extraction
- Vitest for unit tests on pure logic
- html-to-image for share cards, Motion for animation
- Hosting: Cloudflare Pages (or Vercel). Analytics: Cloudflare Web Analytics
- Playwright MCP for UI testing, GitHub MCP for commits/PRs

## Privacy principles
- No network request ever carries user data.
- Raw transactions live in memory only. Don't store them in localStorage.
- Never commit real statements. Use generated fake data. Add statement files to .gitignore.
- Plain-language privacy page.

## Legal/brand
Not affiliated with PhonePe, Google Pay or any bank. No logos. "Not financial advice."

## Coding rules (Day 1 turns these into the Antigravity rules file)
- Pure functions in /lib (parse, categorize, stats), each with tests.
- Money as integer paise, never floats.
- Small files, one responsibility. No new dependency without asking me why.
- After each step: run tests, lint, and build.
- Commit after every working step.

## Monetization (later)
Tip link (UPI/Ko-fi), optional premium card themes. Not before launch.

## Success
Deployed on own domain, Lighthouse 90+, parser works on real statements, share cards look great, indexed for 3+ search intents.

## Risks
PDF layouts vary and change. Mitigation: test on my own real statement, keep parser modular, show friendly errors, add CSV fallback.
