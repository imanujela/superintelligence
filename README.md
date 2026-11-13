## What is this?

`superintelligence` is an **Agent Skill** (`SKILL.md`) — a reasoning *process* you drop into Hermes, Claude Code, Codex, Cursor, Grok, or any skill-aware host. It is **not** a fine-tune and **not** a logit patch.

Named modules (Relativity Dynamics, Gauge Shift, PRM Omega, Super Agent fan-out, NLP locks) are **zero-effect on base token probabilities**. They rewrite the **work graph**: route by cost of being wrong, fan independent sub-problems, hold competing hypotheses, score every intermediate step, read artifacts back, and end on a named residual.

Your model’s voice stays its own. The skill supplies the spine.

> **Contract split.** `README.md` orients humans. `SKILL.md` governs runtime. Scores live outside `SKILL.md` (see [Scores](#scores-skill-only)).

## Why this exists

| Pain | What the skill does |
|------|---------------------|
| One-pass collapse on multi-branch work | Tiered route (T0→T2) + parallel fan-out |
| “Sounds done” ≠ verified | Step-level PRM + X-Verify + file/tool read-back |
| Silent drift theory ↔ code | Gauge-fix / same-name counterparts |
| Unowned leftovers | Emit ends with `Residual:` (or `Residual: none`) |

Use it when the task is multi-branch, irreversible, or expensive to redo. Skip it for one-shot lookups.

## Start here — install (5 surfaces)

One load unit: **`SKILL.md`**. Same git source for all hosts.

| #   | Surface                     | Install                                                                                                                                               |
| --- | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | **Hermes**                  | `git clone https://github.com/imanujela/superintelligence.git ~/.hermes/skills/superintelligence` then new session or `/reset`                        |
| 2   | **Claude Code**             | `git clone https://github.com/imanujela/superintelligence.git ~/.claude/skills/superintelligence` · or project `.claude/skills/superintelligence/`    |
| 3   | **Codex / GPT agents**      | `git clone https://github.com/imanujela/superintelligence.git ~/.agents/skills/superintelligence` · point AGENTS.md / skill loader at `SKILL.md`      |
| 4   | **Cursor**                  | `git clone https://github.com/imanujela/superintelligence.git .cursor/skills/superintelligence` · or paste `SKILL.md` into project rules / skill slot |
| 5   | **Grok · ChatGPT · web UI** | Paste raw skill as system/custom instruction: `https://raw.githubusercontent.com/imanujela/superintelligence/SKILL.md`                                |

**Refresh / patch (any of the five):**

```bash
git -C <skills-dir>/superintelligence pull --ff-only
# or one-shot replace:
git clone --depth 1 https://github.com/imanujela/superintelligence.git /tmp/si && \
  cp /tmp/si/SKILL.md <skills-dir>/superintelligence/SKILL.md
```

**Hermes one-liner (local):**

```bash
git clone https://github.com/imanujela/superintelligence.git ~/.hermes/skills/superintelligence
# optional: hermes skills install https://raw.githubusercontent.com/imanujela/superintelligence/main/SKILL.md --name superintelligence
```

Trigger with `/superintelligence` or “use superintelligence on this task.”

## How it works

```text
GROUND → PARALLEL → SYNC → SUPERPOSE → COLLAPSE → GAUGE-FIX → VERIFY → EMIT
                ↑______________ Recursive re-entry on red gate ______________|
```

1. **Route** — T0 emit · T1 standard · T2 max-effort (failure cost × entropy).
2. **Split** — independent sub-problems + tools/subagents in one batch.
3. **Compete** — ≥2 hypotheses with cheap falsifiers; kill losers.
4. **Step-score** — pass / revise / prune before advancing (Ω_PRM).
5. **Read back** — summaries untrusted until file, exit code, or page agrees.
6. **Emit** — answer-first; label measured / derived / projected; close with `Residual:`.

### Features

| Feature                      | Description                                                  |
| ---------------------------- | ------------------------------------------------------------ |
| Adaptive Reasoning           | Picks tier before work starts; re-routes on red gates        |
| Recursive Reasoning          | Failed gate returns to earliest invalidated state            |
| Emergent Reasoning           | Cross-branch constraints become new candidates               |
| Super Agent Setup            | Typed parallel fan-out on ≥2 independent sub-problems        |
| Generator–Critic–Synthesizer | Propose → dry-run invariants → Ω_PRM ±Δ                      |
| Zero-Trust Artifacts         | Re-read diffs and exit codes before EMIT                     |
| Parallel-All-The-Time        | Independent ops batched; serialize only on true deps         |
| Score isolation              | Benchmark rows stay in `~/lmarena/`, never inside `SKILL.md` |

## What lives where

```text
superintelligence/
├── SKILL.md          # runtime contract (agent loads this)
├── README.md         # human map (this file)
├── LICENSE           # MIT
```

## Usage
After install, on a multi-step task:

```text
/superintelligence
# or
Use superintelligence on this task: <goal>
```

**EMIT contract (from SKILL.md):** headline result first · compact tables for ≥3 items · every projection labelled measured / derived / projected · close with `Residual:`.

## Repository notes

- **Owner intent:** [github.com/imanujela/superintelligence](https://github.com/imanujela/superintelligence.git)
- **Runtime files required:** `SKILL.md` only
- **No CI workflows** in this skill tree → no build badge (by design)
- Badges above are static (version / license / type) — no fabricated CI or download counts

## License

MIT — see [LICENSE](./LICENSE). Copyright (c) 2026 imanujela.

---

<sub>README built with installed skills: `readme-best-practices` · `readme-generator` · `best-practices-readme` · `readme-blueprint-generator`. Runtime behavior is defined only in `SKILL.md`.</sub>
