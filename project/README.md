# Task Manager Pro

## What is this?

Task Manager Pro is a browser-based student productivity app that helps college students manage assignments, deadlines, and study sessions in one place. It integrates Claude AI as a built-in assistant that can read your actual task list and generate personalized study schedules, priority rankings, and daily focus recommendations. All data stays in your browser — nothing is sent to a server.

## What does it do?

- **Task management** — Add tasks manually with due date, time, priority, course, type, and custom tags
- **Smart auto-detection** — Task type (exam, assignment, class, etc.) and priority are inferred automatically from the task name
- **Time-aware urgency scoring** — Every task gets a 0–100 urgency score that factors in how many hours (not just days) remain
- **AI Study Assistant** — Powered by Claude via the Anthropic API; answers questions like "schedule my tasks this week" with a real day-by-day plan using your actual task names
- **Week Calendar View** — Navigate weeks with arrows, click any day tile to filter to just that day's tasks
- **Import from Canvas / Google Calendar** — Paste an iCal URL once and tasks auto-refresh every 5 minutes
- **Bulk actions** — Mark all overdue tasks done at once, or by date range
- **Custom focus timer** — Pomodoro-style animated ring timer; set any duration, not just presets
- **Dark/light theme toggle** — Full iOS 26-style liquid glassmorphic design

## How far did I get?

100% — the project is fully functional and deployed live at:
**[https://aryan-kandula.github.io/TaskManagerPro](https://aryan-kandula.github.io/TaskManagerPro)**

The app went through four major development iterations (v1.0 through v3.2), each adding meaningful features documented in `CHANGELOG.md`. The final version (v3.2.0) added time-aware urgency scoring, smart tagging with pill-style input, task type classification with auto-detection, and the AI disclaimer banner.

## What AI tools did I use?

- **Claude (Anthropic)** — Used throughout the entire development process for iterative code generation, debugging, feature design, and the live AI assistant feature embedded in the app itself. Claude is also the AI engine powering the in-app study assistant via the Anthropic Messages API.
