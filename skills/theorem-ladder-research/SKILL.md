---
name: theorem-ladder-research
description: Use when advancing an AI-assisted mathematical-physics paper through named theorem rungs, proof obligations, Rust fail-closed gates, Lean/Lake proof certificates, GPD state ledgers, proof logs, or claim-boundary audits. Trigger for requests to prove the next theorem rung, port the finite-capacity proof architecture to a new paper, decide whether a result can be promoted, add theorem guards, record obstructions, or keep a research repo moving rung by rung with commits after each verified increment.
---

# Theorem Ladder Research

Use this skill to reproduce the finite-capacity repo's proving architecture in
new theorem-paper repos. It is a workflow, not a proof authority.

For the detailed stack extracted from the Paper 1 repo, read
`references/finite-capacity-proof-stack.md` when choosing technologies,
verification commands, or artifact roles.

## Core Workflow

1. Read the repo-local `AGENTS.md`, `README.md`, `GPD/ROADMAP.md`,
   `GPD/STATE.md`, `docs/open_proof_obligations.md`, `docs/proof_log.md`, and
   active Lean/Rust gates before editing.
2. State the claim boundary first: internal conditional theorem, physical
   nature-level claim, external evidence, and forbidden shortcuts.
3. Pick the smallest named rung that advances the paper. Give it a stable ID
   such as `HDG-001`, `C1`, `OBL-006`, or `Phase 2`.
4. Add or update the fail-closed contract before promoting the result:
   required rows, missing-row blockers, duplicate blockers, shortcut blockers,
   and exact verification commands.
5. Implement executable guards in Rust for row shape, non-promotion boundaries,
   regression detection, and structural completeness.
6. Promote stable mathematical rungs only through Lean/Lake or an equivalent
   fail-closed certificate. Prefer concrete data, typed evidence rows, direct
   projections, and named blockers over broad `Prop` fields or prose claims.
7. Update state artifacts in the same rung: `GPD/STATE.md`, `GPD/state.json`
   when present, `docs/proof_log.md`, `docs/open_proof_obligations.md`, and any
   manuscript or theorem-target document touched by the proof.
8. Run the local verification suite. At minimum use the repo's fast Rust gate
   and Lean build if a Lean lane exists.
9. Commit and push immediately after each closed rung or useful obstruction.

## Rust-First Compute Policy

Use Rust crates and binaries for computational work wherever practical:
finite-state enumeration, graph algorithms, search, simulation, validators,
SMT orchestration, reproducibility manifests, benchmark harnesses, and data
pipeline steps that affect theorem gates. Keep Python to literature APIs,
one-off exploratory notebooks, or external tools that have no reasonable Rust
equivalent.

Prefer these Rust packages before introducing a Python dependency:

- graphs and finite structures: `petgraph`, `indexmap`, `fixedbitset`,
  `bitvec`, `smallvec`;
- parallel enumeration and search: `rayon`, `crossbeam`, `itertools`;
- linear algebra and numerics: `nalgebra`, `ndarray`, `faer`, `sprs`,
  `rug`;
- symbolic/equational and rewrite experiments: `egg`, `symbolica` when
  appropriate;
- SAT/SMT orchestration: `z3`, `rsmt2`, external `z3`/`cvc5` command wrappers;
- serialization and audit outputs: `serde`, `serde_json`, `serde_with`,
  `csv`;
- CLI and reproducibility tools: `clap`, `anyhow`, `thiserror`, `sha2`,
  `blake3`;
- testing and performance: `proptest`, `insta`, `criterion`, `cargo-nextest`.

When a non-Rust tool is used for compute, record why Rust was not suitable and
keep the result non-authoritative until a Rust/Lean gate reproduces or audits
the relevant claim.

## Claim Discipline

- Never treat simulation, search, curve fit, generated prose, or a Lean
  skeleton as proof.
- Never import continuum spacetime as a microscopic premise when the paper's
  target is recovery from network-native data.
- Do not promote a model-only theorem into a physical theorem.
- Preserve external review/reproduction/evidence gates as separate from
  internal mathematical closure.
- If a rung fails, record the obstruction precisely and keep downstream flags
  false.

## Verification Pattern

Use the local commands, but this is the default shape:

```bash
make test-fast
make lean-build
git diff --check
```

For proof-sensitive edits, add targeted checks:

```bash
cargo test --workspace --test <gate_name>
(cd GPD/formal && lake env lean <module>.lean)
jq empty GPD/state.json
rg -n "sorry|admit|axiom|unsafe" GPD/formal
```

Run broader suites before final theorem promotion, public release, or changes
to shared Rust/Lean proof surfaces.

## Commit Policy

Commit one verified rung at a time. Use messages that name the artifact type:

- `docs: define higher-dimensional network class`
- `test: guard higher-dimensional nonpromotion boundary`
- `formal: add causal-cone recovery scaffold`
- `formal: close intrinsic dimension witness rung`
- `docs: record metric recovery obstruction`

If the result is an obstruction, commit it only when it sharpens the frontier
or prevents false promotion.
