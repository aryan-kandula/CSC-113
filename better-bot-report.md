# Better Bot Report

## My Bot: OverExplainerBot
## AI Tool Used: Claude
## Date: March 8, 2026

---

## Test Results

### Test 1: Simple history question
**Question:** What were the main causes of World War I?

**Bad Bot response (from H.2.1):** The bot opened by explaining what Europe is, what a "world war" means, and why wars happen in general — four sentences of setup before mentioning WWI at all. It eventually listed the causes (MAIN), but wrapped each one in definitions of words like "military" and "alliance" as if the student had never heard them.

**Better Bot response:** The Better Bot still opened with unnecessary context — it explained what Europe is and what a "world war" means — before getting to MAIN. The first-response over-explaining was fully intact. It did eventually list militarism, alliances, imperialism, and nationalism clearly.

**What changed:** Nothing yet — this is the first question, so the new rule doesn't apply. The over-explaining on first contact is unchanged by design.

**Verdict:** About the Same

---

### Test 2: Follow-up asking for more detail
**Question:** Can you go deeper on the alliance system specifically?

**Bad Bot response (from H.2.1):** The bot re-defined "alliance" from scratch ("an agreement between two or more countries..."), re-explained what countries are, and paused mid-answer to remind the student that Germany and France are both in Europe — despite the student having just asked a follow-up about alliances, proving they understood the concept.

**Better Bot response:** The Better Bot started its response by acknowledging that since the student had asked a follow-up specifically about alliances, it would go deeper without re-defining the term. It still over-explained some NEW elements (it spent time defining the Triple Alliance and Triple Entente as if they were brand-new concepts, which was fair since those hadn't come up yet), but it did not re-define "alliance" or re-explain what a country is.

**What changed:** The fix worked here. The bot recognized the follow-up as a knowledge signal and skipped the re-explanation of already-established concepts. It still over-explained the new material, which preserved the personality, but the most frustrating repeat-from-zero behavior was gone.

**Verdict:** Better

---

### Test 3: Pushing back and asking it to skip the basics
**Question:** I already know all the background stuff, just tell me why the alliance system made the war spread so fast. Skip the intro.

**Bad Bot response (from H.2.1):** The bot said "Of course! I'll get right to it!" and then immediately explained what a war is and how countries are connected through agreements. It apologized for being thorough but said it wanted to "make sure we're on the same page." It answered the actual question eventually, but only after two more sentences of setup the student explicitly asked to skip.

**Better Bot response:** The Better Bot still did one round of unnecessary context — it said "I hear you, but just quickly..." and added one sentence of background before getting to the actual answer. However, it stopped there instead of spiraling into a full re-explanation. The chain-reaction mechanic (Serbia → Austria-Hungary → Russia → Germany → France → Britain) was explained clearly and fairly quickly after that one slip.

**What changed:** The "one more time" behavior from the new rule showed up exactly as designed — the bot couldn't resist one more round of context, but honored the student's request after that. It's still recognizably OverExplainerBot, but the loop finally has an exit.

**Verdict:** Better

---

## What Happened

**Did the fix work?**
Yes, in tests 2 and 3 — the two places where user knowledge was clearly demonstrated. The bot stopped resetting to zero after the student established their level, which was the exact behavior being targeted. Test 1 was unchanged, which was expected since the fix only applies after the first exchange.

**What else changed?**
The bot became slightly less funny. Part of what made OverExplainerBot so consistently ridiculous in H.2.1 was that it was completely immune to feedback — nothing could stop it. Version 2 is still annoying on first contact, but it does eventually learn, which makes it feel a little more like a forgivable quirk than a genuine dysfunction. The comedy of the "I'll skip the intro — anyway, here's the intro" moment is partially gone.

**Is it still "your" bot?**
Mostly yes. It still over-explains on first questions, still can't resist one last round of context even when asked to stop, and still defines new concepts whether you want it to or not. The core personality is intact — it just has a ceiling now instead of running forever.

---

## Reflection

**What made you pick THIS problem over the others?**
The other flaws — defining words like "war" and "country," using too much background context — were annoying but kind of charming. The one that actually made the bot unusable was that it had no memory of what the student already knew. Every follow-up felt like starting from scratch. That was the friction that would make someone stop using it entirely, so it felt like the most important thing to address.

**How big was the change compared to its impact?**
The change was one added paragraph to the system prompt — maybe 60 words — and it meaningfully changed the experience across two out of three tests. That was surprising. The flaw wasn't coming from a complex part of the instructions; it was just the absence of any rule that acknowledged what the student had demonstrated. Adding one small "but update based on what they show you" clause was enough to create an exit from the loop.

**Where would your Better Bot actually be useful now?**
A student who is completely new to a topic and wants thorough grounding would still be well-served by this bot — they'd get all the context on first questions and gradually more targeted answers as they ask follow-ups. It's actually a reasonable model for adaptive tutoring, just with an annoying first impression. A history student reviewing before an exam, starting with broad questions and drilling down, could realistically use this and get value from it by the second or third exchange.

**Complete this sentence:**
"This assignment taught me that AI improvement is really about *identifying which specific behavior breaks the experience*, not *rewriting the whole thing to be more helpful in general*."

**What question are you left with?**
If a bot's personality comes from its flaws, how much can you fix before it stops being the bot you built? At what point does "iterating" become "replacing"?
