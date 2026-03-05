# KKSK Case Study: JJC Event Landing Page

A real-world application of the KKSK framework to build a branded event landing page for the Johnson Japan Club (JJC) at Cornell's SC Johnson College of Business. Built on KKSK v1 — patterns now codified in the Failure Modes section (the Fake Kamae, the Compound Sasoi pivot) emerged naturally here before they were named.

## Context

The JJC treasurer — the only PM on the board with shipping experience — wanted to "build something for marketing." Without KKSK, this would have become a feature-bloated marketing toolkit. With KKSK, it became a single-purpose landing page that the entire board got excited about within hours of seeing it.

---

## Phase 1: Kamae — Establish Position

**Starting pain statement:** "JJC loses opportunity to host events doing not being able to market and shape demand for events because other than posting on CampusGroups there's very little room for marketing creativity."

**Problem identified:** This statement contained consultant words ("shape demand," "marketing creativity") that hid the absence of a specific problem. Kamae's failure test caught it — this was a Fake Kamae.

**Sharpening process:** Five diagnostic questions were asked to quantify the pain, map the current process, identify the audience, and distinguish between a reach problem vs. a value proposition problem.

**Key discoveries:**
- JJC has use-it-or-lose-it funding. If funds aren't spent on well-attended events, the club gets demoted a tier and loses budget the following year.
- Ticket revenue ($6-10/person) converts allocated funds into discretionary funds, but PayPal fees require tickets to be at least $6 to generate profit.
- JJC is historically a secondary/tertiary club competing against larger affinity groups on the same platform (CampusGroups).
- The new board wants to break out of this reputation but has no brand identity, no marketing infrastructure, and no differentiation.

**Final pain statement:**
> "JJC e-board loses allocated funding (tier demotion risk) because they can't make standard events (sushi night, karaoke) compelling enough on CampusGroups to win 20+ paid attendees away from competing events on the same nights."

**Why this matters:** The original framing ("marketing creativity") would have led to a generic content creation tool. The sharpened statement revealed the real problem: a funding death spiral driven by inability to compete for attention on a noisy platform. This reframing changed everything downstream.

### Wedge Test

1. **10x audience:** JJC e-board members responsible for event attendance who risk losing club funding tier.
2. **One dimension:** First-impression quality — making a standard event feel premium before anyone clicks through to CampusGroups.
3. **Saying no to:** Not building for attendees who are already in the JJC pipeline. Not building a CRM, ticketing system, or general marketing platform.

---

## Phase 2: Kuzushi — Study the Workaround

**Current workflow documented:**

1. E-board decides on an event (sushi night, karaoke, etc.)
2. Someone makes a generic AI-generated graphic in Copilot/Canva
3. Post goes up on CampusGroups + Instagram + WhatsApp + word of mouth
4. Timing is ad hoc — no strategy on when to post or how far in advance
5. People pay through CampusGroups → PayPal
6. Hope for 20+ people to show up

**Bottleneck identified:** Steps 2 and 3. The creative asset is generic and forgettable. There is no campaign tempo, no buildup, no urgency. The entire "marketing process" is a single post and a prayer.

**Key insight:** 80% of the friction concentrated in the quality of the first impression and the lack of a persuasion sequence. The events themselves (karaoke, sushi night) are solid. The problem is presentation, not product.

---

## Phase 3: Sasoi — Isolate the Function

**First attempt (wrong):**

```
generate_event_campaign(event_brief) → marketing_kit
```

This function would take event details and output copy for CampusGroups, Instagram, WhatsApp, and a flyer concept. It was scoped as a multi-channel copy generator for the e-board to use internally.

**The pivot:** The user rejected this scope. Their insight: "Instead of user clicking CampusGroups and seeing all other competing things, they click our link. It's interactive, customized to JJC feel and image, and presented like an actual enticing event. Then the CampusGroups link is there once they're ready to pay."

This reframed the entire function. The tool isn't for the e-board (internal) — it's for potential attendees (external). The core transformation changed from "generate marketing copy" to "replace the first touchpoint." The first attempt was a Compound Sasoi: it was trying to serve two audiences in one function.

**Final function:**

