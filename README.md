## `> cat expertise.md`

| Domain | Proficiency | Details |
|---|---|---|
| RAG & LLM Systems | Intermediate | Built multiple RAG pipelines (ChromaDB, hybrid dense+BM25 retrieval, cross-encoder reranking, Groq, sentence-transformers) across coursework and personal projects |
| Document Intelligence / OCR | Intermediate | 3 months applying OCR pipelines (Tesseract, PaddleOCR) + semantic search on a Pfizer-partnered project via Extern |
| Full-Stack Web Development | Beginner-Intermediate | React, Node.js, Firebase, Twilio, Flask — built role-based, real-time, and REST API systems |
| Backend & Systems Programming | Intermediate | Java OOP coursework, Flask/SQLAlchemy debugging, Git history management (interactive rebase, conventional commits) |
| Fine-Tuning & NLP Classification | Beginner | Fine-tuned a DistilBERT classifier on scraped Reddit data, benchmarked against a zero-shot LLM baseline |
| Operations & Program Management | Advanced | 4+ years leading teams and programs — managed $900K+ in transactions, ran a community meal initiative from age 11 |

## `> ls featured-projects/ --detailed`

<details open>
<summary><b>Self-Correcting Legal Research System — Hybrid RAG</b></summary>
<br/>

Goes beyond basic RAG: combines dense retrieval (sentence-transformers + ChromaDB) with BM25 keyword search via Reciprocal Rank Fusion, then reranks the fused shortlist with a cross-encoder for precision. Benchmarked on CUAD (Contract Understanding Atticus Dataset).

| | |
|---|---|
| **Stack** | Python, sentence-transformers, ChromaDB, rank_bm25, cross-encoder (ms-marco-MiniLM-L-6-v2) |
| **Scale** | Hybrid dense+BM25 retrieval with RRF fusion, cross-encoder reranking on real legal contracts |
| **Impact** | Chunking, dense retrieval, BM25, RRF fusion, and cross-encoder reranking all working end-to-end; query routing, self-verification, and an ablation harness are next |

