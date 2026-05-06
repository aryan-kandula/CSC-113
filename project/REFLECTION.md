# Reflection — Task Manager Pro

## About My Process

**What was your biggest "aha moment" when working with AI this semester?**

My biggest aha moment was realizing that AI is not a shortcut — it's a collaborator. Early on I expected to describe what I wanted and get a finished product. What actually happened was more interesting: the AI would give me something close, I'd test it, find something broken or missing, describe the problem back, and we'd iterate. The "aha" was understanding that the skill isn't in asking once — it's in knowing how to read the output critically, identify what's wrong, and give better follow-up instructions. That loop of prompt → output → critique → re-prompt is where the real work happens.

**Describe a time when the AI gave you something useless. What did you do next?**

When I first tried to get Claude to build the week calendar view, it generated something that looked right visually but was completely broken — tasks were showing up on the wrong days because JavaScript's `new Date("YYYY-MM-DD")` parses date strings as UTC midnight, which shifts them backward by a day in US timezones. Claude's initial code had this bug baked in. What I did next was describe the exact symptom ("tasks due Wednesday are showing up on Tuesday"), ask Claude to explain why that would happen, and once it identified the UTC offset issue, I asked it to rewrite the date-handling logic using local date parsing only. The fix became the `parseLocalDate()` and `toYMD()` helper functions that now run throughout the entire app. That experience taught me to always test AI-generated code against real edge cases, not just the happy path.

**How did your prompting approach change from Week 1 to now?**

Week 1 me was writing vague one-sentence prompts like "make a task manager app." By the end of the semester I was writing prompts with context, constraints, and examples — specifying the exact function name, describing the bug's root cause, providing the relevant code snippet, and stating what the correct output should look like. I also learned to give AI a persona and a set of rules upfront (like the system prompt I wrote for the in-app AI assistant) rather than hoping it would figure out the context on its own. The difference in output quality between those two approaches is enormous.

---

## About What I Learned

**What's one thing you can do with AI now that you couldn't do in August?**

I can build and ship a complete, working web application from scratch — one with real API integrations, a polished UI, and production-quality features — without knowing every syntax detail upfront. Before this semester, I would have gotten stuck on the CSS for a glassmorphic card or the logic for an iCal parser and stopped there. Now I can describe what I need, get working code, understand it well enough to debug and extend it, and actually finish the thing.

**What surprised you most about working with AI tools?**

How much it matters what you already know. I went in thinking AI would make knowledge irrelevant — just describe what you want and it does it. The reality is the opposite: the more you understand about programming, the better your prompts become, the better you can evaluate the output, and the faster you can catch mistakes. AI amplifies what you already know. It's much less useful when you have no foundation to judge the output against.

**What's something AI is genuinely bad at that you discovered firsthand?**

Keeping track of state across a long, complex codebase. When the app grew past a certain size, Claude would sometimes "fix" a bug in one function by rewriting it in a way that broke three other functions that depended on the original behavior — because it didn't have full context of how everything connected. I had to get deliberate about providing the relevant code sections in each prompt rather than assuming it remembered the earlier conversation. AI is great at solving individual, well-scoped problems. It struggles with holistic system awareness across hundreds of lines of interconnected code.

---

## About What's Next

**How might you use AI tools in your other classes or your job?**

In my CS and IT courses, I'll use AI the same way I used it here — as a pair programmer for debugging and feature development, and as a code reviewer to catch edge cases I might miss. For writing-heavy courses I'll use it to outline and structure arguments, though I've learned to always rewrite in my own voice afterward. On the job side, I'm planning to transfer to UNC Pembroke for a CS degree, and I expect AI-assisted development to just be a baseline skill by the time I graduate — so the workflow I built this semester feels like actual career preparation.

**What would you tell a friend who's never used AI tools to help them get started?**

Start with something you actually care about building. The hardest part isn't the AI — it's knowing what you want well enough to describe it. Pick a small, specific project, write down what it should do in plain English, and paste that into Claude or ChatGPT. Don't expect the first output to be perfect. Read it, test it, figure out what's wrong, and tell the AI specifically what needs to change. Do that loop three or four times and you'll understand more about effective prompting than any tutorial could teach you.

**Is there anything you want to learn more about after this course?**

I want to go deeper on the Anthropic API — specifically function calling / tool use, which lets the AI actually take actions (like creating a task in the app) rather than just generating text. I also want to learn more about how to write better system prompts, since the quality of the in-app AI assistant in TaskManagerPro was almost entirely determined by the system prompt I wrote, not the model itself.

---

## Honest Assessment

**On a scale of 1–10, how confident do you feel working with AI tools now versus when the semester started? Why?**

**Start of semester: 2/10 → End of semester: 8/10**

I started at a 2. I had used AI chatbots casually but had no idea how to use them for real technical work. I didn't understand prompting, didn't trust the output, and didn't know how to recover when it gave me something wrong.

I'm at an 8 now because I've built something real with it. TaskManagerPro went through 27 commits, four versioned releases, and hundreds of individual prompting sessions. I know how to scope a prompt, how to provide context efficiently, how to debug AI-generated code, and how to use the API directly to embed AI into a product. The 2 points I'm leaving on the table are for the things I described above — I still have work to do around complex multi-file codebases and getting AI to reliably reason about system-wide state. But the gap between where I started and where I am now is real, and it happened by doing the work.
