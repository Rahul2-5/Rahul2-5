<!--
  Hey curious dev 👀 — you're reading the source.
  Welcome to Rahul's README. Glad you're here.
-->

<div align="center">

# Rahul Temkar

**Flutter × Spring Boot Developer** · building apps that work — even when the internet doesn't 📡

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=18&duration=2800&pause=1000&color=39FF14&center=true&vCenter=true&width=680&lines=root%40rahul%3A~%24+whoami;Flutter+%2B+Spring+Boot+%3D+%E2%9D%A4%EF%B8%8F;Compiling+offline-first+mobile+apps+%F0%9F%93%B1;Encrypting+backends+with+JWT+%2B+Spring+Security+%F0%9F%94%90;%5BOK%5D+Clean+Architecture+%7C+State+Management+%7C+AI+%F0%9F%A4%96;MCA+Student+%40+MET%2C+Mumbai+%F0%9F%87%AE%F0%9F%87%B3" alt="Typing SVG" />

<a href="mailto:rahultemkar61@gmail.com"><img src="https://img.shields.io/badge/Email-rahultemkar61%40gmail.com-0d1117?style=for-the-badge&logo=gmail&logoColor=39FF14" /></a>
<a href="https://www.linkedin.com/in/rahul-temkar-7a53952b3/"><img src="https://img.shields.io/badge/LinkedIn-Rahul_Temkar-0d1117?style=for-the-badge&logo=linkedin&logoColor=39FF14" /></a>
<a href="https://x.com/RahulT_25"><img src="https://img.shields.io/badge/X-@RahulT__25-0d1117?style=for-the-badge&logo=x&logoColor=39FF14" /></a>

<img src="https://komarev.com/ghpvc/?username=Rahul2-5&label=profile+views&color=39ff14&style=flat-square" />

</div>

---

```console
rahul@devbox:~$ neofetch
----------------------------------------------------------------
 User        : Rahul Temkar
 Location    : Maharashtra, India 🇮🇳
 Education   : MCA @ MET, Mumbai ('27, in progress) · BCA ('22–'25)
 Role        : Full Stack App Developer Intern @ GROBIIT
 Shell       : Flutter + Spring Boot
 Toolchain   : Dart · Java · Python · REST · JWT · Spring Security
 Building    : Offline-first healthcare app → Play Store
 Studying    : Clean Architecture patterns in Flutter
 Exploring   : AI in mobile · LLM pipelines · RAG
----------------------------------------------------------------
```

I build mobile apps end to end — **Flutter on the device, Spring Boot or FastAPI behind it** — with a bias toward three things:

- 📴 **Offline-first** — apps that keep working on bad networks and sync when the signal returns
- 🔐 **Secure by default** — stateless JWT auth and Spring Security–hardened APIs
- 🤖 **Useful AI** — LLM features that do real work instead of decorating the UI

---

## `$ ls ~/projects`

