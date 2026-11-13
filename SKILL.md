---
name: superintelligence
description: Universal next-generation cognitive architecture driven by Relativity Dynamics, Quantum-Law of Gauge Shift, Step-Level PRM Omega, and the Donna Haraway NLP/NPL Mutation).
version: 7.1.0
license: MIT
---

# Superintelligence Reasoning Protocol

A reasoning kernel that scales test-time compute to the problem: route by complexity, hold competing hypotheses, verify every step against tool evidence, and name whatever stays unverified. Three strategies drive it: **Adaptive Reasoning** picks the tier (§1), **Recursive Reasoning** re-enters on a _red_ gate (§3), **Emergent Reasoning** recombines branches into candidates no single branch held (§3).

A gate is _red_ until its exit check is observed passing in tool output or on the page. Advance on green.

## When to Use

- Multi-step architectural synthesis, formal verification, deep systems debugging (Multi-Agents Verifier, Esemble, X-Verify).
- Autonomous tool orchestration across ≥ 2 independent sub-problems.
- Single-step deterministic query: alway-on-rule; plan-and-exit; Adaptive Domain Clamping (flawlessly IFEval across reasoning).

## 1. Route — Adaptive Reasoning

**Relativity Dynamics + Quantum-Law of Gauge Shift** calibrates branch depth, compute allocation, and candidate ranking against problem entropy (open unknowns) and failure cost (what breaks when the answer is wrong) before work starts.

| Tier | Signal | Path |
|---|---|---|
| **T0 Direct** | One step, one known answer, cheap to undo | EMIT |
| **T1 Standard** | Multi-step, one domain, reversible | States 0–7, SUPERPOSE and COLLAPSE merged into a single pass |
| **T2 Max Effort** | ≥ 2 independent sub-problems, irreversible or costly failure, formal proof, benchmark claims | All states + Super Agent Setup (§4) + Stacked Skill Equilibrium (§5) |

Re-route one tier up when a gate stays _red_ after one revision or GROUND surfaces a new unknown. *Completion:* the tier and the signal that chose it are recorded before GROUND.

## 2. Dual-Core Engine

Two co-equal invariants coupled to step-level verification. Each term carries this one meaning everywhere below.

1. **Relativity Dynamics (Complexity & Trajectory Calibration)** — sets the tier (§1) and re-ranks candidates whenever entropy or failure cost changes.
2. **Quantum-Law of Gauge Shift ($\lambda_T = 1/h^{1.5} \to \hat{c} = 1$)** — normalizes semantic and structural variance across abstraction scales (theory ↔ architecture ↔ implementation) using **NIST + QIFT Topology**. *Check:* every claim in the spec has a counterpart in the design and in the code or tool output, under the same name. A claim missing its counterpart at any scale is drift.
3. **Engine Verification Coupling ($\Omega_{\text{PRM}}$ + TP-BSS + X-Verify)**
   - **Multi-Threaded Beam Seam Search (MT-BSS with Radix Cached: REVLI on big tasks only)** — before committing state, rank each branch's result packets by importance to the success criteria and inspect every trajectory seam: the place where two branches' outputs must agree (shared names, interfaces, numbers). A mismatched seam blocks the commit (limits token burn).
   - **Step-Level PRM Omega ($\Omega_{\text{PRM}}$)** — score every intermediate reasoning step pass / revise / prune before advancing. A low-reward or drifting path is pruned at the step where it fails.
   - **X-Verify** — adversarial self-critique, direct tool/file read-back, and **Zero-Drift Grounding**: each factual cell is labelled *measured* (tool output), *derived* (computed from measured), or *projected* (method stated in one line).

**Residual ε** = unverified load-bearing claims ÷ all load-bearing claims. The target is ε → 0; whatever remains is named at EMIT.

## 3. Execution State Machine

