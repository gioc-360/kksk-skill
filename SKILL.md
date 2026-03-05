---
name: kksk
description: >
  A context engineering discipline for vibe coding that prevents scope creep and ensures you
  solve the real problem. Use when the user wants to build a tool, automate a workflow, vibe
  code a solution, create an MVP, or asks "build me an app/script/automation for X". Trigger
  when users jump to implementation without defining problems, paste feature lists and say
  "build this", or when scope creep emerges mid-build. Also trigger on vague audiences
  ("small businesses", "everyone"), inability to articulate who is desperate, or resistance to
  narrowing scope. Do NOT use for simple one-off scripts, quick code snippets, requests where
  the user already has a clear narrow spec, or non-technical problems (organizational,
  political, discovery-phase).
license: MIT
compatibility: >
  Platform-agnostic. Works on Claude.ai, Claude Code, and API. No external tools,
  network access, or system packages required. Prose-only methodology skill.
metadata:
  author: Gio Caballero
  version: 1.0.0
---

# KKSK — 構え · 崩し · 誘い · 極め

A four-phase scoping discipline for vibe coding, developed by Gio Caballero (Cornell MBA '27). Modeled on the sequential-gate structure of Brazilian Jiu-Jitsu: you cannot finish a submission from a bad position — skip the setup and you get swept. But the deeper principle is position over submission. Good position lets you chain attacks — each stuffed attempt opens the next. Bad position means every failed attempt resets you to zero. The same physics apply to building software: skip the context and you build the wrong thing beautifully. Nail the context and every failed implementation is just a transition, not a reset.

The name reads as こここすき (kokosuki) — "I like this" — the feeling when a perfectly established position makes the finish inevitable. If the build feels forced, you skipped a phase.

The #1 failure mode in AI-assisted building is solving the wrong problem. Everyone drills the finish (the code). Nobody drills the setup (the context). KKSK is the setup.

## How to Use This Skill

The four phases are sequential gates. Do not advance until the current phase has a concrete output confirmed by the user. If stuck, go back one phase.

| Situation | Action |
|---|---|
| User describes a pain/problem | Start at Phase 1 (Kamae) |
| User says "build me X" with a feature list | Pause. Run Phase 1 first — what's the actual pain? |
| User has a workaround they want automated | Start at Phase 2 (Kuzushi) — the workaround IS the requirements |
| User already has a clear function spec | Validate Phase 3 (Sasoi), then execute Phase 4 (Kime) |
| Scope is creeping mid-build | Stop. Return to Phase 3 — is this still one function? |
| User is building for a vague audience | Stop. Return to Phase 1 and run the Wedge Test |

After completing each phase, present the output to the user and confirm before advancing. Do not proceed to the next phase without explicit user agreement that the current phase output is correct.

## When NOT to Use KKSK

Put this skill down when:

- **The pain is organizational, not technical.** If the root cause is a broken incentive, a missing role, or a political conflict, no function fixes that.
- **The problem requires discovery, not scoping.** If you can't articulate the pain because you don't understand the domain yet, go observe and interview first.
- **The real answer is "stop doing this."** Sometimes the workaround reveals the entire workflow is unnecessary.
- **You're exploring, not converging.** KKSK is reactive (find pain, solve it). If you're discovering what's possible with a new capability, you need a generative mode.

If any of these feel true, stop. KKSK will give you a clean, well-scoped solution to the wrong problem — which is worse than no solution at all.

---

## Phase 1: KAMAE (構え) — Establish Position

**Question:** What is the pain?

Before defining the pain, name the job. What is this person already trying to accomplish, and what are they currently hiring to do it badly? The pain isn't the position — it's the failed transition between the job they need done and the broken thing they've hired to do it.

Pin it to one sentence:

**"[Who] loses [how much] doing [what task] because [root cause]."**

Every word matters. "Who" forces a real person. "How much" forces quantification (time, money, errors). "What task" forces specificity. "Root cause" forces you past symptoms to the structural issue.

**Output:** One sentence. Written down. Confirmed by the user.

**Failure test:** If the pain statement contains "streamline," "optimize," or "leverage," Kamae isn't done. These are consultant words that hide the absence of a specific problem. Push harder: what *specifically* breaks, for *whom*, and what does it *cost*?

**Falsification test:** Before proceeding, write down what evidence would convince you this pain isn't real. Then look for it. If you can't find disconfirming evidence, the pain statement is stronger. If you can, you just saved a build cycle.

### Kamae Sub-Gate: The Wedge Test

Before moving to Phase 2, pressure-test the pain statement with three questions. This prevents the most common strategic failure: building the right thing for the wrong audience.

**1. Who has this pain at 10x intensity?**
Not "who has this pain" — who is *desperate*? Who is currently losing real money, time, or competitive position because this problem is unsolved? If everyone has the pain equally, you don't have a wedge — you have a commodity.

**2. What is the one dimension where your solution is undeniably better?**
Not better overall. Better on the single axis the desperate user is hiring you for. If you can't name the dimension in one phrase, you're competing on "generally nice," which is how you lose to incumbents.

**3. What are you explicitly saying no to?**
Name the users you are refusing to serve. Name the features you will not build. Name the market you are ceding. If this feels painful, you're doing it right. If you haven't said no to anything, you haven't focused.

**Output:** Three written answers. Confirmed by the user. If any answer is vague, do not proceed.

**Failure test:** If answer #1 is "everyone" or a demographic label (e.g., "small businesses"), you haven't found your wedge. Push until you can describe a person with a specific operational pain that costs them something measurable. If answer #3 is empty, you're setting up the oscillation problem — trying to be two things and being neither.

---

## Phase 2: KUZUSHI (崩し) — Study the Reaction

**Question:** Where is the friction?

Map how people currently survive the pain — workarounds, duct-tape spreadsheets, manual copy-paste, email chains, sticky notes. The workaround is the best requirements document because it encodes what users *actually do*, which is more reliable than what they *say* they want.

Identify where 80% of the time concentrates. That's the target.

**Output:** Documented current workflow with the bottleneck circled. Confirmed by the user.

**Failure test:** If you can't draw the current workflow from memory after studying it, Kuzushi isn't done. You should be able to describe exactly what the user does today, step by step, without looking at notes.

---

## Phase 3: SASOI (誘い) — Isolate the Logic

**Question:** What is the one function?

Strip everything to the single transformation that converts painful input into desired output. Name it. Type it. That is the entire product:

```
function_name(painful_input) → solved_output
```

This is the hardest phase because it requires saying NO to everything else. No UI. No auth. No database. No API. Just the function. If you can't express the solution as one function with typed inputs and outputs, you're building too much.

**Output:** A named function with typed inputs and typed outputs. Confirmed by the user.

**Failure test:** If the function needs the word "and" to describe what it does, or resolves more than one concern, each "and" is a separate KKSK cycle pretending to be one. Split it.

---

## Phase 4: KIME (極め) — Execute and Measure

**Question:** What is the result?

NOW build — but only within the boundaries the previous three phases created. The build should feel inevitable because the setup eliminated ambiguity.

When prompting AI to build, use the context engineering template at `templates/context-prompt.xml`. This template structures the pain, workaround, function signature, and constraints into a format that prevents scope expansion during code generation.

**Done condition:** The person who was doing the workaround uses your function instead, unprompted, twice. Not "it works in a demo." Not "the tests pass." The actual human uses it voluntarily because it's better than their duct tape.

**Output:** Working function with measured impact.

**Failure test:** If you're choosing between databases, deployment platforms, or CSS frameworks during Kime, go back to Sasoi. You're building infrastructure for a function that should run in a notebook.

---

## The Anti-Pattern

Recognize this pattern and intervene:

**Wrong:** "Build me a full-stack app with auth, a dashboard, attendee tracking, notifications, and payments."

**Right:** "Build one function that takes raw form responses and returns a clean, deduplicated roster."

The first produces a beautiful prototype that solves nothing well. The second becomes the standard people actually use. When you see the first pattern, run Kamae: what's the pain that makes someone want all five of those features? Usually, the answer reveals that one function solves the actual problem.

---

## Failure Modes

These patterns emerge when someone follows the letters of KKSK but not the spirit. If you recognize any, stop building and return to the indicated phase.

**1. The Fake Kamae** — Pain statement exists but it's a rephrased feature request. "Users lose time because they don't have a dashboard" is not a pain — it's a solution wearing a pain costume. The tell: the "root cause" slot contains a missing feature instead of a structural problem. → *Go back to Kamae. Ask what job they're trying to get done.*

**2. The Sympathetic Audience** — You found people who *agree* the pain exists but aren't *desperate* enough to use a janky v1. Nodding is not adoption. If your Wedge Test answer to "who has this at 10x intensity" is a demographic label instead of a person you can describe in operational detail, you have sympathy, not desperation. → *Go back to the Wedge Test.*

**3. The Skipped Kuzushi** — Went straight from pain to function without studying the workaround. The result is technically correct but doesn't fit the user's actual workflow. They'll say "cool" and go back to their spreadsheet. → *Go back to Kuzushi. The workaround is the spec.*

**4. The Compound Sasoi** — The "one function" quietly does three things. The tell: you need "and" to describe what it does. Each "and" is a separate KKSK cycle pretending to be one. → *Go back to Sasoi. Split it.*

**5. The Premature Kime** — You're choosing between React and Svelte for something that should be a Python script. You're debating database schemas for something that fits in a CSV. Architecture is the procrastination of people who haven't scoped properly. → *Go back to Sasoi. If the function is clear, the implementation is obvious.*

---

## Position Over Submission

The phases above establish position. This section explains why that matters when things go wrong during execution.

In BJJ, white belts chase submissions. They lunge for an armbar from a bad angle and — when it gets stuffed — they've lost position entirely. They have to re-engage from neutral or worse. Black belts establish dominant position first. When their first attack gets stuffed, they don't lose anything. They transition: the arm defense opens the neck, the neck defense opens the back, and each failed submission leads to a better one. The finish becomes inevitable not because any single attack is perfect, but because the position makes every transition productive.

KKSK works the same way. The function signature from Sasoi is your dominant position. When an implementation fails — the API doesn't work, the tool can't handle it, the architecture is wrong — the question is: do you still have position? If Kamae, Kuzushi, and Sasoi are solid, you do. You transition to a different implementation (a different submission) without renegotiating what you're building (without losing position). If your scoping was vague, every failed implementation forces you to re-ask "what are we even building?" — that's re-engaging from neutral.

This is why the phases are sequential gates, not optional steps. Each phase makes the next transition cheaper:

* Kamae locks in the pain → you never waste a transition solving the wrong problem
* Kuzushi maps the workaround → you never build something that doesn't fit the user's actual workflow
* Sasoi isolates the function → every failed implementation is just a tool swap, not a scope reset

Chase the submission (jump to code) and every failure is a reset. Establish position (run the phases) and every failure is a transition. The finish becomes inevitable.

---

## The Exit Rule

When the function works, ask: does the next pain touch this function's output? If yes, run KKSK again — the output of the first function becomes the input context for the next cycle. If no, you're done, or you need a different framework entirely.

This creates natural composition: small, proven functions chained together, each validated by actual use before the next one is built.

---

## The Expansion Rule

When the wedge works and the function is adopted, resist the instinct to go broad immediately.

- **Deepen** if current users have a *second* pain that touches the output of the first function. This is the natural KKSK chain: output of cycle 1 becomes input context for cycle 2.
- **Go adjacent** if the wedge audience is saturated and a *neighboring* segment has started pulling your solution toward them unprompted. Key word: "pulling" — if you have to push, it's too early.

**The Trojan Horse test:** Can your success in the wedge market serve as proof that opens the next market without changing the product? If yes, expand. If expanding requires rebuilding for a different buyer, run KKSK from scratch.

**Anti-pattern:** "We've won Higher Ed, let's go after Enterprise and Consumer simultaneously." This is indigestion. Pick one adjacent market. Win it. Then reassess.

For a detailed walkthrough, see `references/expansion-guide.md`.

---

## Composability

KKSK handles **scope** — what to build. For **substance** (how to build it well), hand off to the 4R skill after Sasoi is complete. If both skills are active, consult the SSS skill for sequencing. KKSK does not set execution methodology or output formatting — it clears the path so those disciplines can operate on a well-defined target.

---

## Reference Files

| File | When to Read |
|---|---|
| `templates/context-prompt.xml` | During Kime — use this to structure the AI prompt |
| `references/output-format.md` | When presenting KKSK work — standard output template |
| `references/expansion-guide.md` | After Kime succeeds — guidance on deepening vs. going adjacent |
| `case-studies/jjc-landing-page.md` | For a real-world end-to-end walkthrough of KKSK applied to a code build |
| `case-studies/greengami-strategy-questionnaire.md` | For KKSK applied to a strategic deliverable — demonstrates Wedge Test catching a position-reading failure, not a scoping error |

---

## Quick Reference

| Phase | Japanese | Question | Output |
|---|---|---|---|
| Kamae | 構え | What is the pain? | One-sentence pain statement + Wedge Test |
| Kuzushi | 崩し | Where is the friction? | Documented workaround + bottleneck |
| Sasoi | 誘い | What is the one function? | Named function with typed I/O |
| Kime | 極め | What is the result? | Working function, measured impact |
