# KKSK Case Study: GreenGami Strategy Questionnaire

A real-world application of KKSK to a strategic deliverable rather than a code build. This case demonstrates how KKSK catches position-reading failures in business communication, and why the Wedge Test is the skill's most important mechanism. The failure in v1 was not a knowledge gap or a reasoning error. It was a position mismatch: the output claimed attacks the team's position did not support.

## Context

FusionFive is a four-person team of Cornell materials science students (MSE 4072) building GreenGami, a sustainable acoustic panel that upcycles spent diatomaceous earth (SDE) waste from breweries. The team had a prototype review handout documenting their DFMEA, House of Quality, calcination optimization matrix (18 conditions), panel composition test plan (54 formulations), custom impedance tube design, and consumer research findings.

Cornell's SC Johnson College of Business Startup Mentors Program issued a questionnaire: 12 due-diligence questions that a VC evaluator would ask a technology startup. An MBA mentor was advising the team and asked Claude to answer the questionnaire using multiple skills (SSS, KKSK, 4R, managerial-comms) applied to the prototype handout.

The SSS skill sequenced the work: KKSK as Scope, 4R as Substance, managerial-comms as Surface. This case study focuses on the KKSK layer because it drove the most consequential decision.

---

## The Setup: What Made This Hard

The questionnaire was designed for startups. It asks about customers, market share, funding requirements, exit options. FusionFive is not a startup. They are undergrad materials scientists running a prototype validation in a course lab. But the questionnaire doesn't care about that. It asks its questions regardless of where you are.

This creates a trap. The natural response is to answer every question as if you're a real company, because the questions assume you are one. The pain is real (VOC-emitting foam panels, $0.85B market, sustainability gap). The technology is novel (SDE waste upcycling, origami surface geometry, dual-scale innovation). The experimental design is rigorous (systematic DOE, DFMEA-driven test plan, House of Quality). There is enough real substance to write a convincing pitch.

The trap is that "convincing" and "honest" are not the same thing. And evaluators can tell the difference.

---

## V1: The Position-Reading Failure

### Kamae

The initial pain statement was technically correct:

> "Health-conscious building managers and architectural firms lose design credibility and face regulatory risk by installing VOC-emitting foam acoustic panels because no sustainable alternative exists that matches foam's acoustic performance at commercial scale."

This passed Kamae's failure test. No consultant words. Specific who (building managers, architectural firms). Quantified cost (design credibility, regulatory risk). Named task (installing acoustic panels). Root cause (no sustainable alternative at performance parity). The statement was real.

### Wedge Test (v1)

1. **Who has this at 10x intensity?** LEED/WELL-certified commercial construction projects where VOC compliance is a hard gate, not a preference. These buyers face real penalties for non-compliance.
2. **One dimension of advantage?** Genuine waste-stream upcycling combined with competitive acoustic performance. No competitor occupies this position.
3. **Saying no to?** Individual consumers, residential installations, aesthetic-first buyers.

These answers were also technically correct. They described a real market wedge that a real company could pursue.

### The Problem

Every downstream answer followed the wedge's logic. Customer became "specification managers at mid-to-large commercial construction firms." Market share became "$3.4M–$10M SOM within 3–5 years." Funding became "$150K seed round" with a detailed use-of-funds table. Exit became "acquisition by Armstrong or Owens Corning." Manufacturing became "contract manufacturing model scales without heavy capital investment." The document read like a Series Seed pitch deck.

The evaluators would have read it and immediately seen the gap. This team has no NRC data. They haven't measured acoustic performance. They haven't talked to a single architectural firm. They haven't tested fire resistance. They haven't validated that waste SDE can even match foam. Every confident market claim was built on a foundation that didn't exist yet.

**V1 was a white belt move: lunging for the armbar from a position that doesn't support it.**

---

## The Correction

The mentor came back with one sentence: "The new context is that these students just want to prototype, then the project goes to market."

This is the kind of feedback that, without a framework, gets handled as a tone adjustment. Make it sound less aggressive. Add some hedging language. Soften the funding ask. That would have been a Surface fix applied to a Scope problem.

SSS prevented that. The protocol requires rerunning the pipeline from Scope, not patching from Surface. So KKSK ran again.

---

## V2: Reading the Actual Position

### Kamae (Unchanged)

The pain statement didn't change. The pain is real regardless of who is trying to solve it:

> "Health-conscious building managers and architectural firms lose design credibility and face regulatory risk by installing VOC-emitting foam acoustic panels because no sustainable alternative exists that matches foam's acoustic performance at commercial scale."

The falsification test still holds. No evidence that the pain is fake. VOC regulations are tightening. The market gap is documented. This was never the problem.

