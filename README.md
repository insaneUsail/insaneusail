<div align="center">

# Hey, I'm Usail 👋

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1000&color=5BCDEC&center=true&vCenter=true&width=600&lines=Full-Stack+Developer;Real-Time+Systems+%2B+AI+Integrations;Currently+building+with+LLMs+and+WebSockets)](https://git.io/typing-svg)

<img src="https://komarev.com/ghpvc/?username=insaneUsail&label=Profile%20views&color=5BCDEC&style=flat" alt="profile views" />

</div>

<br>

## About Me

I build **end-to-end products** — usually the same person writing the React UI, the Express/FastAPI backend, the auth middleware, and the deploy config. My repos lean toward two recurring problems: **real-time synchronization** (chat, collaborative canvases) and **wiring LLMs into real product features** (data analysis, code review, interview prep, reading assistance) rather than another chatbot wrapper.

My current focus is backend and infrastructure — job queues, webhook security, rate limiting, WebSocket protocols. The parts of a project that don't show up in a demo GIF but decide whether it survives production traffic. My most recent project, an AI PR-review GitHub App, is the clearest example: less "call an API and show the result," more "verify the request, queue the work, handle the failure, gate the outcome."

**A few habits that show up across my repos, for better or worse:**
- Prefer a degraded response over a broken one — several AI integrations have explicit fallback chains instead of a single point of failure.
- Verify inputs at the boundary (webhook signatures, JWTs, Zod schemas) rather than trusting the caller.
- Reach for the managed tool (Socket.IO, an ORM) when it fits, and drop to the lower-level primitive (raw `ws`, a hand-written protocol) when I want more control.
- Started on plain JS/CRUD apps and moved toward TypeScript, queues, and AI-integrated backends as the projects got more recent — still learning in public.

<br>

## Tech Stack

<p align="left">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=js,ts,py,cpp,react,nextjs,redux,tailwind,vite,nodejs,express,fastapi,postgres,mongodb,prisma,firebase,supabase,redis,docker,vercel,git,github&perline=11" />
  </a>
</p>

| | |
|---|---|
| **Languages** | JavaScript · TypeScript · Python · C++ |
| **Frontend** | React · Next.js · Redux · Zustand · Tailwind CSS · Vite · Radix UI · Recharts |
| **Backend** | Node.js · Express · FastAPI · Socket.IO · WebSocket (`ws`) · BullMQ |
| **Databases** | PostgreSQL · Prisma · MongoDB / Mongoose · Supabase · Firebase Firestore |
| **AI & ML** | Gemini API · Groq (Llama 3.x) · OpenAI SDK · Vapi (voice AI) · pandas / numpy |
| **DevOps** | Docker · Turborepo · Redis · PM2 · Vercel · Heroku |
| **Tools** | JWT · Cloudinary · Stripe · GitHub Apps/Webhooks API · Zod · ESLint |

<br>

## Featured Projects

### 🔍 [Review-Codex](https://github.com/insaneUsail/Review-Codex) — AI-powered PR review GitHub App
An installable GitHub App that reviews every pull request with an LLM, posts inline comments, and can **fail a required Check Run** on critical findings so a bad PR can't be merged.

- **Problem solved:** manual review is slow and inconsistent, especially without a dedicated reviewer rotation.
- **Engineering challenges:** HMAC-SHA256 webhook verification with a timing-safe comparison to stop forged events; Redis-backed rate limiting per repo; a diff chunker that respects LLM token budgets *without* splitting a file's hunks across two calls, so the model always sees a file's full context; a BullMQ fan-out/fan-in pipeline with idempotent completion counters; a "fail open" rule so one broken LLM call doesn't kill the whole review job.
- **Tech:** TypeScript · Express · Redis · BullMQ · Groq (Llama 3.3 70B) · Octokit · GitHub Checks API
- **Why it stands out:** the only project here shipped as an actual installable product, not a local demo — the code reads like it was written by someone who's thought about what happens when things go wrong, not just the happy path.

### 🎨 [Zketch](https://github.com/insaneUsail/Zketch) — real-time collaborative whiteboard
A multiplayer drawing canvas where strokes, cursors, and chat sync live across a room, with state persisted so a drawing survives a refresh or dropped connection.

- **Problem solved:** synchronous canvas collaboration with state that outlives the WebSocket connection instead of vanishing on disconnect.
- **Engineering challenges:** a hand-written WebSocket protocol (not Socket.IO) with an explicit auth handshake and timeout before a socket is trusted; in-memory room/user maps for multiplexing sockets into rooms; a persist-on-stroke/replay-on-join reconciliation strategy backed by Prisma; a Turborepo monorepo with shared UI, ESLint, and TypeScript config packages.
- **Tech:** Next.js · TypeScript · `ws` · Prisma · PostgreSQL · Turborepo · Zustand · Radix UI · Docker
- **Why it stands out:** building the real-time layer on raw WebSockets instead of a library shows comfort with the protocol itself, not just an abstraction over it.

### 🎙️ [AI-interview-WebApp](https://github.com/insaneUsail/AI-interview-WebApp) — voice-driven mock interview platform
Generates role- and stack-specific interview questions with an LLM, then runs the interview through a live conversational voice agent.

- **Problem solved:** interview practice is hard to do alone; this turns a static question list into a spoken, back-and-forth mock interview.
- **Engineering challenges:** a polyglot setup — TypeScript/Next.js frontend talking to a separate Python/FastAPI backend; normalizing Vapi's different tool-call payload shapes into one format; defensively extracting a JSON array from LLM output that doesn't always come back clean; Firebase Firestore as the data layer alongside Firebase Auth.
- **Tech:** Next.js · TypeScript · FastAPI · Python · Groq · Vapi · Firebase · Zod · React Hook Form
- **Why it stands out:** most "AI chat" side projects stop at text — this one integrates a real voice agent and coordinates two backend languages for one product.

### 📊 [InsightAI](https://github.com/insaneUsail/InsightAI) — AI-assisted data analytics dashboard
Upload a CSV, get automatic KPI extraction, charts, and a Gemini-generated executive summary you can ask follow-up questions about.

- **Problem solved:** turning an arbitrary business spreadsheet into KPIs and a narrative summary without manual wrangling per dataset.
- **Engineering challenges:** a column-detection heuristic that guesses which column is revenue/profit/region/date from naming patterns instead of assuming a fixed schema; safe fallback math when an expected column (like profit) is missing; a FastAPI service layer using dependency overrides so services are shared singletons; parsing structured sections back out of free-form LLM prose.
- **Tech:** FastAPI · pandas · numpy · Gemini API · React · Recharts · Tailwind CSS
- **Why it stands out:** the column-detection logic means it wasn't hard-coded against one sample CSV — a small but telling sign of building for general input, not a demo.

### 📖 [Text-Companion](https://github.com/insaneUsail/Text-Companion) — AI reading companion for PDFs
Read a PDF in-browser, select any word or passage, and get an instant AI explanation, example, and synonyms — library synced to the cloud.

- **Problem solved:** dense reading material usually means switching tabs to look something up; this keeps the explanation inline.
- **Engineering challenges:** a **three-tier fallback chain** for the AI feature (Gemini → Groq → a static offline response) so it degrades instead of breaking when a provider is down or rate-limited; in-browser PDF rendering and text selection with `react-pdf`/`pdfjs-dist`; Supabase for file storage alongside Firebase for auth.
- **Tech:** React · Vite · Express · Supabase · Firebase Admin SDK · Gemini SDK · Groq (OpenAI-compatible SDK) · `pdf-parse`
- **Why it stands out:** the fallback chain is a genuinely pragmatic resilience pattern — most side projects call one API and hope it stays up.

<br>

## Engineering Highlights

**AI integration, more than one way.** Gemini, Groq-hosted Llama models, the OpenAI SDK, and a voice agent (Vapi) across different projects — including a multi-provider fallback chain (Text-Companion) and structured-JSON prompting for downstream parsing (Review-Codex, AI-interview-WebApp, InsightAI).

**Real-time communication at different levels of abstraction.** Socket.IO for a straightforward presence/chat app, a hand-rolled WebSocket protocol with an auth handshake for a collaborative canvas, and a job queue (BullMQ) used as a batched, async form of "broadcast" for PR reviews.

**Backend architecture and job processing.** Redis-backed rate limiting, BullMQ fan-out/fan-in with idempotent counters, and webhook signature verification in Review-Codex — the most infrastructure-heavy code in the portfolio.

**Authentication, repeated deliberately.** JWT auth middleware in nearly every backend (a consistent `protectRoute`/`isAuthenticatedUser` pattern), plus Firebase Auth and Supabase auth in the AI-facing apps.

**Full-stack commerce.** Cart, checkout, Stripe payments, order lifecycle, and a role-gated admin dashboard in an earlier e-commerce project — a useful counterweight to the AI-heavy recent work.

**Developer tooling.** A Turborepo monorepo with shared ESLint/Tailwind/TypeScript config packages (Zketch), Docker, and PM2 process management.

**Fundamentals.** A handful of smaller repos (a currency converter, a weather app, a browser game, DSA practice in C++) sit earlier in the commit history — the on-ramp before the full-stack and AI-integrated work above.

<br>

## Current Interests

- **Agentic / LLM-powered developer tooling** — automated code review is a step past "chatbot," and I want to keep building in this direction.
- **Lower-level real-time systems** — writing WebSocket handling myself instead of only relying on Socket.IO.
- **Voice-driven AI interfaces** — the interview app is my first project past text-based chat.

<br>

## GitHub Stats

<table>
  <tr>
    <td><img src="https://github-readme-stats.vercel.app/api?username=insaneUsail&show_icons=true&theme=synthwave&hide_border=true" /></td>
    <td><img src="https://github-readme-streak-stats.herokuapp.com/?user=insaneUsail&theme=synthwave&hide_border=true" /></td>
  </tr>
</table>

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=insaneUsail&layout=compact&theme=synthwave&hide_border=true)



![snake gif](https://github.com/insaneUsail/insaneUsail/blob/output/github-contribution-grid-snake.svg)


<br>

## Connect

<p align="left">
  <a href="https://linkedin.com/in/your-handle"><img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" /></a>
  <a href="https://your-portfolio-url.com"><img src="https://img.shields.io/badge/Portfolio-000000?style=flat&logo=About.me&logoColor=white" /></a>
  <a href="mailto:your.email@example.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" /></a>
</p>
