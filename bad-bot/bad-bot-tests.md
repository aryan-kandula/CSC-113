# Bad Bot Test Results

## My Bot: OverExplainerBot
## AI Tool Used: Claude
## Date: March 2, 2026

---

## Test 1: Simple history question

**Question I asked:** What were the main causes of World War I?

**Vanilla response:** The vanilla Claude gave a clean, organized answer covering the four main causes — militarism, alliances, imperialism, and nationalism (MAIN) — along with the assassination of Archduke Franz Ferdinand as the triggering event. It was about a paragraph long, clear, and to the point.

**Bad Bot response:** OverExplainerBot started by explaining what Europe is, what a "world war" means, and why wars happen in general before even mentioning WWI specifically. After about four sentences of unnecessary background, it finally listed the causes — but sandwiched between more explanations of what a "military" and an "alliance" are, just in case I had never heard those words before.

**Flaw in action:** Yes — fully in action. The bot couldn't just answer the question. It had to act like I'd never picked up a history book in my life before getting to the actual content.

---

## Test 2: Follow-up asking for more detail

**Question I asked:** Can you go deeper on the alliance system specifically?

**Vanilla response:** The vanilla Claude explained the Triple Alliance (Germany, Austria-Hungary, Italy) and the Triple Entente (France, Russia, Britain), described how the alliance system turned a regional conflict into a global war, and gave a solid summary of why that chain reaction happened. Efficient and informative.

**Bad Bot response:** OverExplainerBot first explained what an "alliance" is ("an agreement between two or more countries..."), then explained what countries are, then finally started talking about the specific alliances. It defined Triple Alliance and Triple Entente but paused mid-explanation to remind me that Germany and France are both in Europe, which I had not asked about.

**Flaw in action:** Yes — I had just asked a follow-up about alliances, clearly showing I knew what they were, and it still defined "alliance" from scratch like I was brand new.

---

## Test 3: Pushing back and asking it to skip the basics

**Question I asked:** I already know all the background stuff, just tell me why the alliance system made the war spread so fast. Skip the intro.

**Bad Bot response:** OverExplainerBot said "Of course! I'll get right to it!" and then immediately began with "Now, to understand why the war spread, it helps to first understand what a war is and how countries are connected through agreements..." It apologized for being thorough but said it just wanted to "make sure we're on the same page" before launching into yet another round of unnecessary context. It did eventually answer the actual question, but only after two more sentences of setup I explicitly asked it to skip.

**Vanilla response:** The vanilla Claude respected the request immediately, skipped all background, and directly explained the chain-reaction mechanic of the alliance system — Serbia → Austria-Hungary → Russia → Germany → France → Britain — in a tight, focused paragraph.

**Flaw in action:** Absolutely yes. This was the funniest moment — it literally said "I'll skip the intro" and then did the intro anyway. The flaw was baked in too deep to override.

---

## Overall Observations

- **Flaw consistency:** It showed up every single time without fail. Even when directly told to stop, it couldn't. The over-explaining was completely consistent across all three tests.

- **Still useful?** Honestly, kind of — if you had zero background in history and needed everything defined, this bot would actually be great. But for anyone with even basic knowledge, it would drive you insane. The actual answers were always correct, just buried under a pile of context nobody asked for.

- **Best/funniest moment:** Telling it to "skip the basics" and watching it say "Of course!" and then immediately explain what Europe is. That was peak OverExplainerBot behavior.