🔗 [github.com/rohitpeets/A-Self-Correcting-Legal-Research-System](https://github.com/rohitpeets/A-Self-Correcting-Legal-Research-System)

</details>

<details>
<summary><b>StudentBuddy — AI-Powered Professor Review RAG System</b></summary>
<br/>

RAG pipeline enabling McNeese students to query professor reviews in natural language instead of scattered Rate My Professors searches. Custom delimiter-based chunking and metadata-filtered retrieval, with strict prompt grounding via Groq to reduce hallucinated answers.

| | |
|---|---|
| **Stack** | Python, ChromaDB, sentence-transformers, Groq API |
| **Scale** | 141 professor reviews across 10 faculty members |
| **Impact** | Reduced hallucinated responses via strict prompt grounding; documented and fixed a real retrieval bug (ChromaDB defaulting to L2 distance instead of cosine) |

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
| **Impact** | End-to-end provenance detection system with confidence scoring |

🔗 [github.com/rohitpeets/provenance-guard](https://github.com/rohitpeets/provenance-guard)

</details>

<details>
<summary><b>TakeMeter — Fine-Tuned Reddit Comment Classifier</b></summary>
<br/>

Fine-tuned DistilBERT classifier for r/soccer comments across four labels (Analysis, Prediction, Reaction, Humor), benchmarked against a zero-shot Groq baseline on real collected Reddit data.

| | |
|---|---|
| **Stack** | Python, DistilBERT (fine-tuned), Reddit data collection |
| **Scale** | 288 manually labeled examples, 4-label classification |
| **Impact** | Improved Humor F1 by +0.26 and Prediction F1 by +0.13 over the zero-shot baseline, despite lower overall accuracy |

🔗 [github.com/rohitpeets/takemeter](https://github.com/rohitpeets/takemeter)

</details>

<details>
<summary><b>MixTape — Debugging an Existing Codebase</b></summary>
<br/>

Picked up an existing Flask/SQLAlchemy social music app with 5 known bugs in its service layer. Traced each from its route down to the failing service; found, fixed, and documented 3.

| | |
|---|---|
| **Stack** | Flask, SQLAlchemy, Python |
| **Scale** | 5 known service-layer bugs across streaks, search, playlists, feed, and notifications |
| **Impact** | Fixed and documented the listening-streak reset boundary, a duplicate-song search bug, and a missing last-song-in-playlist bug |

🔗 [github.com/rohitpeets/MixTape](https://github.com/rohitpeets/MixTape)

</details>

<details>
<summary><b>CineLog — Feature Contribution + Code Review Cycle</b></summary>
<br/>

Implemented a watchlist feature end-to-end (deduplication logic + tests) on an existing Flask/SQLAlchemy film-tracking API, then worked through a full code review cycle.

| | |
|---|---|
| **Stack** | Flask, SQLAlchemy, Python |
| **Scale** | End-to-end feature + 6 maintainer review comments addressed |
| **Impact** | Recovered from a silent rebase that had dropped commits by managing an interactive rebase back to a clean, conventional-commit linear history |

🔗 [github.com/rohitpeets/CineLogApi](https://github.com/rohitpeets/CineLogApi)

</details>

<details>
<summary><b>FitFindr — Agentic Thrift-Shopping Assistant</b></summary>
<br/>

A three-tool agentic pipeline that searches thrift listings, suggests outfits from a user's wardrobe, and generates social-media-style captions — with defensive fallbacks instead of hard failures on edge cases like an empty wardrobe.

| | |
|---|---|
| **Stack** | Python, Groq, Gradio |
| **Scale** | 3 chained tools (search, outfit suggestion, caption generation) |
| **Impact** | Explicit failure handling on every tool rather than unhandled exceptions |

🔗 [github.com/rohitpeets/myFitBuddy](https://github.com/rohitpeets/myFitBuddy)

</details>

<details>
<summary><b>Flappy Bird — Multiplayer 2D Game</b></summary>
<br/>

Rebuilt Flappy Bird in Java Swing with 60 FPS physics, pixel-accurate collision, and local multiplayer — solo, 2 weeks.

| | |
|---|---|
| **Stack** | Java Swing GUI, OOP, file I/O persistence |
| **Scale** | 4 game states, in-game shop + persistent balance system |
| **Impact** | Shipped every feature requested by a 10-person classmate survey |

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

**CodePath — Applied AI Engineering Pathway (AI201)** — Student · *May 2026 – August 2026 (in progress)*
- Accepted into CodePath's Applied AI Engineering program; shipped a new applied AI/software project roughly every week
- Built a hybrid RAG system (Legal Research Assistant) combining dense retrieval, BM25, Reciprocal Rank Fusion, and cross-encoder reranking, benchmarked on the CUAD legal contract dataset
- Built StudentBuddy, a RAG chatbot over 141 chunked professor reviews (ChromaDB, sentence-transformers, Groq) — evaluation write-up documents both what worked and a real retrieval failure
- Built Provenance Guard, a dual-signal AI-text-detection backend (LLM classification + stylometric heuristics) with confidence scoring, an appeals workflow, and full audit logging
- Fine-tuned a DistilBERT classifier (TakeMeter) on real scraped Reddit data to score discourse quality in r/soccer
- Debugged an existing Flask/SQLAlchemy codebase (MixTape) as a structured bug-hunt exercise — found, fixed, and documented 3 of 5 known service-layer bugs
- Contributed a feature to an existing codebase (CineLog) through a full code review cycle, including recovering a silent rebase via interactive rebase

![RAG](https://img.shields.io/badge/-RAG-00BFFF?style=flat-square&labelColor=0D1117) ![ChromaDB](https://img.shields.io/badge/-ChromaDB-00BFFF?style=flat-square&labelColor=0D1117) ![Groq](https://img.shields.io/badge/-Groq-00BFFF?style=flat-square&labelColor=0D1117) ![Debugging](https://img.shields.io/badge/-Debugging-00BFFF?style=flat-square&labelColor=0D1117) ![Git](https://img.shields.io/badge/-Git-00BFFF?style=flat-square&labelColor=0D1117)

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
    - Applied AI Engineering (CodePath AI201) - wrapping up in August 2026
    - Query routing and self-verification for RAG systems
  building:
    - A-Self-Correcting-Legal-Research-System (hybrid retrieval + reranking done; query routing, self-verification, guardrails, and an ablation harness next)
    - Full-stack Volunteer Management System (React/Node/Firebase/Twilio)
  exploring:
    - RAG evaluation and ablation methodology
    - OCR and document intelligence pipelines
    - Data structures & algorithms practice (NeetCode)
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
