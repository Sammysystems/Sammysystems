![AI Automation Engineer](./banner.svg)

**AI Automation Engineer** — I build agents, LLM integrations, and workflow automation that ship.

Uyo, Nigeria (WAT, UTC+1) · Remote worldwide

[Email](mailto:ubaniekan29@gmail.com) · [X](https://x.com/Psarmhye) · [GitHub](https://github.com/Sammysystems)

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black) ![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white) ![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-06B6D4?logo=tailwindcss&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?logo=vercel&logoColor=white)

---

## What I build

- **AI agents and LLM integrations** — model APIs, embeddings, structured outputs, fallbacks, and guardrails so the model cannot invent the things that matter.
- **Workflow automation** — event-driven pipelines, webhooks, SLA clocks, and handoffs across CRM, calendar, WhatsApp, and email.
- **Production discipline** — tests, CI, failure modes, capacity budgets, and degradation plans. Ship small, measure, then widen.

## Selected builds

Each one is a working system, not a pitch. The interesting part is never the happy path.

### [job-finder-bot](https://github.com/Sammysystems/job-finder-bot) — agentic job-search pipeline

Seven free job sources in, a small ranked shortlist out, then grounded outreach drafts and a human approval loop — running on a schedule with no laptop open.

**The hard part** — job feeds are noisy, and "AI outreach" usually invents things. The system had to keep only genuinely relevant roles and write emails grounded strictly in facts it could cite.

**How I solved it** — multi-source ingestion with normalization and fuzzy dedupe; a scored gate that rejects off-scope titles; deterministic, evidence-bound drafting (no model arithmetic anywhere near a claim); a Telegram approval loop; and GitHub Actions cron so it runs unattended.

`TypeScript · Node · VoltAgent · Zod · Telegram Bot API · GitHub Actions`

### [proofgate](https://github.com/Sammysystems/proofgate) — payment verification without a payment gateway

A Telegram bot reads the customer's bank-transfer receipt — photo, PDF, or screenshot — and returns **CONFIRMED** or **HOLD**.

**The hard part** — a receipt image is not a payment. The system had to make a trust decision from a picture and fail in the safe direction.

**How I solved it** — Gemini Vision extracts amount and reference; code verifies them against the order; a three-tier OCR fallback covers degraded images; and a deterministic gate the model cannot override decides the outcome. **21/21 tests**, with code and security reviews committed.

`Google Apps Script · Gemini Vision · Telegram`

### [dmi-concierge](https://github.com/Sammysystems/dmi-concierge) — embeddable booking concierge

A single `<script>` tag adds a concierge that answers from committed facts and captures real bookings.

**The hard part** — letting a model talk to customers while guaranteeing it never quotes a price that isn't on the rate card.

**How I solved it** — retrieval over committed facts, plus a code-level rate-card check that catches any off-card figure and corrects it before it reaches the customer. Bookings require a valid email, then mint a reference, notify both sides, and hand off to WhatsApp. An end-to-end booking suite, iframe-isolated, no database.

`React 19 · Vite · Gemini embeddings · OpenRouter/NVIDIA fallback · Resend`

### [lead-followup](https://github.com/Sammysystems/lead-followup) + [outbound-campaign](https://github.com/Sammysystems/outbound-campaign) — lead operations that don't lose the follow-up

**The hard part** — the first reply is easy. The leak is everything after it: the lead nobody chased, the deal that stalled, the sequence that quietly stopped.

**How I solved it** — every lead on a 4-hour SLA clock; the auto first-reply assembled from real property facts; stalled deals flagged by stage day-limit; event-driven enrollment through webhooks; and one drip email per scheduler tick, with a dashboard to manage sequences. Serverless plus Postgres, run on free tiers.

`Node · TypeScript · PostgreSQL (InsForge) · Vercel · Gmail SMTP · cron`

## How I work

- **Guardrails before autonomy.** When a wrong answer is expensive, the model proposes and code decides.
- **Model where it helps, code where correctness matters.** No model arithmetic in prices or payments.
- **Tests and CI are part of the build**, not a later phase.
- **Small ships.** One integration at a time, measured, then widened.

## Stack

- **Languages** — TypeScript, JavaScript, SQL
- **Frontend** — React 19, Vite, Tailwind 4
- **Backend & data** — Node.js, PostgreSQL, serverless on Vercel, REST, webhooks
- **AI & LLM** — Gemini (Vision, embeddings), OpenAI, Claude, OpenRouter/NVIDIA fallback, prompt design, structured outputs
- **Automation** — n8n, Make, Zapier concepts, cron scheduling, GitHub Actions
- **Integrations** — Telegram Bot API, WhatsApp Business API, Gmail SMTP, Resend, Google Drive/Sheets
- **Practice** — Vitest and e2e tests, CI, FMEA, capacity budgets, load testing, runbooks

## Build-in-public

These are reference builds I ship in public to pressure-test real operational problems — not client engagements. Where a number appears, it is a test count or a measured result from the repo, not a customer metric.

## Open to

Full-time remote roles in **AI automation, AI agents, LLM integration, and workflow automation**. Based in WAT (UTC+1), comfortable overlapping EU hours and US-East mornings.

---

[Email](mailto:ubaniekan29@gmail.com) · [X](https://x.com/Psarmhye) · [GitHub](https://github.com/Sammysystems)
