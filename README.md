## `> cat expertise.md`

| Domain | Proficiency | Details |
|---|---|---|
| RAG & LLM Systems | Intermediate-Advanced | Built hybrid (dense+BM25) retrieval with Reciprocal Rank Fusion and cross-encoder reranking from scratch across two separate systems; query routing and self-verification still in progress |
| Backend & API Development | Intermediate-Advanced | Multiple Flask/SQLAlchemy REST APIs (Provenance Guard, CineLog, Mixtape) — service-layer debugging, code review cycles, and Git history recovery |
| Document Intelligence / OCR | Intermediate | 3 months applying OCR pipelines (Tesseract, PaddleOCR) + semantic search on a Pfizer-partnered project via Extern |
| Full-Stack Web Development | Beginner-Intermediate | React, Node.js, Firebase, Twilio — built a handful of role-based, real-time systems |
| Systems Programming (Java) | Intermediate | OOP coursework and game architecture — file I/O persistence, access-control systems, real-time game loops |
| Fine-Tuning & NLP Classification | Beginner | One project fine-tuning a DistilBERT classifier on scraped Reddit data |
| Operations & Program Management | Advanced | 4+ years leading teams and programs — managed $900K+ in transactions, ran a community meal initiative from age 11 |

## `> ls featured-projects/ --detailed`

<details open>
<summary><b>Self-Correcting Legal Research System — Advanced RAG</b></summary>
<br/>

Self-correcting RAG system for legal contract Q&A over the CUAD dataset. Goes past "embed, search, generate" — combines dense + BM25 retrieval via Reciprocal Rank Fusion, reranks the fused shortlist with a cross-encoder, and (planned) adds a self-verification pass so the system can catch its own bad answers.

| Stage | Status |
|---|---|
| Chunking | ✅ Done |
| Dense retrieval (sentence-transformers + ChromaDB) | ✅ Done |
| BM25 keyword retrieval | ✅ Done |
| Hybrid retrieval (RRF fusion) | ✅ Done |
| Cross-encoder reranking | ✅ Done |
| Query routing | Code written, not yet wired into the main pipeline |
| Self-verification / guardrails / CUAD ablation harness | Planned |

**Impact:** Fixed a real RRF scoring bug where a missing rank was incorrectly treated as rank 0 (a high score) instead of a non-contribution — caught via boundary testing, not by accident. Also fixed a BM25 tokenization bug (unstripped punctuation silently breaking keyword matches) that changed the top-5 results.

