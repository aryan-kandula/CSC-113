# Prompts Used — Task Manager Pro

These are the actual prompts I used throughout the development of Task Manager Pro.
They're organized roughly in the order I used them. Some are paraphrased slightly
because I didn't save every single conversation, but these represent the real
questions and problems I brought to Claude at each stage.

---

## Early Stage — Getting the structure down

**Prompt 1**
> "I want to build a task manager web app as a single HTML file — no frameworks,
> no build tools, just vanilla JS. I'm a CS student so I know some JavaScript but
> I've never built something this big from scratch. Can you help me figure out what
> features to start with and how to structure the file?"

I used this to get an outline before writing any code. Claude gave me a feature
list and I crossed off things that felt too complex for a first version.

---

**Prompt 2**
> "Okay so I want the design to be a dark glassmorphic style — like frosted glass
> panels over a dark background with glowing orbs. I've seen this on some portfolio
> sites. How do I actually do that in CSS? Like what properties make something look
> like glass?"

I had the visual in my head but didn't know the CSS for it. After Claude explained
`backdrop-filter`, `rgba` backgrounds, and border tricks, I wrote the actual style
rules myself using those concepts.

---

## Building Core Features

**Prompt 3**
> "Here's my addTask() function. It works but when I reload the page everything
> disappears. I know localStorage exists — can you show me how to plug it into
> what I already have without rewriting the whole thing?"

I specifically asked it NOT to rewrite everything because I wanted to understand
the change, not just paste new code. It showed me the save() and load() pattern
and I wired it in myself.

---

**Prompt 4**
> "I want tasks to have a priority level — high, medium, low. But I also want the
> app to guess the priority automatically based on the task name. Like if someone
> types 'Final Exam' it should default to high without them having to pick it.
> What's a clean way to do that?"

This became the `inferPriority()` function. I came up with the keyword categories
(exams = high, labs = medium, attendance = low) based on my own experience as a
student — I just asked Claude to turn my logic into a regex pattern.

---

**Prompt 5**
> "My urgency score only looks at days remaining. But if two tasks are both due
> today, the one due at 9am should feel more urgent than the one due at 11pm.
> How do I factor in the actual time of day into the score?"

This was my own idea — I noticed the flaw while testing. Claude helped me refactor
the function to build a full datetime instead of just a date, and handle the edge
case where no time is set (default to 23:59).

---

## Debugging Sessions

**Prompt 6**
> "Okay something is really wrong with my week calendar view. Tasks that are due
> on Wednesday keep showing up on the Tuesday column. I've been staring at this
> for like 20 minutes and I can't figure out why. Here's the relevant code:"
>
> *[pasted the date comparison logic]*

This was genuinely frustrating. Claude explained the UTC midnight shift issue —
that `new Date("YYYY-MM-DD")` in JavaScript is treated as UTC, which moves it
back a day in US timezones. I didn't know that was a thing. The fix was writing
`parseLocalDate()` to build dates from year/month/day components manually.

---

**Prompt 7**
> "The iCal import is working but some events are still landing on the wrong day.
> I think it might be the same UTC issue but in the ICS parser. The DTSTART line
> looks like this: `DTSTART;TZID=America/New_York:20250312T090000`. How should I
> parse that without accidentally shifting the date?"

Follow-up to the same bug in a different part of the code. I had to ask this
separately because the ICS format is different from a plain date string.

---

## AI Integration

**Prompt 8**
> "I want to add a real AI assistant inside the app — not a fake one, an actual
> API call to Claude. The assistant should know all the user's tasks and be able
> to answer things like 'what should I study today' or 'schedule my week for me.'
> How does the Anthropic Messages API work and how do I call it from plain JS
> with no backend?"

This was the biggest single feature. I read through the API docs myself first,
then used Claude to help me structure the fetch() call and figure out what to put
in the system prompt.

---

**Prompt 9**
> "Here's the system prompt I wrote for the in-app AI assistant. The problem is
> when I ask it to 'schedule my tasks this week' it dumps everything on Monday
> instead of spreading it out. How do I change the system prompt to fix that?"
>
> *[pasted my system prompt]*

This taught me a lot about prompt engineering — the fix wasn't more code, it was
rewriting the instructions in the system prompt to add explicit scheduling rules
like "max 4-6 tasks per day" and "skip weekends unless overdue."

---

## UI / UX Refinements

**Prompt 10**
> "I want to add a tag system where users can type a tag, press Enter, and it
> shows up as a colored pill inside the input field — like how Notion or Linear
> do it. The tag should be removable with an X. Can you show me the HTML/CSS/JS
> pattern for that?"

I had used tag inputs in other apps and wanted to replicate the feel. After Claude
showed me the pattern, I customized the colors to match the app's existing palette
and added the auto-tag merging logic myself.

---

**Prompt 11**
> "My detail panel looks fine on desktop but on mobile the grid is too wide and
> some buttons get cut off. Here's the CSS for `.dp-grid`. What's the fastest fix
> that doesn't break the desktop layout?"

Most of my responsive fixes came from prompts like this — describing a specific
broken layout and asking for a targeted fix, not a full rewrite.

---

## Documentation

**Prompt 12**
> "I need to write a CHANGELOG.md for my project repo. I have four versions:
> v1.0 (basic task CRUD), v2.0 (week view + import), v3.0 (AI assistant), and
> v3.2 (urgency scoring + tags). What's the standard format for a changelog and
> can you help me fill it out based on those versions?"

I filled in the actual feature descriptions myself — Claude just gave me the
Keep a Changelog format so it looked professional.
