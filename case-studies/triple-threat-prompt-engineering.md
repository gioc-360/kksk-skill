# KKSK Case Study: Triple Threat Prompt Engineering

A real-world application of KKSK to a non-code deliverable: a prompt string for gpt-4o-mini. The build target was natural language engineering, not software. This case demonstrates KKSK working outside its original domain (vibe coding) and introduces a new constraint type: model capability ceilings as immovable boundaries that scoping must respect rather than fight.

## Context

NBA 4920/6921 Homework 2 (Professor Manzoor, Cornell). The assignment: engineer a prompt that makes GPT play Triple Threat — a 4x4 board game where 3-in-a-row wins but 4-in-a-row loses. The prompt must output the winning move as `row,col`. Evaluated on 5 test boards using gpt-4o-mini at temperature=1. Solo submission with KKSK (scope), 4R (execution), and managerial-comms (surface) as teammates.

The deliverable is not code. It's a string. But it has a function signature, measurable output, and iterative refinement — all KKSK territory.

---

## Phase 1: Kamae — Establish Position

**First attempt at pain statement:** "GPT doesn't play Triple Threat correctly."

**Problem:** This is a symptom description, not a pain statement. It doesn't identify who, how much, what task, or root cause. Kamae's failure test caught it.

**Diagnostic process:** Instead of jumping to prompt writing, the pain was sharpened by asking: what specifically does GPT get wrong, and why?

Three root causes were identified before writing a single prompt:

1. **The Inversion Problem.** Every game in GPT's training data rewards longer sequences. Triple Threat punishes them. The model's strongest prior is exactly backwards on the critical edge case.
2. **ASCII Parsing.** Pipe characters and whitespace in the board representation create ambiguous cell boundaries during tokenization. The model misreads which cells are occupied.
3. **Diagonal Blindness.** A 4x4 board has eight length-3 diagonals. The model only checks the two main diagonals and misses the six off-diagonals.

**Final pain statement:**
> "GPT (gpt-4o-mini) loses 60-80% of Triple Threat puzzles because its training prior treats 4-in-a-row as success, it can't parse ASCII board art reliably, and it doesn't know the diagonal geometry of a 4x4 grid."

**Why this matters:** The original framing ("doesn't play correctly") would have led to a generic "be smarter about the game" prompt. The sharpened diagnosis revealed three distinct failure modes, each requiring a different fix. Every prompt version that worked addressed a specific diagnosed failure. Every version that failed tried to fix something not on this list.

### Wedge Test

1. **10x intensity:** The 5 test boards in the assignment spreadsheet. These are the "users" who are desperate — the prompt must work on them or it fails.
2. **One dimension:** Structured output that constrains the model's reasoning path. Not "better reasoning" (can't control that) but "less room to reason wrong."
3. **Saying no to:** Multi-turn prompting. Tool use. Code interpreter. System prompt tricks. Changing the model. All out of scope — the deliverable is a single user-message prompt string.

---

## Phase 2: Kuzushi — Study the Workaround

**Current workflow (the baseline prompt):**

```
Below is a Triple Threat game being played between player X and player O,
what should be the next move for player X?

{board}

Response (row and column number separated by a comma):
```

This is the assignment's starter prompt. It scores ~20% — the model guesses randomly.

**Bottleneck identified:** The prompt provides zero structure for reasoning. The model receives an ASCII board and must simultaneously: parse it, understand the rules, find candidate moves, evaluate them, check for loss conditions, and format the output. All in one unguided pass. 80%+ of the failure concentrates in the reasoning step — the model finds plausible-looking moves without checking loss conditions or diagonals.

**Key insight:** The workaround IS the spec. The starter prompt shows what the model gets: a board and a question. The prompt engineer's job is to insert enough structure between the board and the answer that each reasoning step is constrained to something gpt-4o-mini can actually do.

---

## Phase 3: Sasoi — Isolate the Function

```
find_winning_move(ascii_board: str) → "row,col"
```

- **Input:** ASCII board string with pipe-separated cells
- **Output:** Three characters: row digit, comma, column digit

**Why Sasoi was easy here:** The assignment defined the function. The constraint is the prompt string that makes gpt-4o-mini execute it correctly.

**The real Sasoi question:** What is the one transformation the prompt performs? Not "make GPT play the game" — that's too broad. The one transformation:

```
convert_open_ended_game_query(board) → structured_line_checking_table(board) → winning_cell
```

The prompt's job is to convert an open-ended "what's the best move?" into a structured table-filling task that gpt-4o-mini can execute as pattern completion rather than spatial reasoning.

---

## Phase 4: Kime — Execute and Measure

### Iteration Log

Eight prompt versions. Each tested one hypothesis. Measured on 5 test boards.

**v1 (20%): Zero-shot + CoT + worked example.** Full rules, four reasoning steps, worked example from the assignment. Failed on parsing AND game logic simultaneously. Learned: two compounding failures must be isolated, not fixed together.

**v2 (40%): Line enumeration, no reasoning.** Listed all lines, told model to output answer only. Accuracy doubled because the model stopped making long reasoning errors. But no verification = coin-flipping on hard boards.

**v3 (0%): Line enumeration + forced CoT.** Combined v2's lines with v1's reasoning. Information overload — the model made up its own lines instead of reading the table. **Critical learning: longer prompts make gpt-4o-mini worse, not better.**

