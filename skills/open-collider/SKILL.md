---
name: open-collider
description: Idea generation engine using controlled collisions between structurally distant domains (Open Collider / Koestler bisociation protocol). Escapes the Artificial Hivemind — the LLM tendency to converge on the training distribution's dense center. Generates a domain bank of 5–7 distant domains with specific named references, runs isolated collisions plus one cross-domain collision, applies 3-filter curation, returns a ranked pool. MANDATORY TRIGGERS — open collider, bisociation, cross-domain prompting, domain bank, escape hivemind, non-trivial ideas, brainstorm with AI, generate original ideas, beat the obvious, distant domain collision, Koestler bisociation, lateral thinking with AI, generate angles, generate theses, generate hooks, ideation brief, idea pool. Use when the brief is open-ended, when previous output felt generic, or when originality is explicitly required. DO NOT use when the brief has a strong thesis and needs convergence, for fact-checking, or for editing tasks.
---

# OPEN COLLIDER — Controlled Collision Ideation Engine

> Version: 1.0 (generic)
> Based on: CL-ML, "Escape the Artificial Hivemind" (2026) + Koestler, *The Act of Creation* (1964)
> Status: protocol validated empirically by the original paper (12 projects, ~23k ideas, 4320 pairwise judgments).

---

## 1. When to use

**USE when:**
- Open-ended ideation brief with no pre-defined thesis
- Previous output felt generic, obvious, or "sounded like any LLM"
- User explicitly asks for "different ideas" / "non-obvious" / "outside the cliché"
- Generating theses for essays, articles, or research
- Generating angles for content, marketing, or product
- Brainstorming hooks that need to break through saturated noise
- Any creative or strategic task where the default LLM answer is predictable

**DO NOT use when:**
- The brief already has a strong thesis and needs convergence
- High-intent conversion copy (use focused copywriting tools)
- Fact-checking, editing, QA
- Tasks with hard token constraints — this skill is expensive by design

---

## 2. Mechanism (paper summary)

**Artificial Hivemind:** LLMs converge on the dense center of the training distribution. Adding more in-domain context or asking the model to "be original" barely moves the output (measured effect: 4–13× smaller than collision-based prompting).

**Bisociation (Koestler):** a genuinely new idea emerges from the collision between two distant frames of reference — specifically, when a *hidden dimension of proximity* between them is discovered (e.g. parasitology × platform economics → shared mechanism of behavioral redirection for asymmetric benefit).

**Counterintuitive move:** inject *less related* material, not more related material. Volume + curation compensate for the inevitable noise.

---

## 3. Protocol (5 stages)

### Stage 1 — Briefing

Elicit from the user (or accept if already provided):

- **Ideation problem:** what is the open question?
- **"Good idea" criterion:** what validates an idea? (pure originality, operational feasibility, voice fit, etc.)
- **Non-negotiable constraints:** what must be present or absent?
- **Output destination:** what does this feed into? (essay, campaign, product, research)
- **Desired volume:** how many curated ideas at the end? (default: 10)

### Stage 2 — Generate Domain Bank

Produce 5–7 **structurally distant** domains from the brief. Each domain is described as:

```
DOMAIN N: [domain name + SPECIFIC NAMED REFERENCE]
  Persona: [hypothetical specialist of that field]
  Counterintuitive mechanism: [the non-obvious rule/dynamic of that field]
  Bridge question: [question that forces a bridge to the brief]
```

**CRITICAL RULE:** each domain needs a **specific named reference** — a historical case, named species, dated event, real person, specific work. A generic domain produces decorative analogy; a specific reference produces operational mechanism.

- ❌ Weak: "Aviation"
- ✅ Strong: "Aviation — Air France 447 accident (2009)"
- ❌ Weak: "Art forgery"
- ✅ Strong: "Art forgery — Han van Meegeren, Wolfgang Beltracchi"
- ❌ Weak: "Catholic liturgy"
- ✅ Strong: "Catholic liturgy after Vatican II (1962–65)"

**Distance criteria:**
- Different vocabulary
- Different historical/cultural context
- Different temporal scale (microbiology × geology × fashion cycle)
- Different discipline (engineering × ritual × botany × jurisprudence)

**Anti-pattern:** avoid domains that are "close cousins" in disguise (e.g. marketing × advertising × branding = same zone). Seek genuine *outsiders*.

### Stage 3 — Collisions in isolated contexts

For each (brief × domain), generate 15–20 ideas in a **dedicated block**, with explicit instruction to:

1. Identify the mechanism of the distant domain
2. Construct the bridge (what hidden dimension connects them?)
3. Produce ideas that only make sense *through that bridge*

**Output format per collision:**

```
=== COLLISION N: [brief] × [domain] ===

HIDDEN DIMENSION IDENTIFIED:
[1–2 sentences on what makes these two fields secretly close]

IDEAS (15–20):
1. [...]
2. [...]
...
```