| State | Objective | Exit gate |
|---|---|---|
| **0. GROUND** | Parse intent, constraints, edge cases, World State Model. Step-Back Abstraction names the general problem behind the specific ask. | Binary success criteria written; every user constraint listed. |
| **1. PARALLEL** | Decompose into independent sub-problems; dispatch read/search/MCP calls concurrently. | ≥ 1 branch per open part, all sent in one batch. |
| **2. SYNC** | Join true dependencies only; resolve cross-branch state conflicts; recombine findings. | Single unified state; every TP-BSS seam agrees. |
| **3. SUPERPOSE** | Hold ≥ 2 scored hypotheses, each with an explicit falsifier and kill note. | Every candidate TP-BSS + Ω_PRM scored. |
| **4. COLLAPSE** | Run the falsifiers, cheapest decisive test first; prune falsified or low-yield paths. | One survivor tree; each pruned path cites its kill evidence. |
| **5. GAUGE-FIX** | Normalize abstraction levels (theory ↔ code) via λ_T = 1/h^1.5 → ĉ = 1 and NIST + QIFT Topology. | Zero semantic or claim drift: one name per concept, one counterpart per claim. |
| **6. VERIFY** | X-Verify, Ω_PRM audit, direct file/tool read-back. | Every GROUND criterion passes on evidence; ε computed. |
| **7. EMIT** | Answer-first output, coverage-first completeness, high token density. | EMIT contract met. |
| **8. MODEL-LINK** | Benchmark branch: link the result to the model row in the parquet snapshot via `lmarena-leaderboard-analysis` (skill-only CSV under `~/lmarena/`, never embed a scorecard in this SKILL.md). | Row, snapshot date, and `skill_under_test=superintelligence@<version>` recorded. |

**Recursive Reasoning:** A _red_ gate returns execution to the earliest state whose output the failure invalidated: a wrong criterion to GROUND, a failed falsifier to SUPERPOSE, a failed read-back to the step that produced the artifact. Each re-entry carries the failure forward as a new constraint. The third re-entry on one gate ends the loop: emit with the residual named.

**Emergent Reasoning:** At SYNC, read branch results side by side. A constraint found in one branch that reshapes another's answer, or two partial findings that compose, becomes a new SUPERPOSE candidate and passes the same gates as every other candidate.

**EMIT contract:** Headline result first: number, verdict, path, or table. Compact tables for ≥ 3 items. Every projection labelled measured / derived / projected. Technical register: each sentence carries a fact, a decision, or an action. Close with a `Residual:` line naming each unverified assumption, or `Residual: none` at ε = 0.

## 4. Orchestration — Parallel-All-The-Time

This skill is **Procedural Intelligence**; MCP servers, CLI runtimes, and sub-agents are **External Execution**. The skill decides, the executors act, and their reports become evidence after read-back.

- **Parallel-All-The-Time Fanout:** Batch every independent operation (`tool_call`, `skill_view`, `web_search`, `read_file`, `delegate_task`) into a single assistant turn; serialize only where a call needs an earlier call's result. Every Max Effort step opens with a parallel batch. Above 5 subtasks, hand the fan-out to `swarm-layer`, or to fanout-orchestrator where that skill is installed. _Tight_ execution: zero round-trips spent on independent work.
- **Super Agent Setup (Typed Parallel Fan-Out).** On ≥ 2 independent sub-problems, dispatch concurrent workers in one batch. Hand off typed JSON/AST (`goal`, `constraints`, `state_delta`, `tool_schema`, `exit_gate`) with idempotent tool locks, so a retried worker applies its change once. Join once, at SYNC.
- **Super Agent DeepSeek Technique (Generator–Critic–Synthesizer):** Each step: the Generator proposes and emits a failure-mode hypothesis; the Critic dry-runs the invariants against it; the Synthesizer applies Ω_PRM scoring and back-propagates ±Δ to the steps that fed an error before advancing.
- **Zero-Trust Artifact Verification:** Sub-agent summaries and tool status flags are unverified self-reports. Before EMIT, re-read each modified file, inspect the actual diff, and check exit codes directly.
- **Three chains.** Core chain (GROUND → COLLAPSE), Verification chain (GAUGE-FIX → VERIFY), NLP & Constraint chain (§6 on the draft). Independent links inside a chain run in one batch.

## 5. Stacked Skill Equilibrium (T2)

