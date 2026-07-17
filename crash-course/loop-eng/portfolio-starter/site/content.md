# content.md — words for the page

This file is copy, organized by the section it belongs in. Section ids match
`spec.md` M1 exactly: `hero`, `about`, `projects`, `skills`, `contact`.

Per `design.md`, the page is a multi-agent trace: five numbered steps running
down the page (received → initialized → tool-calls → tools → human-in-the-loop),
with `contact` marked as the one step waiting on a person. Each section below
carries its step number and label — use them as the visible marker for that
step (e.g. in a `<span>` or small heading before the section's main content),
not as the section's only content.

Nav labels (for the sticky nav / thread, five links, in this order):
`Received` → `#hero`, `Initialized` → `#about`, `Tool-Calls` → `#projects`,
`Tools` → `#skills`, `Awaiting Input` → `#contact`.

---

## `#hero` — Step 00 · RECEIVED

Step marker: `00 — RECEIVED`

`<h1>`: **Rubaiya Asif**

Role line (optional small text near the h1, not required by M11 but supports
the trace framing): `Python & Agentic AI Developer`

Required `<p>` (≥4 words — this is the "task received" line, no separate
summary paragraph):

> Task received: build autonomous, tool-calling AI agents — with a human always in the loop.

---

## `#about` — Step 01 · INITIALIZED

Step marker: `01 — INITIALIZED`

Body copy (≥40 words):

> Initialized: more than two years into an intensive three-year Python and Agentic AI program at PIAIC, Rubaiya builds systems that reason, call tools, and pause for a human before they act. Over that time she has moved from small scripts toward multi-agent orchestration — agents that plan, hand off work to other agents, and stop at a checkpoint instead of running unsupervised. She has also spent part of 2026 interning: building agentic workflows at Nexe-Agent, and full-stack web features at CodeAlpha, testing what the program has taught her against real, external codebases instead of only class projects.

(Word count: ~97, well over the 40-word floor.)

---

## `#projects` — Step 02 · TOOL-CALLS

Step marker: `02 — TOOL-CALLS`

Render each project as an `<article>` with an `<h3>` and a **call → result**
pair (a "call" line stating the problem taken in, a "result" line stating
what she built and shipped) — never a loose paragraph of tools.

### Article 1 — `<h3>` Autonomous AI Agent System

CALL:
> Give an agent a goal, let it plan its own steps, call tools to execute them, and don't let it act unsupervised.

RESULT:
> Rubaiya designed and built a multi-agent orchestration system on OpenAI Agents SDK, FastAPI, and MCP, where agents plan actions, call tools to carry them out, and stop at built-in Human-in-the-Loop checkpoints so a person signs off before anything ships.

### Article 2 — `<h3>` Cloud-Ready AI Chatbot

CALL:
> A chatbot that forgets everything the moment you close the tab isn't production-ready — it needs to remember the conversation and survive being redeployed.

RESULT:
> She built a chatbot in Chainlit that keeps persistent memory and stateful conversation across sessions, then containerized it with Docker and shipped it to a Kubernetes cluster on Azure using Helm charts, so the same image runs the same way every time it's deployed.

### Article 3 — `<h3>` Workflow Automation Platform

CALL:
> Several APIs and AI services needed to talk to each other without someone manually pushing data between them every time something changed.

RESULT:
> She built event-driven workflows in n8n backed by FastAPI and Python that trigger automatically on events and move data between services, cutting the manual, repetitive part of the pipeline down to only the parts that actually need a human.

---

## `#skills` — Step 03 · TOOLS

Step marker: `03 — TOOLS`

Framing line (small intro, optional): "The tools available to this run."

`<ul>`, one `<li>` per skill — all 19, copied exactly from `profile.md`:

- OpenAI Agents SDK
- MCP Servers
- LLM Prompt Engineering
- Multi-Agent Orchestration
- HITL Systems
- Tool-Calling
- Agent Memory & State
- FastAPI
- Chainlit
- Streamlit
- Next.js
- n8n
- Docker
- Kubernetes
- Git & GitHub
- Python
- Async Programming
- Event-Driven Architecture
- Reproducible AI Pipelines

---

## `#contact` — Step 04 · HUMAN-IN-THE-LOOP (awaiting input)

Step marker: `04 — HUMAN-IN-THE-LOOP` / status text: `Awaiting input.`

Intro line:
> The trace stops here. Everything above ran on its own — this step doesn't.

Links (at least one must be `mailto:` or `https://`; all five below are
straight from `profile.md`, only reformatted as links):

- Email: `mailto:rubaiyakamal0@gmail.com` — link text "rubaiyakamal0@gmail.com"
- Phone (plain text, not required as a link): +92-331-3494999
- Portfolio: `https://portfolio-professional-oul9.vercel.app` — link text "Portfolio"
- GitHub: `https://github.com/RubaiyaKamal` — link text "GitHub"
- LinkedIn: `https://linkedin.com/in/rubaiya-kamal-0a69622ba` — link text "LinkedIn"

---

## Notes for the builder

- Do not add a photo. `profile.md` has no image; an `<img>` inside `hero` or
  `projects` would need a non-empty, truthful `alt` (M5) and there is no
  source material to describe truthfully.
- Do not turn "Experience" (PIAIC / Nexe-Agent / CodeAlpha) into a dated
  sidebar ledger — that is the résumé shape J6 forbids. The internships and
  the PIAIC program are folded into the About paragraph above as context, not
  laid out as a dates column.
- No certifications section is written, because `profile.md` states none are
  held yet. Do not add one.