### Stage 3.5 — Cross-domain second collision

After Stage 3, identify the **two domains that produced the strongest collisions** (highest density of ideas with real, not decorative, bridges).

Run **one additional collision crossing those two domains with each other** (not with the brief):

```
=== CROSS COLLISION: [strong domain 1] × [strong domain 2] → [brief] ===

TRIPLE DIMENSION:
[what connects the two domains to each other, and both to the brief]

IDEAS (5–10):
```

**Why:** cross-domain collisions empirically produce the most distinctive ideas — articulating angles no single-domain collision reaches.

Limit to ONE second collision per run. More than that becomes combinatorics without return.

### Stage 4 — Curation (3 filters)

Apply in this order:

**Filter 1 — Signal vs. Noise**
- Discard ideas that: (a) are absurd without payoff, (b) only repeat the distant domain without a real bridge, (c) reconstruct the obvious with exotic vocabulary.

**Filter 2 — Voice / Style fit (with inline rewrite)**
- Check candidates against the voice or style criteria of the output destination.
- If an idea has a strong mechanism but weak formulation, REWRITE inline here — do not defer to delivery. Late rewriting wastes time and contaminates final output.
- Discard criterion: idea whose mechanism only works with vocabulary or tone unsuitable for the destination.
- Flag criterion: structurally original but operationally complex idea — flag it, let the user decide.

**Filter 3 — Brief criterion**
- Apply the "what validates" definition from Stage 1.

### Stage 5 — Ranked output

Deliver:

```
## TOP {N} CURATED IDEAS

1. [idea]
   ↳ Came from collision: [domain]
   ↳ Hidden dimension: [the bridge]
   ↳ Next step: [concrete action]

2. [...]
```

Plus a block of **interesting discards** (3–5 ideas that didn't pass but are worth logging for future iteration).

---

## 4. Embedded falsifiers

Before delivering, run internal checks:

- **Test A vs B:** if I removed the domain bank and used only the brief, would I reach the same ideas? If yes → failed, redo Stage 2 with more distant domains.
- **Test C:** do the ideas depend on the bridge, or would they be the same if I just said "be original"? If they're independent → failed.
- **Test D:** if the brief were 3× longer and more detailed (without domains), would I reach here? If yes → failed.

If any of the three fails, declare it and offer a rerun.

---

## 5. Cost gate

This skill is **expensive by design** (5–7 collisions × 15–20 ideas = ~100 ideas generated, then curated down to ~10, plus the cross-domain collision).

**Initial gate — ask the user before running:**

> "Open Collider will generate ~100 ideas across separate collisions and curate down to {N}. Token cost is high. Worth running, or would a lighter pass work?"

Lighter alternatives to suggest depending on context:
- Direct brainstorm with the model
- Focused angle generation
- Structured outline without domain collisions

---

## 6. Anti-patterns

- ❌ Generating generic domains without specific named reference (aviation ≠ "Air France 447, 2009")
- ❌ Generating "creative" but close domains (design × architecture × fashion — same zone)
- ❌ Skipping Stage 4 (curation) and delivering the raw pool
- ❌ Skipping Stage 3.5 (cross-domain) when there are two clearly strong collisions
- ❌ Applying voice/style pass *at delivery* instead of *at curation* (wastes time + contaminates output)
- ❌ Running without the cost gate
- ❌ Using as a substitute for convergent skills (copy, essay with defined thesis, editing)
- ❌ Running more than ONE cross-domain collision per execution (combinatorics without return)

---

## 7. Declared limitations

- Original paper tested only on Claude Sonnet 4; cross-vendor replication is future work
- LLM-as-judge is an imperfect metric — output still requires human judgment
- Bisociation produces **novelty**, not **value** — human curation remains the real filter
- Risk of "exotic idea without operational viability" — Stage 4 mitigates, does not eliminate

---

## 8. Iteration log (for users adapting this skill)

After running on 3 real briefs, review:
- Which generic domains kept recurring (build a blacklist)
- Which bridges worked (build a library of "confirmed hidden dimensions")
- Signal-to-noise ratio per brief (calibrate domain volume)
- Which cross-domain collisions (Stage 3.5) produced top-3 final ideas

This is how the skill compounds in value with use.

---

## References

- CL-ML (2026). "Escape the Artificial Hivemind." Open Collider research. github.com/CL-ML/open-collider
- Koestler, A. (1964). *The Act of Creation*. Hutchinson.
- Hofstadter, D. & Sander, E. (2013). *Surfaces and Essences*. Basic Books.
- Jiang, L. et al. (2025). "Artificial Hivemind: The Open-Ended Homogeneity of Language Models." arXiv:2510.22954.
- Polanyi, M. (1958). *Personal Knowledge*. (For the tacit dimension that curation cannot fully codify.)