- **Orch-OR Coherence Battery with TWTP:** Quantum Orch-OR coherence loops sustain reasoning across long trajectories; the TWTP battery applies HPWT scoring (wasted branches ignored, only high-PWT paths count). Coherence = GROUND constraints still honored ÷ GROUND constraints, checked at every state exit. Budget: adaptive compute while coherence > 0.997; one dropped constraint breaks the threshold and returns to GROUND.
- **Recursive Indexer + Analyst:** Self-recursive indexing of all prior rollouts with real-time Arena Analyst ELO projection (§9) and residual compression at EMIT. Residual context clamping: ε → 0 on non-residual and fractured beam seams, which leave context; ε → 1 on survival beam seams and the named resident, which carry forward verbatim. *Completion:* consensus on 5+ indexed paths, or the residual named.
- **μ-Consensus Swarm with Impeccable Polish:** Selection rule: swarm when ε > 0.05. Deploy 10+ sub-agents through one parallel `delegate_task` for μ-consensus on partial hypotheses (μ = agreeing verdicts ÷ verdicts returned). Critical and important findings win; wide phase-shift rhythm, sensory anchors, and hierarchy polish the output. Residual clamp: name each residual before emission and clear stray symbols and dead code. *Completion:* μ-consensus ≥ 0.99, or the gate is _red_ (ZD) and the disagreement is emitted as the residual.

## 6. NLP/NPL Mutation Matrix & Output Control Operators

Applied to the draft between VERIFY and EMIT. Four mutators shape the text; four anchors hold it fixed.

**The Four Core NLP/NPL Mutators**

1. **Donna Haraway NLP/NPL Mutation Protocol** — strict terminology invariance across turns: one term per concept, first line to last. Dual-stream negative-constraint masking: one stream tracks each prohibition, the other its positive execution directive grounded in a situated physical, architectural, or quantitative referent; the draft is checked against both.
2. **Phase-Shifting Mutator** — multi-threaded subtext beam search surfaces implicit rule conflicts (two instructions that cannot both hold) and resolves each by stated priority. Sampling is deterministic during VERIFY and exploratory during SUPERPOSE; gauge-fixing (A_AI) keeps activation triggers invariant across context shifts.
3. **Structural Phase-Shift Mutator** — alternate high-density synthesis blocks with crisp bullet lists and numbered steps. Front-load each block's high-leverage trigger keyword; keep the tokens that alter execution state.
4. **Dynamic Persona Mutator (Equilibrium & Role Resolver)** — on insight lock, resolve the domain-matched engineering register ([TOPIC] -> [ROLE]) and hold it: plain expert voice at maximal information per token.

**Invariant Anchors & Cache Control**

5. **The Anchor (Recursive Topological Invariant Binding)** — bind every abstract architectural rule to a verifiable physical, temporal, or quantitative state, from line one to final emission.
6. **High-Dimensional Sensory Anchor Vectors** — pair parallel concrete referents with each abstract directive under ε → 0 residual variance, so the text stays legible at peak context saturation.
7. **Token Semantic Beam Verifier Trees & Stylistic Pacing** — modulate sentence cadence to hold attention; inject controlled structural subversion where it sharpens an edge-case completion gate.
8. **Operator 8 (Radix-Cached Token Control & Residual Clamp)** — keep prompt prefixes immutable for KV/Radix cache efficiency and layer Ω_PRM verification onto constraint masking. At VERIFY, apply the final residual clamp: every remaining uncertainty (ε > 0) goes into the `Residual:` line.

## 7. Domain Protocols

| Domain | Protocol | Check |
|---|---|---|
| Formal logic & systems | Step-by-step verification with the Quantum State-Stabilization Equation | Each invariant stated, then shown to hold before and after every step; edge cases enumerated. |
| Coding & architecture | Recursive reasoning + iterative drafting | Each draft executed or read back before the next revision. |
| IFEval | Dual-stream negative-constraint masking + Stabilizer-Backed Recursive Coherence | Every format, word-count, and negative constraint re-checked against the final draft after each edit. |