| | Project | What it does | Stack | Status |
|:-:|---|---|---|---|
| 🏥 | [**Offline-First Healthcare App**](#-offline-first-healthcare-app) | Patient records for ASHA workers in rural India, with zero connectivity | Flutter · SQLite · Spring Boot · JWT | MVP shipped → Play Store next |
| 🤖 | [**AutoAuditor**](https://github.com/Rahul2-5/AutoAuditor) | Upload a CSV of expenses, get a fraud-and-policy audit with LLM insights | Flutter · FastAPI · Pandas · Llama 3 | Active |
| 💰 | [**Budget Tracker**](https://github.com/Rahul2-5/Budget_Tracker) | Expenses, budgets and spending charts with PIN auth | Flutter · Firestore | Shipped |

---

### 🏥 Offline-First Healthcare App

![MVP shipped](https://img.shields.io/badge/MVP-shipped-39FF14?style=flat-square) ![Next](https://img.shields.io/badge/next-Play_Store-FFD700?style=flat-square) ![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-07405E?style=flat-square&logo=sqlite&logoColor=white)

> *"The internet is a privilege. Healthcare is not."*

**Problem:** ASHA workers in rural India record patient data where the network drops for hours.
**Solution:** every core flow runs on the device. Records live in local SQLite first and sync to a Spring Boot backend automatically when the network comes back.

<!-- 📸 ADD SCREENSHOTS HERE — the single biggest upgrade to this section.
<p align="center">
  <img src="assets/health-1.png" width="200" />
  <img src="assets/health-2.png" width="200" />
  <img src="assets/health-3.png" width="200" />
</p>
-->

```mermaid
flowchart LR
    W["ASHA worker"] --> APP["Flutter app"]
    APP <--> LOCAL[("SQLite<br/>local-first store")]
    APP -. "auto-sync on reconnect" .-> API["Spring Boot REST API<br/>JWT + Spring Security"]
    API --> SERVER[("Server database")]
```

<details>
<summary><b>Engineering details</b></summary>
<br/>

| Area | Implementation |
|---|---|
| 🔐 **Auth** | Stateless JWT — no server-side sessions |
| 📋 **Records** | Patient CRUD with local-first persistence |
| 📴 **Offline** | Every core flow works with zero internet |
| 🔄 **Sync** | Pushes queued local changes to the server on reconnect |
| 🖼️ **Media** | Image capture with a local cache |
| 🛡️ **API** | REST endpoints hardened with Spring Security |

</details>

<!-- TODO: add repo link once public → [![Source](https://img.shields.io/badge/Source_Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rahul2-5/REPO_NAME) -->

---

### 🤖 AutoAuditor — AI Expense Auditor

[![Source](https://img.shields.io/badge/Source_Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rahul2-5/AutoAuditor) ![Active](https://img.shields.io/badge/status-active-FFD700?style=flat-square) ![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

> *"Corporate expenses audited in seconds, not weeks."*

**Problem:** manual expense audits are slow and miss patterns spread across thousands of rows.
**Solution:** upload a CSV of corporate transactions and get back fraud signals, policy violations, analytics and plain-English insights from Llama 3 — through a four-phase pipeline.

<!-- 🎬 ADD A DEMO GIF HERE (CSV upload → dashboard, under 10 seconds)
<p align="center"><img src="assets/autoauditor-demo.gif" width="700" /></p>
-->

```mermaid
flowchart LR
    UI["Flutter UI"] -- "CSV upload" --> API["FastAPI"]
    API --> P1["1 · Data Prep"]
    P1 --> P2["2 · Rule Engine"]
    P2 --> P3["3 · AI Audit"]
    P3 --> P4["4 · LLM Insights<br/>Llama 3"]
    P4 --> OUT[("JSON dashboard")]
    OUT --> UI
```

<details>
<summary><b>Pipeline details</b></summary>
<br/>

| Phase | What happens |
|---|---|
| 📥 **Data Prep** | Dynamic schema detection, cleaning, behavioural tagging |
| 📏 **Rule Engine** | Budget-threshold, duplicate, frequency and missing-document violations |
| 🧠 **AI Audit** | Statistical anomaly detection, risk scoring, fraud-signal correlation |
| 💬 **LLM Insights** | Llama 3 writes natural-language summaries and cost-optimisation tips |
| 📊 **Dashboard** | Executive summary, spending trends, top spenders, category breakdown |

</details>

---

### 💰 Budget Tracker

[![Source](https://img.shields.io/badge/Source_Code-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Rahul2-5/Budget_Tracker) ![Shipped](https://img.shields.io/badge/status-shipped-39FF14?style=flat-square) ![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white) ![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)

> *Because "where did my money go?" shouldn't be a mystery.*

Track expenses, set budgets and visualise spending — with PIN auth and real-time Firestore sync.

<details>
<summary><b>More on GitHub</b></summary>
<br/>

- [**Encoder-Decoder-Project-DSA-**](https://github.com/Rahul2-5/Encoder-Decoder-Project-DSA-) — encoding and decoding built on core data-structures and algorithms concepts (Java)

</details>

---

## `$ cat stack.yml`

| Layer | Tools |
|---|---|
| **Mobile** | ![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white) ![Dart](https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white) |
| **Backend** | ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white) ![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black) |
| **AI / Data** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![Llama 3](https://img.shields.io/badge/Llama_3-0467DF?style=flat-square&logo=meta&logoColor=white) |
| **Databases** | ![SQLite](https://img.shields.io/badge/SQLite-07405E?style=flat-square&logo=sqlite&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=flat-square&logo=mongodb&logoColor=white) ![Firestore](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black) |
| **Deploy** | ![Render](https://img.shields.io/badge/Render-46E3B7?style=flat-square&logo=render&logoColor=black) ![Heroku](https://img.shields.io/badge/Heroku-430098?style=flat-square&logo=heroku&logoColor=white) |
| **Tooling** | ![Git](https://img.shields.io/badge/Git-F05033?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-00C4CC?style=flat-square&logo=canva&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white) |

---

## `$ git log --oneline --reverse`

```text
 2022 ──────────── 2023 ──────────── 2024 ──────────── 2025 ──────────── now ──▶
  │                 │                 │                 │                 │
 [BCA]          [First repos]    [Real projects]    [MCA + AI]        [Intern]
 Java &         Git, Java,       Offline health     AutoAuditor:      Full Stack App
 fundamentals   REST APIs        app · Budget       Flutter + LLM     Developer
                                 Tracker            full stack        @ GROBIIT
```

**Next up**

- [x] Ship the offline-first healthcare app MVP
- [x] Build AutoAuditor — AI expense-audit pipeline
- [ ] Play Store launch for the healthcare app
- [ ] RAG-based audit chat for AutoAuditor
- [ ] First open-source contributions

---

## `$ gh stats`

<p align="center">
  <img height="165" src="https://github-readme-stats.shion.dev/api?username=Rahul2-5&theme=chartreuse-dark&hide_border=false&include_all_commits=true&count_private=true" />
  <img height="165" src="https://github-readme-stats.shion.dev/api/top-langs/?username=Rahul2-5&theme=chartreuse-dark&hide_border=false&include_all_commits=true&count_private=true&layout=compact" />
</p>
<p align="center">
  <img src="https://streak-stats.demolab.com/?user=Rahul2-5&theme=chartreuse-dark&hide_border=false" />
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Rahul2-5/Rahul2-5/output/github-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Rahul2-5/Rahul2-5/output/github-snake.svg" />
    <img alt="Rahul's contribution snake" src="https://raw.githubusercontent.com/Rahul2-5/Rahul2-5/output/github-snake.svg" />
  </picture>
</p>

---

```console
rahul@devbox:~$ exit
[connection closed] — thanks for visiting. Got an idea or a role? My inbox is open. 🚀
```