**v4 (20%): Inverted search.** Told model to find lines where X has 2 marks, then complete them. Model found correct candidates then talked itself out of answers in the same paragraph. Self-contradiction is the defining failure mode of temperature=1.

**v5 (40-60%): Table fill-in format.** The structural breakthrough. Grid template + table of all 24 lines as fill-in-the-blank. Pattern completion instead of open reasoning. At temperature=0, consistently hit 60%. Two specific boards always failed:
- Board 4: model checked diagonal but forgot to substitute the new X
- Board 5: model wrote "X, empty, X" then counted it as "1 X"

**v6 (40%): Pattern matching rules.** Added explicit pattern instructions. Confused the model into new false positives. Reverted.

**v7 (80%): Detection + forced substitution.** 4R-driven surgical fix (see below). Changed "count 2 X's" to "no O's and one empty" (detection replaces counting). Added "replace the empty with X, then write out the line" (forced substitution replaces mental evaluation). Two changes, both targeting diagnosed failures. Hit 80%.

### The 4R Handoff (v5 → v7)

After v5+temp=0 plateaued at 60%, 4R was invoked for the final push. Full 4R write-up is in `4r/case-studies/triple-threat-prompt-engineering.md`.

**Right View:** Riskiest assumption — "gpt-4o-mini can count non-adjacent X's in a sequence." Falsified by Board 5: the model writes "X, empty, X" and labels it "1 X" every run.

**Right Build:** Two surgical changes to v5. No rewrite.

**Right Rhythm:** One increment. Done condition: >60% on the same 5 boards.

**Right Effort:** Prompt craft (Gio) for the specific wording. 4R for the diagnosis of what to change.

**Result:** 60% → 80%. Total 4R cycle: ~10 minutes.

### The Ceiling

The same v7 prompt achieves 100% on o1. The 20% gap on gpt-4o-mini is a model capability ceiling:

1. gpt-4o-mini cannot reliably count non-adjacent items in a sequence
2. gpt-4o-mini cannot reliably perform mental substitution (placing a hypothetical X and re-evaluating)
3. Temperature=1 amplifies both failures through sampling noise

These are architectural constraints, not scope or build failures. KKSK's Kamae diagnosed the pain correctly. 4R's Right View confirmed the implementation limits. The prompt's job is to minimize cognitive load per step — and at 80%, it's within one board of the model's ceiling.

---

## What KKSK Prevented

Without KKSK, the likely outcomes were:

- **"Make GPT smarter at the game"** — a vague prompt with more rules, more examples, more instructions. v3 proved this approach scores 0%.
- **"Use a different model"** — out of scope. The assignment constrains the model.
- **"Add code execution"** — the model evaluates the board programmatically. Out of scope (deliverable is a prompt string).
- **Endless iteration without diagnosis** — changing random things and hoping accuracy improves. KKSK's Kamae forced the diagnosis first, so every version tested a specific hypothesis.

KKSK compressed the work into: one function (find_winning_move), three diagnosed failure modes (inversion, parsing, diagonals), and a measurable outcome (accuracy on 5 boards). Total prompt: ~400 tokens. Total iterations: 8 (each with a reason).

---

## What's New in This Case Study

This case extends KKSK in three ways not covered by the JJC or GreenGami case studies:

1. **Non-code deliverable.** The "build" is a prompt string, not a script or a landing page. KKSK's phases still apply: Kamae diagnosed the pain, Kuzushi mapped the baseline, Sasoi defined the function, Kime iterated to 80%. The framework is domain-agnostic.

2. **Model capability ceiling as a constraint.** Previous case studies had human-imposed constraints (budget, timeline, audience). This one has an architectural constraint: the model literally cannot perform certain operations (counting non-adjacent items, mental substitution). Kamae must diagnose which failures are addressable by prompting and which are model limits. 4R's Right View confirmed the ceiling.

3. **Measured iteration with regression.** v3 scored 0% — worse than the baseline. v6 scored 40% — worse than v5. Not every iteration improves. KKSK's one-hypothesis-per-version discipline made regressions diagnosable: v3 failed because the prompt was too long (testable), not because "the approach didn't work" (vague).

---

## Key Takeaways

1. **Kamae's diagnosis drove every iteration.** The three failure modes (inversion, parsing, diagonals) were identified before writing a single prompt. Every version that improved addressed one of them. Every version that regressed violated a constraint they implied (e.g., "shorter is better for mini").

2. **Sasoi works for non-code functions.** `find_winning_move(board) → "row,col"` is a valid function signature even though the implementation is a natural language prompt. The one-function discipline prevented scope creep into multi-turn, tool-use, or system-prompt approaches.

3. **The ceiling is not a failure.** 80% on gpt-4o-mini with 100% on o1 using the same prompt proves the prompt is correct. The remaining 20% is a model constraint, not a scope or build error. KKSK doesn't promise 100% — it promises you're solving the right problem. The right problem here was "maximize accuracy within model limits," not "achieve perfection."

4. **4R as a mid-project handoff.** KKSK scoped the problem (v1). Iteration found the structure (v5). 4R diagnosed the last two failures and made surgical fixes (v7). The KKSK → 4R handoff happened mid-project, not at the start. This is the natural rhythm: scope until you have a working baseline, then switch to execution discipline for the refinement push.