🔗 [github.com/rohitpeets/A-Self-Correcting-Legal-Research-System](https://github.com/rohitpeets/A-Self-Correcting-Legal-Research-System)

</details>

<details>
<summary><b>CineLog — Community Film Tracking API</b></summary>
<br/>

A Flask/SQLAlchemy API for tracking watched films and building collections. Contributed the watchlist feature end-to-end on a shared codebase.

| | |
|---|---|
| **Stack** | Flask, SQLAlchemy, pytest |
| **Scale** | Deduplication logic + full test coverage for the watchlist feature |
| **Impact** | Addressed 6 maintainer review comments through a full code-review cycle; recovered from a silent rebase that dropped commits by managing an interactive rebase back to a clean, conventional-commit linear history |

🔗 [github.com/rohitpeets/CineLogApi](https://github.com/rohitpeets/CineLogApi)

</details>

<details>
<summary><b>StudentBuddy — AI-Powered Professor Review RAG System</b></summary>
<br/>

RAG pipeline enabling McNeese students to query professor reviews in natural language instead of scattered Rate My Professors searches. Custom delimiter-based chunking and metadata-filtered retrieval, with strict prompt grounding via Groq to reduce hallucinated answers.

| | |
|---|---|
| **Stack** | Python, ChromaDB, sentence-transformers, Groq API |
| **Scale** | 141 professor reviews across 10 faculty members |
| **Impact** | Debugged a real ChromaDB distance-metric bug (L2 → cosine) that was failing evaluation checkpoints; documented a specific retrieval failure case (a comparative query that missed one professor's reviews) with root-cause analysis |

🔗 [github.com/rohitpeets/StudentBuddy](https://github.com/rohitpeets/StudentBuddy)

</details>

<details>
<summary><b>Provenance Guard — AI Text Provenance Detection</b></summary>
<br/>

Flask-based system detecting AI-generated text using dual signals: LLM classification (Groq) and stylometric heuristics, with confidence scoring, an appeals workflow, rate limiting, and audit logging.

| | |
|---|---|
| **Stack** | Flask, Groq (LLM classification), stylometric heuristics |
| **Scale** | Dual-signal detection + appeals workflow + rate limiting + audit logging |
| **Impact** | Wrote 9 boundary-case tests against the exact scoring thresholds (0.39 vs 0.41, 0.59 vs 0.61, the disagreement override at 0.4) before trusting the implementation — all passing |

🔗 [github.com/rohitpeets/provenance-guard](https://github.com/rohitpeets/provenance-guard)

</details>

<details>
<summary><b>TakeMeter — Fine-Tuned Reddit Comment Classifier</b></summary>
<br/>

Fine-tuned DistilBERT classifier for r/soccer comments across four labels (Analysis, Prediction, Reaction, Humor), using real collected Reddit data.

| | |
|---|---|
| **Stack** | Python, DistilBERT (fine-tuned), Reddit data collection |
| **Scale** | 288 manually labeled examples, downsampled to 160 balanced for training |
| **Impact** | Improved Humor F1 by +0.26 and Prediction F1 by +0.13 over the zero-shot baseline, despite lower overall accuracy — fine-tuning learned community-specific patterns (sarcasm, memes) the baseline missed |

🔗 [github.com/rohitpeets/takemeter](https://github.com/rohitpeets/takemeter)

</details>

<details>
<summary><b>Mixtape — Debugging a Live Codebase</b></summary>
<br/>

Picked up an existing Flask/SQLAlchemy social music app with 5 known bugs in its service layer. Traced each from its route through to the failing service.

| | |
|---|---|
| **Stack** | Flask, SQLAlchemy, pytest |
| **Scale** | 3 of 5 bugs fixed and documented: listening-streak reset boundary, duplicate-song search, missing last-song-in-playlist |
| **Impact** | Remaining 2 (stale "friends listening now" feed, missing rating notifications) honestly tracked as open issues rather than glossed over |

🔗 [github.com/rohitpeets/MixTape](https://github.com/rohitpeets/MixTape)

</details>

<details>
<summary><b>Flappy Bird 2D — Multiplayer Game</b></summary>
<br/>

Flappy Bird rebuilt from scratch in Java Swing/AWT — no game engine, just JFrame, JPanel, and a manual game loop.

| | |
|---|---|
| **Stack** | Java Swing GUI, OOP, flat-file persistence |
| **Scale** | Local split-screen multiplayer, a 3-skin shop (500/2,000/10,000 coin tiers), persistent coin balance and save state |
| **Impact** | Score-to-currency economy funds the shop directly from gameplay skill — no separate grind loop |

🔗 [github.com/rohitpeets/flappy-bird-2d](https://github.com/rohitpeets/flappy-bird-2d)

</details>

<details>
<summary><b>Schedule Buddy</b></summary>
<br/>

A schedule planner that helps students plan effective class schedules without the headache.

| | |
|---|---|
| **Stack** | JavaScript |
| **Scale** | Personal student scheduling tool |
| **Impact** | Simplifies conflict-free schedule planning for students |

🔗 [github.com/rohitpeets/schedule-buddy](https://github.com/rohitpeets/schedule-buddy)

</details>

## `> git log --experience`

**Extern Externship — Pfizer Partner Project** — Extern (Software Engineering Extern) · *May 2026 – Present*
- Placed via Extern's externship program on a project team partnered with Pfizer
- Building Python pipelines to process pharmaceutical vendor files using Tesseract and PaddleOCR for automated document classification
- Developing a RAG retrieval system with LlamaIndex, deploying open-source LLMs (Mistral, Phi-2) for semantic document search
- Delivering end-to-end system evaluation benchmarking OCR accuracy and retrieval quality, including deployment recommendations and a demo UI

![Python](https://img.shields.io/badge/-Python-00BFFF?style=flat-square&labelColor=0D1117) ![RAG](https://img.shields.io/badge/-RAG-00BFFF?style=flat-square&labelColor=0D1117) ![OCR](https://img.shields.io/badge/-OCR-00BFFF?style=flat-square&labelColor=0D1117)

**CodePath — Applied AI Engineering Pathway (AI201)** — Student · *May 2026 – August 2026*
- Accepted into CodePath's Applied AI Engineering program; shipped a new applied AI/RAG project roughly every week
- Built StudentBuddy, a RAG chatbot over 141 chunked professor reviews (ChromaDB, sentence-transformers, Groq) — evaluation write-up documents both what worked and a real retrieval failure
- Built Provenance Guard, a dual-signal AI-text-detection backend with confidence scoring, an appeals workflow, and full audit logging, backed by 9 boundary-case tests
- Fine-tuned a DistilBERT classifier (TakeMeter) on real scraped Reddit data to score discourse quality in r/soccer
- Debugged an existing Flask/SQLAlchemy codebase (Mixtape), fixing and documenting 3 of 5 known bugs by tracing failures from routes into the service layer
- Completed a full open-source-style contribution cycle on CineLog: implemented the watchlist feature end-to-end, addressed 6 maintainer review comments, and recovered from a dropped-commit rebase via interactive rebase to a clean history

![RAG](https://img.shields.io/badge/-RAG-00BFFF?style=flat-square&labelColor=0D1117) ![ChromaDB](https://img.shields.io/badge/-ChromaDB-00BFFF?style=flat-square&labelColor=0D1117) ![Groq](https://img.shields.io/badge/-Groq-00BFFF?style=flat-square&labelColor=0D1117) ![Debugging](https://img.shields.io/badge/-Debugging-00BFFF?style=flat-square&labelColor=0D1117) ![Code-Review](https://img.shields.io/badge/-Code%20Review-00BFFF?style=flat-square&labelColor=0D1117)

**Operations Committee Member** — The Big Event @ McNeese State University · *Aug 2025 – May 2026*
- Coordinated venue setup and tool distribution/return across 20 job sites for a 176-volunteer community event
- Contributed to securing $4,700+ in sponsorships from Lowe's, Stine, and Tractor Supply
- Building a full-stack volunteer management system (React, Node.js, Firebase, Twilio) to solve gaps identified on event day

![React](https://img.shields.io/badge/-React-00BFFF?style=flat-square&labelColor=0D1117) ![Node.js](https://img.shields.io/badge/-Node.js-00BFFF?style=flat-square&labelColor=0D1117) ![Firebase](https://img.shields.io/badge/-Firebase-00BFFF?style=flat-square&labelColor=0D1117)

**Procurement Manager** — Teja Singh And Sons · *Jun 2025 – Jul 2025*
- Closed ~16 maize deals over 4 weeks generating ~$100K in revenue — negotiating price, quality grading, and payment terms
- Maintained a consistent 15.5% profit margin by adjusting bids daily based on live market signals
- Managed 6 supply chain intermediaries ensuring zero disruptions between suppliers and industrial buyers

![Negotiation](https://img.shields.io/badge/-Negotiation-00BFFF?style=flat-square&labelColor=0D1117) ![Operations](https://img.shields.io/badge/-Operations-00BFFF?style=flat-square&labelColor=0D1117)

**Lead Organizer** — Independent Community Meal Initiative · *Jun 2021 – Jun 2025*
- Planned and executed community feeding operations serving 1,000+ people across 7 stages, with zero institutional support
- Fundraised the full annual budget independently through personal networks, donations, and local business sponsorships
- Scaled the initiative from a volunteer role at age 11 to sole lead organizer over 4+ years

![Leadership](https://img.shields.io/badge/-Leadership-00BFFF?style=flat-square&labelColor=0D1117) ![Fundraising](https://img.shields.io/badge/-Fundraising-00BFFF?style=flat-square&labelColor=0D1117)

**Student Administrative Assistant** — McNeese State University, Int'l Student Services · *Jun 2024 – Aug 2024*
- Maintained confidential records for 400+ international students across a university system, physical files, and Excel databases
- Produced promotional materials for 2 ISA events, contributing to a 30% increase in attendance

![Data Entry](https://img.shields.io/badge/-Data%20Entry-00BFFF?style=flat-square&labelColor=0D1117) ![Admin-Support](https://img.shields.io/badge/-Admin%20Support-00BFFF?style=flat-square&labelColor=0D1117)

**Assistant Operations Manager** — Teja Singh And Sons · *Jan 2023 – Dec 2023*
- Managed $900K+ in farmer payments across government portals, catching and resolving discrepancies before they affected disbursements to 300+ farmers
- Built Excel tracking systems from scratch to monitor transaction volumes, payment status, and commodity flow across 300+ accounts
- Led a 25-person field team through peak harvest season, tracking 4,125 metric tonnes of grain intake with full quality and compliance oversight

![Team-Leadership](https://img.shields.io/badge/-Team%20Leadership-00BFFF?style=flat-square&labelColor=0D1117) ![Compliance](https://img.shields.io/badge/-Compliance-00BFFF?style=flat-square&labelColor=0D1117)

## `> cat achievements.md`

<div align="center">

| Achievement | Detail |
|---|---|
| CodePath Applied AI Engineering Pathway | Accepted into a competitive AI/ML engineering program |
| $4,700+ Raised in Sponsorships | Secured funding from Lowe's, Stine, and Tractor Supply for a 176-volunteer event |
| 1,000+ People Fed | Self-funded community meal initiative across 7 stages over 4+ years |
| $900K+ Managed | Farmer payment oversight across 300+ accounts with zero disbursement errors |
| 120,000+ Organic Views | Video marketing campaign — zero paid promotion |
| 30% Attendance Increase | Promotional materials produced for International Student Association events |

</div>

## `> cat education.md`

<div align="center">

![Education](https://img.shields.io/badge/McNeese%20State%20University-B.S.%20Computer%20Science%20%2727-00BFFF?style=for-the-badge&labelColor=0D1117)

</div>

## `> ./analytics --github`

<div align="center">

<img src="https://raw.githubusercontent.com/rohitpeets/rohitpeets/main/profile-assets/stats.svg" width="49%"/>
<img src="https://streak-stats.demolab.com/?user=rohitpeets&hide_border=true&background=0D1117&stroke=00BFFF&ring=00BFFF&fire=00BFFF&currStreakLabel=00BFFF&sideNums=00BFFF&sideLabels=E6EDF3&dates=E6EDF3&currStreakNum=E6EDF3" width="49%"/>

<img src="https://raw.githubusercontent.com/rohitpeets/rohitpeets/main/profile-assets/top-langs.svg" width="49%"/>

</div>

## `> activity-graph --timeline`

<div align="center">

![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=rohitpeets&bg_color=0D1117&color=00BFFF&line=00BFFF&point=00BFFF&hide_border=true&area=true&area_color=00BFFF)

</div>

## `> contribution-report --detailed`

<div align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=rohitpeets&theme=github_dark" width="100%"/>
<img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=rohitpeets&theme=github_dark" width="49%"/>
<img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=rohitpeets&theme=github_dark" width="49%"/>
<img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=rohitpeets&theme=github_dark" width="49%"/>
<img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=rohitpeets&theme=github_dark&utcOffset=-6" width="49%"/>

</div>

## `> ./snake-animation.sh`

<div align="center">

![Snake animation](https://raw.githubusercontent.com/rohitpeets/rohitpeets/output/github-contribution-grid-snake-dark.svg)

</div>

## `> cat current-focus.yaml`

```yaml
current_focus:
  learning:
    - Data Structures & Algorithms interview prep (NeetCode)
    - Query routing integration, self-verification, and ablation evaluation for RAG systems
  building:
    - A-Self-Correcting-Legal-Research-System — hybrid retrieval + reranking done, wiring in query routing and self-verification next
    - Full-stack Volunteer Management System (React/Node/Firebase/Twilio)
  exploring:
    - PathReview (forked) — an AI portfolio-review tool, studying its FastAPI + multi-agent architecture
    - RAG evaluation methods
  open_to:
    - Software Engineering Internships (Summer/Fall 2026, 2027)
    - AI/ML Engineering Internships
    - Full-Stack Engineering roles
```

## `> ping me`

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LINKEDIN-00BFFF?style=for-the-badge&logoColor=000000&labelColor=00BFFF)](https://www.linkedin.com/in/rohitpreet-singh-swe/)
[![Email](https://img.shields.io/badge/GMAIL-00BFFF?style=for-the-badge&logoColor=000000&labelColor=00BFFF)](mailto:rsingh5@mcneese.edu)
[![GitHub](https://img.shields.io/badge/GITHUB-00BFFF?style=for-the-badge&logoColor=000000&labelColor=00BFFF)](https://github.com/rohitpeets)

*I build things that work under real constraints.*

![Footer](https://capsule-render.vercel.app/api?type=wave&color=0:161B22,100:0D1117&height=120&section=footer)

</div>
