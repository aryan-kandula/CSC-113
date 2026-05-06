# 🤖 CSC-113: Artificial Intelligence Fundamentals

**Aryan Kandula** · Fayetteville Technical Community College · Spring 2025

> A semester of learning how to actually work with AI —
> prompting, iterating, breaking things, and building something real.

---

## 👤 About Me

Computer Science student at FTCC, transferring to UNC Pembroke for a B.S. in CS. I came into this course knowing how to code but not how to use AI as a real development tool. By the end I had shipped a fully functional web app with a live AI assistant baked in. This repo documents that whole process.

---

## 🏆 Final Project — Task Manager Pro

The capstone of the semester. A browser-based student productivity app powered by the Claude API.

🔗 **[Live Demo → aryan-kandula.github.io/TaskManagerPro](https://aryan-kandula.github.io/TaskManagerPro)**

**What it does:**
- Manages assignments and deadlines with smart auto-detection of priority and task type
- Time-aware urgency scoring (0–100) that factors in hours remaining, not just days
- Built-in AI assistant that reads your actual task list and schedules your week
- Canvas + Google Calendar iCal import with 5-minute auto-refresh
- Custom Pomodoro timer, bulk actions, week calendar view, dark/light theme

**What's in `project/`:**

| File | What It Is |
|---|---|
| [`project/README.md`](project/README.md) | Project overview — what it is, what it does, how far I got |
| [`project/REFLECTION.md`](project/REFLECTION.md) | Honest reflection on what I learned this semester |
| [`project/prompts/prompts.md`](project/prompts/prompts.md) | Real prompts I used while building the app |
| [`project/ITERATION_LOG.md`](project/ITERATION_LOG.md) | Development decisions across all 4 versions |
| [`project/PRD.md`](project/PRD.md) | Product requirements document |
| [`project/PROTOTYPE_TESTING.md`](project/PROTOTYPE_TESTING.md) | Tool comparison and testing notes |

---

## 📂 Repository Structure

```
CSC-113/
├── project/                    ← Final project submission
│   ├── README.md
│   ├── REFLECTION.md
│   ├── ITERATION_LOG.md
│   ├── PRD.md
│   ├── PROTOTYPE_TESTING.md
│   └── prompts/
│       └── prompts.md
│
├── bad-bot/                    ← Module: Bad bot vs better bot prompt engineering
│   ├── README.md
│   ├── bad-bot-prompt.md
│   └── bad-bot-tests.md
│
├── better-bot/                 ← Improved bot with refined prompting
│   ├── README.md
│   ├── better-bot-prompt.md
│   └── better-bot-report.md
│
├── csc113-portfolio/           ← Week 2 prompt experiments and tool comparisons
│   └── week-02-sage/
│       ├── kevin-conversation.md
│       ├── prompt-library.md
│       ├── tool-comparison.md
│       └── track-b-prompt-experiments.md
│
├── module-1/                   ← Module 1 reflections and Gemini experiments
│   ├── gemini-flash.md
│   └── ai-for-everyone/
│       └── ai-for-everyone.md
│
└── project-ideas/              ← Early ideation before settling on Task Manager Pro
    └── README.md
```

---

## 📈 What I Learned

A rough arc of the semester:

**Weeks 1–3** — Learned what prompting actually is. Realized vague questions get vague answers. Started building a personal prompt library.

**Weeks 4–6** — Bad bot / better bot assignment. The gap in output quality between a one-liner prompt and a structured system prompt with examples was genuinely surprising.

**Weeks 7–12** — Started building Task Manager Pro. Used Claude for code generation, debugging, and architecture decisions. Learned that AI amplifies what you already know — the more I understood the code, the better my prompts became.

**Weeks 13–15** — Integrated the Anthropic Claude API directly into the app. Learned that prompt engineering applies just as much to system prompts as it does to chat — the AI assistant's scheduling behavior was almost entirely determined by how I wrote the rules in the system prompt.

Full reflection: [`project/REFLECTION.md`](project/REFLECTION.md)

---

## 📌 Project Planning

Issue tracking and planning managed through GitHub Issues.
➡️ [View planning board](https://github.com/aryan-kandula/CSC-113/issues/11)