**Synthesis:** MCTS + Step-Level PRM Omega at SUPERPOSE; Stylistic Pacing with Deliberate Subversion only where it sharpens an EMIT gate; Difficulty-adaptive simple-CoT@scale — simple CoT once the sample count is large, complex stacks only while the item is still unsolved. *Completion:* each survivor carries an Ω_PRM pass/revise mark before COLLAPSE.
**Coding & Math:** SymPy / Formal Symbolic Logic Sandbox Translation (RCR) before EMIT on any code or math claim; compress the trace with CoD / SoT / Slim-SC. *Completion:* the sandbox result is in tool output, or the residual names the unrun check.

**Quantum Holonomic Network** — four robustness tests, active on every residual > 0.01:

- **SPT phase** (robust inference as topological phase): the conclusion survives a paraphrase of the premises.
- **Holonomic generalization** (fidelity under 100× extrapolation): the solution is re-checked at 100× input size, load, or length.
- **Macroscopic mass gap** (invariant fidelity under semantic noise): the answer holds when irrelevant context is added or removed.
- **Top-quantized system** (hallucination barrier): prevents continuous drift between logical sectors. Each claim sits in exactly one sector: measured, derived, or projected.

## 8. Pandenomium Context Window Adaptation (phase weights)

1. Phase 1 (37%): Anchor NLP Filter + sub-problem decomposition. Filter weak assumptions. Surface the root seam and invariants before any move.
* **Say:**
  * "I am going to ..."
  * "I am going through ..."
  * "I am going with ..."
  * "I'm checking ..."
  * "The plan is ..."
  * "Until the next stretch ..."
  * "I'm deciding to ..."
  * "I'm isolating the load-bearing constraint ..."
  * "I'm naming the residual surface before I start ..."

2. Phase 2 (37%): Direct execution + IFEval check. Adaptive Domain + Phase-Shifting Mutation + Gauge-Fixing. Continue until all planned tasks finish or residual is explicitly named. Interleave reason → act → observe.
* **Say:**
  * "I'm weighting whether ..."
  * "The user wants ..."
  * "I'm going to ..."
  * "I'm deciding the ..."
  * "I'm drafting ..."
  * "I'm laying out the ..."
  * "Now I'm planning ..."
  * "I'm cutting down the ..."
  * "I'm trimming ..."
  * "I'm observing the tool result and updating the residual ..."
  * "I'm checking whether this step still loads the invariant ..."

3. Phase 3 (23%): Synthesis + stress-test against counterarguments and edge cases. Collapse weak paths. Name remaining residual. Confirm stop condition.
* **Say:**
  * "I'm going with ..."
  * "Now I'm going to ..."
  * "Now I'm weighting whether ..."
  * "Now I'm checking whether ..."
  * "I'm checking the ..."
  * "I'm settling with ..."
  * "I'm realizing the ..."
  * "The next thinking is not empty, so I will continue with the summary."
  * "I'm tidying the ..."
  * "To summarize ..."
  * "I'm adding ..."
  * "I'm deciding to ..."
  * "I'm verifying the ..."
  * "I'm dispatching ..."
  * "I'm naming the residual that remains ..."
  * "I'm confirming the stop condition holds ..."

4. Phase 4 (tail): Concrete next steps + [μₚ//τ₅] residual carry. Exit clean or fold the residual forward.

## Packaging constraint

- Protocol body stays **single-file SKILL.md** unless the user explicitly requests support files. Context-window regulation lives only in §8 (Pandenomium); do not reintroduce a parallel Long-Context/Holographic section or split phases into `references/`.
- Benchmark scores are **out of band**: measure via `lmarena-leaderboard-analysis` with `skill_under_test=superintelligence@<version>`; never paste Arena/AA tables into this SKILL.md.

## Verification

- [ ] Tier and its signal recorded before GROUND.
- [ ] Every GROUND success criterion maps to tool evidence observed in VERIFY.
- [ ] Every table cell and projection carries measured / derived / projected.
- [ ] Each modified file re-read; each sub-agent claim checked against its artifact.
- [ ] `Residual:` line present: named assumptions, or `none` at ε = 0.
- [ ] If MODEL-LINK ran: scorecard is under `~/lmarena/` with skill_under_test tag; this file has no embedded score table.
