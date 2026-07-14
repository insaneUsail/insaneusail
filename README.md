<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:eeba2c,100:000000&height=220&section=header&text=Usail%20Khan&fontSize=55&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Full-Stack%20Developer%20%E2%80%94%20Real-Time%20Systems%20%2B%20AI%20Integrations&descAlignY=58&descSize=20" width="100%" />

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1000&color=eeba2c&center=true&vCenter=true&width=800&lines=Building+chat+apps%2C+canvases%2C+and+AI-integrated+backends;Currently+exploring+queues%2C+WebSockets%2C+and+voice+AI)](https://git.io/typing-svg)

<img src="https://komarev.com/ghpvc/?username=insaneUsail&label=Profile%20views&color=eeba2c&style=flat" alt="profile views" />

</div>

<br>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:eeba2c,100:000000&height=3&width=100%25" width="100%" />

## About Me

<table>
<tr>
<!-- Image Column -->
<td width="260" valign="top" align="center">
  <img src="assets/about.jpg" width="250" style="border-radius:10px; display:block; box-shadow: 0 4px 20px rgba(238,186,44,0.15);" alt="Usail Khan" />
</td>

<!-- Text Column with Custom Background Color -->
<td valign="top" bgcolor="#161b22" style="padding: 20px; border-radius: 10px;">

### Hi there! 👋
<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=eeba2c&width=450&lines=I+build+end-to-end+products.;Focusing+on+real-time+systems.;Wiring+LLMs+into+real+features." alt="Typing SVG" /></a>

I'm usually the same person writing the UI, the backend, the auth, and the deploy config. My repos lean toward two problems: **real-time sync** (chat, collaborative canvases) and **wiring LLMs into real features** (code review, data analysis, interview prep) rather than another chatbot wrapper.

Lately I've been focused on infrastructure — job queues, webhook security, rate limiting, WebSocket protocols — the parts that decide whether a project survives real traffic, not just the demo.

**Habits that show up across my repos:**
- 🛡️ **Verify inputs at the boundary** — webhook signatures, JWTs, Zod schemas
- ⛓️ **Fallback chains over failure** — prefer a degraded response over a broken one
- 🛠️ **Pragmatic tooling** — reach for managed tools first, drop to raw primitives for control

</td>
</tr>
</table>

## Tech Stack

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:eeba2c,100:000000&height=3&width=100%25" width="100%" />

## Tech Stack

<p align="left">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=js,ts,py,cpp,react,nextjs,redux,tailwind,vite,nodejs,express,fastapi,postgres,mongodb,prisma,firebase,supabase,redis,docker,vercel,git,github&perline=11" />
  </a>
</p>

| | |
|---|---|
| **Languages** | JavaScript · TypeScript · Python · C++ |
| **Frontend** | React · Next.js · Redux · Zustand · Tailwind · Vite · Radix UI |
| **Backend** | Node.js · Express · FastAPI · Socket.IO · `ws` · BullMQ |
| **Databases** | PostgreSQL · Prisma · MongoDB · Supabase · Firebase |
| **AI & ML** | Gemini · Groq (Llama 3.x) · OpenAI SDK · Vapi · pandas/numpy |
| **DevOps** | Docker · Turborepo · Redis · PM2 · Vercel |
| **Tools** | JWT · Cloudinary · Stripe · GitHub Webhooks API · Zod |

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:eeba2c,100:000000&height=3&width=100%25" width="100%" />

## Featured Projects

<table>
<tr>
<td width="120" valign="top"><img src="assets/review-codex.png" width="100" height="100" style="border-radius:10px;" /></td>
<td valign="top">

**🔍 [Review-Codex](https://github.com/insaneUsail/Review-Codex)** — AI GitHub App that reviews every PR with an LLM and can **block merges** via a failing Check Run on critical findings.
`TypeScript` `Express` `Redis` `BullMQ` `Groq` · HMAC-verified webhooks, rate limiting, token-aware diff chunking, idempotent job fan-in.

</td>
</tr>
</table>

<table>
<tr>
<td width="120" valign="top"><img src="assets/zketch.png" width="100" height="100" style="border-radius:10px;" /></td>
<td valign="top">

**🎨 [Zketch](https://github.com/insaneUsail/Zketch)** — real-time collaborative whiteboard with persistent room state that survives refreshes.
`Next.js` `ws` `Prisma` `PostgreSQL` `Turborepo` · hand-written WebSocket protocol with auth handshake, monorepo architecture.

</td>
</tr>
</table>

<table>
<tr>
<td width="120" valign="top"><img src="assets/ai-interview.png" width="100" height="100" style="border-radius:10px;" /></td>
<td valign="top">

**🎙️ [AI-interview-WebApp](https://github.com/insaneUsail/AI-interview-WebApp)** — voice-driven mock interview platform with an LLM generating questions and a live voice agent running the interview.
`Next.js` `FastAPI` `Groq` `Vapi` `Firebase` · polyglot TS + Python backend, resilient LLM output parsing.

</td>
</tr>
</table>

<table>
<tr>
<td width="120" valign="top"><img src="assets/insightai.png" width="100" height="100" style="border-radius:10px;" /></td>
<td valign="top">

**📊 [InsightAI](https://github.com/insaneUsail/InsightAI)** — upload a CSV, get automatic KPIs, charts, and a Gemini-generated executive summary.
`FastAPI` `pandas` `Gemini API` `React` · heuristic column detection, no hard-coded schema.

</td>
</tr>
</table>

<table>
<tr>
<td width="120" valign="top"><img src="assets/text-companion.png" width="100" height="100" style="border-radius:10px;" /></td>
<td valign="top">

**📖 [Text-Companion](https://github.com/insaneUsail/Text-Companion)** — AI reading companion; select text in a PDF, get an instant explanation.
`React` `Express` `Supabase` `Gemini` `Groq` · three-tier AI fallback chain (Gemini → Groq → offline default).

</td>
</tr>
</table>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:eeba2c,100:000000&height=3&width=100%25" width="100%" />

## Engineering Highlights

- **AI integration, more than one way** — Gemini, Groq, OpenAI SDK, and a voice agent (Vapi), including a multi-provider fallback chain and structured-JSON prompting
- **Real-time at different levels** — Socket.IO, a hand-rolled WebSocket protocol, and a job queue used as async "broadcast"
- **Backend infra** — Redis rate limiting, BullMQ fan-out/fan-in, HMAC webhook verification
- **Auth, repeated deliberately** — JWT middleware in nearly every backend, plus Firebase/Supabase auth
- **Full-stack commerce** — cart, Stripe checkout, order lifecycle, role-gated admin dashboard
- **Developer tooling** — Turborepo monorepo with shared config packages, Docker, PM2

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:eeba2c,100:000000&height=3&width=100%25" width="100%" />

## Current Interests

- Agentic / LLM-powered developer tooling
- Lower-level real-time systems (raw WebSockets over Socket.IO)
- Voice-driven AI interfaces

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:eeba2c,100:000000&height=3&width=100%25" width="100%" />

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
