# KKSK Case Study: The Founding Agent

A real-world application of KKSK to a strategic pitch deliverable: an MBA homework assignment requiring conceptual agent design. The build target was a 12-slide presentation and 10-minute video, not software. This case demonstrates KKSK's value in rapid idea refinement under time pressure, and introduces a pattern not seen in prior case studies: multiple Kamae resets driven by the user's own taste rejecting technically valid scopes.

## Context

NBA 4920/6921 Homework 2 Part B (Professor Manzoor, Cornell). The assignment: conceptualize a useful AI agent, design its architecture, evaluation plan, and cost model. Deliverable is a 10-15 minute video presentation scored against a rubric with four sections: business/AI problem (2.5pts), evaluation (5pts), architecture (5pts), and cost/tradeoffs (2.5pts). The rubric explicitly references OpenAI's in-house data agent as the gold standard.

Solo submission. KKSK (scope), 4R (substance), managerial-comms + writing-style (surface) were orchestrated via SSS. The entire project — from first idea to final deck and video script — was completed in a single extended session.

---

## Phase 1: Kamae — Establish Position

### The Rejection Sequence

This case is unusual because Kamae ran five times before a pain statement stuck. Each rejection was driven by the user's taste, not by Kamae's failure test. The user knew what felt wrong before they could articulate what was right. KKSK's sequential gates gave structure to that instinct instead of letting it spiral.

**Attempt 1: "MarketCast multilingual NLP agent"**
Technically valid — the user built the original NLP engine and had ground truth data for backtesting. Rejected because the pain is too domain-specific. Half the presentation would be spent explaining open-end survey coding methodology instead of the agent design.