### Wedge Test (v2) — Where Everything Changed

1. **Who has this at 10x intensity?** The team itself. They need to know whether waste SDE achieves competitive NRC before anything else matters. The prototype gate is the point of maximum desperation: if the answer is no, the entire concept collapses. If yes, every commercial question becomes addressable.
2. **One dimension of advantage?** Experimental rigor. The team has a systematic DFMEA, a House of Quality, a structured DOE (18 calcination conditions, 54 composition formulations, custom impedance tube). Their advantage is not a product; it is a well-designed experiment that will produce a definitive answer.
3. **Saying no to?** Claiming market share they can't substantiate. Presenting unit economics they haven't validated. Describing customer relationships they haven't built. Requesting funding for a company that doesn't exist.

**The wedge shifted from a market segment to the prototype gate itself.**

This single reframe cascaded through every answer:

| Question | V1 Answer (Wrong Wedge) | V2 Answer (Correct Wedge) |
|---|---|---|
| Customer | Specification managers at commercial construction firms | Hypothesized B2B buyers, contingent on prototype results |
| Market share | $3.4M–$10M SOM in 3–5 years | Speculative at this stage; market position is currently empty if performance validates |
| Funding | $150K seed round with detailed allocation | University-funded now; $150K estimated if commercialized |
| Exit | Acquisition by Armstrong/Owens Corning | Entirely contingent on prototype results |
| Manufacturing | Contract manufacturing model | Standard industrial processes; scalability depends on prototype |
| IP | Provisional patent planned | Process knowledge is primary IP; formal protection depends on results |
| Team | Complementary technical expertise | Strong prototype capability; business development is the gap |

Every V2 answer drew its confidence from what the team actually had (experimental design, materials characterization, systematic test plans) and drew its humility from what they didn't (NRC data, customer interviews, manufacturing cost validation). V1 drew confidence from the market opportunity and hid the missing prototype results. V2 was honest. V1 was aspirational.

---

## Why the Wedge Test Is the Mechanism

The Wedge Test caught something that the pain statement alone could not. The pain was correct in both versions. If you only had Kamae, v1 would have passed. The error was not in identifying the wrong pain. It was in identifying the wrong point of maximum desperation.

The Wedge Test's first question ("who has this at 10x intensity?") is usually interpreted as a market question: which customer segment is most desperate for your solution? That interpretation works when you're an operating company with a product. But the question is more general than that. It asks: where is the desperation concentrated right now? For a prototype-stage team, the desperation is internal. They need to know if the technology works. The evaluators need to see that the team knows they need to know. Claiming commercial certainty before answering the feasibility question isn't confidence; it's evasion.

The third question ("what are you saying no to?") did the sharpest work. V1's exclusion list was cosmetic: no individual consumers, no residential installs, no aesthetic-first buyers. These are segments the team was never going to pursue anyway. Saying no to them cost nothing.

V2's exclusion list was painful: no market share claims, no unit economics, no customer relationships, no funding requests. These are things the questionnaire explicitly asks for. Saying no to them required writing answers that said "we don't know yet, and here's why that's the right answer." That took more discipline than writing a confident number.

**The Wedge Test works because it makes cheap exclusions visible.** If your "saying no to" list doesn't hurt, you haven't actually narrowed anything. V1's exclusions were free. V2's exclusions cost the document its most impressive-sounding claims. That's how you know the wedge is real.

---

## The BJJ Principle in Action

The skill's deepest principle is "read the position and take what it gives you." This case is the clearest illustration of what that means outside of a grappling context.

**The team's position:** Innovation Level II. No NRC data. Rigorous experimental design. Systematic DFMEA and HoQ. 18 calcination conditions running. 54 composition formulations planned. Custom impedance tube under construction. Preliminary consumer surveys completed.

**What the position gives you:**
- "We designed a rigorous experiment that will definitively answer whether this technology works."
- "Our failure mode analysis identifies exactly what could go wrong and our test plan addresses each mode."
- "Consumer research confirms the market values what we're building, contingent on performance."
- "Here's what commercialization would look like if the prototype validates."

**What the position does not give you:**
- "Our product achieves competitive NRC ratings." (Not measured yet.)
- "We project $3.4M–$10M in revenue." (No basis for the estimate.)
- "Architectural firms will specify our product." (Never talked to one.)
- "We need $150K to scale." (Nothing to scale yet.)

V1 took what the position did not give. V2 took what the position gave. The document worked almost as-is because the claims matched the evidence. The evaluators could trust it.