```
generate_event_page(event_brief) → branded_landing_page
```

- **Input:** event name, date, time, location, price, what's included, vibe/theme
- **Output:** a single interactive HTML page with JJC branding that sells the event and funnels to CampusGroups for payment

**Why Sasoi worked here:** The one-function discipline forced a choice between building a tool for the e-board vs. a tool for attendees. The user's taste and judgment made the right call: attendees are the bottleneck, not the e-board's copywriting process. Sasoi's constraint ("if you can't express it as one function, you're building too much") prevented bundling both concerns into one bloated project.

---

## Phase 4: Kime — Execute and Measure

**Build sequence:**

1. **V1:** Clean, Japanese-inspired landing page with Sell-style persuasion funnel (hook → details → inclusions → social proof → CTA). Washi paper texture, vermillion red accent, Noto Serif JP typography. Functional but static.
2. **V2 (user-driven upgrade):** User requested "Apple product page" feel with interactive scroll. Rebuilt with cinematic dark hero, gradient orbs, preloader, parallax kanji, dark-to-light gradient transitions, sticky experience showcase, staggered scroll reveal animations, shimmer CTA button. Same function, elevated execution.
3. **Config page:** Built a no-code visual editor so the board could customize colors, copy, and sections without touching code. Live preview, color presets (Sakura, Matcha, Midnight Blue), device preview toggle, one-click HTML export.
4. **Board communication:** Used managerial-comms framework to draft the board message. Assessed credibility (high: only PM on board who ships), chose Sell style with direct approach, and crafted a group text that presented the work and invited iteration, not permission.

**Done condition:** The JJC board shares the landing page link instead of a raw CampusGroups link, and paid attendance hits 20+ for the first time.

**Early signal:** Board responded with excitement within hours. The quote copy needs work (board feedback), but the architecture, branding, and vision landed. This is a positive Kime indicator — the structure is right, the details are tunable.

**Note:** V1 to V2 was not scope creep — it was execution refinement on the same function. The Apple-level upgrade didn't change what the page does (sell an event, funnel to payment). It changed how well it does it. Iteration on quality within the same function signature is encouraged.

---

## What KKSK Prevented

Without KKSK, the likely outcomes were:

- **"Full-stack event management app"** with auth, attendee tracking, notifications, payment processing, and a dashboard. Months of work, zero adoption.
- **"Marketing automation platform"** that generates copy for five channels, schedules posts, and tracks engagement. Over-engineered for a club with 20 attendees.
- **"JJC website redesign"** with an about page, team bios, event calendar, blog, and contact form. A beautiful artifact that doesn't solve the attendance problem.

KKSK compressed all of that into: one HTML file, one function (event brief → landing page), one measurable outcome (20+ paid attendees). Total build time: one session.

---

## Follow-On Cycles

KKSK's exit rule asks: does the next pain touch this function's output?

The board identified two follow-on opportunities:

1. **Campaign timing/sequencing:** when to post, where, what cadence. This touches the landing page's output (it needs traffic to convert). → Run KKSK again.
2. **Brand identity development:** the board wants to co-create JJC's visual identity. The config page enables this without a new build cycle.

Both are natural KKSK follow-ons, not scope creep. The first function proved itself; now the next cycle can begin.

---

## Key Takeaways

1. **Kamae's failure test is the most valuable gate.** Catching "shape demand" and "marketing creativity" early prevented weeks of building the wrong thing. If the pain statement sounds like a consulting deck, push harder.
2. **Sasoi pivots are features, not failures.** The initial function (copy generator) was reasonable but wrong. The user's taste caught it. Sasoi's one-function constraint made the pivot clean because there was only one thing to change, not an architecture to unwind.
3. **Kime can iterate within scope.** V1 to V2 was execution refinement on the same function signature. KKSK encourages quality iteration within scope — the boundary is the function, not the fidelity.
4. **The framework is necessary but not sufficient.** KKSK prevented the wrong build and structured the right one. But the key decisions (landing page over copy generator, Apple-level quality, board communication strategy) came from the user's taste and judgment. Frameworks are guardrails and accelerators. The limiting factor is always the person.