**Attempt 2: "Dell PM onboarding agent"**
Clear pain (new PMs waste weeks figuring out what's going on), relatable audience (every MBA intern). Rejected because the user didn't want to play PM in the presentation — they wanted to play PM *in the product*. The agent should be the engineering team, not the onboarding buddy.

**Attempt 3: "PM workflow agent using KKSK/4R/managerial-comms"**
The user's skill stack as the agent's methodology. Rejected because it positioned the skills as what the agent uses. The user's reframe: the skills are how *they* manage the agent. They want to direct, not be replaced.

**Attempt 4: "Karaoke machine agent" / "Japanese cigarettes procuring agent"**
Both rejected on the spot. Neither had a clear AI problem, both failed the "why can't you just Google this?" test, and neither had a viable evaluation story.

**Attempt 5: The pivot.**
The user asked: "What about we say yes to those users who just want to be creative?" This reframe cracked the problem open. The agent isn't for engineering teams or PM orgs. It's for solo builders with taste who use AI as their engineering team. The user is the case study.

### Final Pain Statement

> "Solo builders with ideas and taste lose days per project to scope creep and rework because AI coding tools execute whatever you ask for without questioning whether it's the right thing to build — so the builder becomes a babysitter debugging a mess instead of a creative directing a build."

### Falsification Test

Would this pain disappear if coding tools got smarter? No. Smarter tools execute faster, which makes bad scoping worse, not better. Speed without direction is faster scope creep.

### Wedge Test

1. **10x desperate:** Non-technical founders, designers, and PMs who vibe code as their primary build method. They have taste and domain expertise but zero engineering background. Every bad AI output costs them hours because they can't diagnose why it broke.
2. **One dimension better:** The agent says no for you. Every other tool says yes.
3. **Saying no to:** Professional engineers (they have their own discipline). Enterprise teams with PMs and scrum. People who just want code written faster.

**Why this matters:** The five-rejection sequence looks inefficient on paper, but each rejection sharpened the scope. Without KKSK's gate structure, the user might have committed to attempt 1 or 2 and built a competent presentation for the wrong idea. The gates gave permission to reject without losing momentum.

---

## Phase 2: Kuzushi — Study the Workaround

**Current workflow documented (the user's actual process):**

1. Idea hits.
2. Open Claude.ai. Describe the idea conversationally. 20+ messages before the problem is clear.
3. Manually decide "scope is locked." No gate enforces this — it's gut feel.
4. Switch to Claude Code or stay in Claude.ai for execution. Prompt, review, reject, redirect, reprompt.
5. Scope creep starts. "While we're at it, add this." The tool happily complies.
6. Catch it (or don't). If caught, manually prune. If not, ship something bloated.
7. Formatting/polish is another manual pass.

**Bottleneck identified:** Steps 2-3 (scoping without structure) and step 5 (unchecked scope creep). The actual building (step 4) is fast — the tool is good at executing. The problem is it executes anything, including bad scope.

**Key insight:** The user's entire skill stack (KKSK, 4R, SSS, managerial-comms, writing-style) is a manual discipline layer they impose on themselves to prevent steps 2-3 and 5 from going sideways. But they have to *remember* to invoke it. The tools don't enforce it. Self-discipline degrades at 1am when you're excited about a build.

---

## Phase 3: Sasoi — Isolate the Function

**First attempt:**

```
creator_agent(raw_idea) → scoped_build_with_phase_gates
```

Rejected as too vague. Sharpened through dialogue.

**Final function:**

```
founding_agent(vague_idea, builder_taste) → shipped_product
```

Where `builder_taste` is persistent — it learns what the user accepts, rejects, and cares about across builds. The agent gets better at anticipating judgment over time.

**The "and" test:** Does this need "and" to describe? "It scopes AND builds AND formats." Three things. But they're sequential phases of one pipeline, not parallel concerns. One pipeline. One function. The "and" test passed because each phase gates the next — they don't operate independently.

**Key distinction surfaced during Sasoi:** "Skills make *you* a better builder. The agent makes *anyone with taste* a builder." This distinction — skills as IP, agent as product — became the moat argument in the final deck.

---

## Phase 4: Kime — Execute and Measure

Kime here was not code. It was a 12-slide presentation and a 10-minute video script.

### SSS Orchestration

Because multiple skills applied, SSS was invoked to sequence them:

| Skill | Role | Authority |
|---|---|---|
| KKSK | Scope | Already complete. Constrained everything below. |
| 4R | Substance | Produced architecture, evaluation plan, cost model. |
| Managerial-comms | Surface | Presentation strategy, action titles, audience calibration. |
| Writing-style | Surface | Prose quality in video script. |

### 4R Substance Pass

**Right View — Riskiest assumption:** "Solo builders with taste are a real, findable market segment, not just the user." Spiked by referencing the vibe coding movement: Pieter Levels, Replit growth, the "CEO of one" meme. Confirmed.

**Right Build — Architecture:** Four-layer agent pipeline (Scout → Scoping → Build → Polish) with the user as the Founding Agent who coordinates. Six course concepts (Tools/MCP, Skills, RAG, Memories, Fine-tuning, Preference Optimization) mapped to specific architectural decisions.

**Right Rhythm — Evaluation:** Three backtest layers (scoping accuracy, build quality, taste calibration). No pilot groups. Historical builds as ground truth.

**Right Effort — Cost:** Opus 4.6 at $5/$25 per 1M tokens. 100 users × 4 builds/month = ~$400/month compute. $49/user subscription = $4,900 MRR. 92% gross margin. Key tradeoff: Opus is 5x pricier than Sonnet, but cheap reasoning breaks the coordination.

### Deck Iterations

The deck went through four versions, each driven by the user's taste:

1. **v1:** Managerial-comms reading deck with full content. User rejected: "too fucking wordy."
2. **v2:** Stripped to Steve Jobs minimal — big text, icons, no paragraphs. User approved the energy.
3. **v3:** User introduced the Founding Agent metaphor (inspired by Attack on Titan's Founding Titan — coordination as power, not raw strength). Rebranded from "Creator Agent" to "The Founding Agent." User caught a stray "titan" reference and flagged it — agent terminology only, no anime terminology in the final product.
4. **v4 (final):** Merged back to managerial-comms reading deck with Founding Agent threading and action titles. User's reasoning: "Manzoor needs to be able to read it and know wtf is going on too." The minimal version was presentation-only; the reading deck works as a leave-behind.

A conceptual UI mockup was built as an HTML page and screenshotted into the deck, showing the agent mid-build on a real project (the JJC karaoke lottery tool). This grounded the architecture slides in something tangible.

### Video Script

Written using writing-style principles (classic style, show don't argue, kill metadiscourse). Opens with a cold take on the vibe coding era — "speed without direction produces beautiful garbage faster" — before any slides appear. The user noted they would edit the script to make it more their voice. This is consistent with the Surface layer's role: shape communication, don't override the communicator's identity.

### Rubric Audit

Final deck audited against every rubric requirement:

- Title + name: ✅
- Business problem + who benefits: ✅
- AI problem + why AI: ✅
- Why not just prompt ChatGPT: ✅
- Data needed: ✅ (added after audit caught the gap)
- Evaluation without pilot groups: ✅
- Trust/transparency pattern: ✅
- Architecture (context + tools): ✅
- Concept map (all 6 concepts): ✅
- Cost for 100 users: ✅
- Revenue vs. cost + tradeoffs: ✅

The data requirement was the only gap caught during audit. It was patched into the AI problem slide before final export.

---

## Lessons

**1. Multiple Kamae resets are not failure — they're taste at work.** Five rejections before a pain statement stuck looks expensive. But each rejection took minutes, and any of the rejected scopes would have produced a mediocre presentation. KKSK's gates gave the user permission to say "this isn't it" without losing structure.

**2. The user's taste is the scoping instrument.** In prior case studies (JJC landing page, GreenGami), Kamae's failure test caught bad pain statements. Here, the failure test never triggered — the pain statements were technically valid. The user's gut rejected them anyway. KKSK accommodated this because the gate requires user confirmation, not just passing the failure test. The framework held even when the diagnostic was "this doesn't feel right."

**3. SSS prevented skill competition.** Four skills applied to one deliverable. Without SSS sequencing, managerial-comms would have dominated (it's the most template-heavy). Instead, KKSK scoped first, 4R built substance within those constraints, and managerial-comms + writing-style formatted last. Each skill operated in its lane.

**4. The deck iteration pattern mirrors KKSK's own philosophy.** Four deck versions, each rejected and rebuilt. Position before submission: the user established what the deck needed to *do* (reading deck for Manzoor, Founding Agent metaphor, rubric compliance) before committing to how it looked. The visual pivots were transitions, not resets, because the scope never changed.

**5. The meta-irony is the point.** The Founding Agent pitch was itself built using the Founding Agent methodology — KKSK scoped it, 4R structured it, managerial-comms formatted it, the user's taste gated every phase. The presentation is a live case study of its own thesis. This wasn't planned. It emerged because the framework works.