This is the BJJ principle operating at a strategic level. In grappling, a white belt sees an armbar opening and lunges for it from half guard. A black belt recognizes that the arm is available but the position doesn't support the finish. The black belt improves position first, and the finish becomes available later. V1 lunged for the commercial finish from a prototype position. V2 established the prototype position and let the commercial possibilities follow naturally as "if this works, here's what opens up."

The deeper insight: every failed attack from a bad position costs you. In grappling, you lose position. In a strategy document, you lose credibility. The evaluators reading v1 would not have thought "this team has a great go-to-market plan." They would have thought "this team doesn't know what they don't know." The aggressive claims would have undermined the genuinely impressive experimental work. V2 protected the team's credibility by not overclaiming, which made the claims they did make more persuasive.

---

## What KKSK Prevented

Without KKSK's sequential gates and the Wedge Test specifically, the likely failure mode was a Surface fix to a Scope problem. The mentor's feedback ("they just want to prototype") would have been interpreted as "soften the tone." The same overclaimed content would have been wrapped in more hedging language: "we believe," "we anticipate," "preliminary estimates suggest." The structure and claims would have stayed the same. The evaluators would have seen through it.

KKSK forced a Scope rerun, not a Surface patch. The Wedge Test's three questions, answered honestly in the new context, changed the constraint document. The constraint document changed every answer. The answers changed the document's credibility.

---

## Failure Modes Exercised

**1. The Rubber-Stamp Scope (v1).** The constraint document existed (pain statement, wedge test, exclusions) but didn't actually constrain anything. Every answer would have been the same without it. Test: did Scope cause anything to be cut? In v1, no. In v2, Scope cut market share projections, unit economics, the funding ask framing, and customer certainty. That's how you know v2's scope was real.

**2. The Sympathetic Audience (v1, partial).** The wedge identified buyers who would agree the pain exists (sustainability-minded architects) but who the team has never spoken with. V1 treated survey agreement as customer validation. V2 correctly labeled it: "The team has survey data on what consumers say they value, but no direct evidence of willingness to pay from the specific B2B buyer persona." Nodding is not adoption. Survey data is not purchase orders.

---

## How This Case Differs from the JJC Case

The JJC case study shows KKSK scoping a code build. The failure mode was feature bloat (marketing toolkit → single landing page). Kamae caught consultant words. Sasoi caught a Compound Sasoi. The pivot was functional: wrong tool for the wrong audience → right tool for the right audience.

The GreenGami case shows KKSK scoping a strategic deliverable. The failure mode was position mismatch (prototype team → startup pitch). Kamae was correct in both versions. The Wedge Test caught the error. The pivot was not functional but positional: the "one function" was the same (answer the questionnaire), but the position from which it was answered changed everything.

This makes the GreenGami case a better illustration of KKSK's deepest principle. In the JJC case, the framework caught a scoping error. In the GreenGami case, the framework caught a position-reading error. The first is about what to build. The second is about where you're building from. Both are KKSK's domain, but the second is the harder lesson and the one that BJJ practitioners recognize immediately: the same attack from two different positions produces completely different results.

---

## Key Takeaways

1. **The Wedge Test is the skill's most important mechanism.** Kamae was correct in both versions. The pain was real. The Wedge Test caught the error because it asks a different question: not "is the pain real" but "where is the desperation concentrated right now." For a prototype team, the desperation is at the feasibility gate, not in the market.

2. **Cheap exclusions are a signal that Scope isn't working.** If "saying no to" doesn't hurt, you haven't actually narrowed. V1 excluded customer segments the team was never going to pursue. V2 excluded the document's most impressive-sounding claims. The pain of the exclusion is the evidence that the wedge is real.

3. **"Read the position and take what it gives you" applies to communication, not just code.** The team's position gave them experimental rigor and systematic design. It did not give them commercial certainty. V1 ignored the position and claimed what it didn't support. V2 read the position and built every answer from what the team actually had. The document worked because the claims matched the evidence.

4. **A Surface fix cannot solve a Scope problem.** Adding hedging language to overclaimed content doesn't fix it. The evaluators can tell the difference between "we project $3.4M–$10M SOM" with "preliminary" in front of it and "market share projections would be speculative at this stage." The first is a confident claim wearing a disclaimer costume. The second is an honest assessment. KKSK forces the honest version by rerunning Scope, not patching Surface.

5. **KKSK works on strategic deliverables, not just code.** The framework was designed for vibe coding. This case proves it generalizes. The phases (identify the pain, study the workaround, isolate the function, execute and measure) map onto any scoping problem. The Wedge Test (who is desperate, what's your one dimension, what are you refusing) maps onto any positioning problem. The BJJ principle (position determines available attacks) maps onto any communication problem. The mechanism is the same: sequential gates with concrete outputs that prevent you from skipping the setup and lunging for the finish.
