# Theorem Proving Stack

This document summarizes the reusable skills and technologies behind the
finite-capacity causal-geometry proof workflow. It is intended for people who
want to understand how the research repos are advanced without rereading the
entire Paper 1 repository.

The stack proved the **internal conditional mathematical theorem** in
`finite-capacity-causal-geometry`. It did not prove the physical nature-level
claim; that remains separated behind external evidence and reproduction gates.

## Reusable Codex Skill

The repo-local skill is:

```text
skills/theorem-ladder-research/SKILL.md
```

Use it when starting or advancing a theorem paper:

```text
Use $theorem-ladder-research to advance the current theorem paper one verified rung at a time.
```

The skill encodes the proof workflow: read state, choose the smallest named
rung, add fail-closed Rust guards, promote stable mathematics through Lean or
equivalent certificates, update state/proof logs, verify, commit, and push.

## Skills And Technologies

| Layer | What We Use | Purpose |
| --- | --- | --- |
| AI research assistant | Codex | Plans rungs, edits artifacts, runs checks, summarizes blockers, commits each verified step. |
| Research state | GPD documents | Keeps roadmap, state, machine-readable contracts, frontier indexes, and obligations aligned. |
| Executable gates | Rust + Cargo | Implements theorem gates, validators, diagnostics, non-promotion checks, and reproducibility commands. |
| Stable commands | Make | Provides repeatable entrypoints such as `make test-fast` and focused test filters. |
| Formal proof lane | Lean 4 + Lake | Kernel-checks theorem rungs, typed evidence rows, projections, and fail-closed blockers. |
| Structured state | JSON + jq | Validates machine-readable status, manifests, frontier data, and audit outputs. |
| Research record | Markdown, TeX, PDF | Stores theorem targets, proof logs, manuscript drafts, review packets, and claim boundaries. |
| Version control | Git + GitHub | Preserves rung-by-rung proof history and makes public review possible. |
| External validation | OBL-style evidence manifests | Separates internal proof closure from physical evidence, reproduction, and reviewer acceptance. |

## Workflow Pattern

The finite-capacity repo advanced by converting ambitious claims into small,
auditable rungs:

1. State the theorem target and the forbidden shortcuts.
2. Split the target into named proof obligations.
3. Add Rust gates that fail on missing evidence, duplicate evidence, shortcut
   routes, and overpromotion.
4. Move stable claims into Lean as concrete definitions, typed evidence rows,
   direct projections, and named fail-closed blockers.
5. Replace broad assumptions with explicit witnesses whenever possible.
6. Compose closed rungs into higher-level closure packages.
7. Update the roadmap, state file, proof log, open obligations, and manuscript
   surface in the same rung.
8. Verify with Rust, Lean, JSON, and diff checks.
9. Commit and push after each closed rung or useful obstruction.

## Core Claim Discipline

The proof workflow is designed to prevent false promotion:

- Simulation, search, curve fitting, generated prose, or a Lean skeleton cannot
  count as proof by themselves.
- Smooth continuum spacetime cannot be imported as a microscopic premise when
  the theorem target is emergent geometry.
- Internal mathematical closure cannot be relabeled as physical proof.
- Missing rows, missing witnesses, duplicate rows, unchecked assumptions, and
  shortcut routes must keep downstream flags false.
- External review and reproduction are separate evidence tracks, not internal
  proof artifacts.

## Rust-First Compute

Use Rust crates and binaries for computation wherever practical. Rust is the
default for finite-state enumeration, graph algorithms, discrete dynamics,
search, validators, artifact generators, reproducibility manifests, benchmarks,
and SMT/SAT orchestration. Python and CAS tools may still be useful for
literature APIs or exploratory symbolic checks, but their outputs are
diagnostic until a Rust gate, Lean proof, or explicit fail-closed audit
reproduces the relevant claim.

Preferred Rust crates include `petgraph`, `fixedbitset`, `bitvec`, `rayon`,
`nalgebra`, `ndarray`, `faer`, `sprs`, `egg`, `serde`, `serde_json`, `clap`,
`proptest`, `insta`, and `criterion`. Use external `z3`/`cvc5` binaries or
stable Rust wrappers for solver-backed bounded checks.

## Default Verification Shape

For a new paper repo, start with:

```bash
make test-fast
make lean-build
git diff --check
```

For proof-sensitive changes, add focused checks:

```bash
cargo test --workspace --test <gate_name>
(cd GPD/formal && lake env lean <module>.lean)
jq empty GPD/state.json
rg -n "sorry|admit|axiom|unsafe" GPD/formal
```

The exact command set should stay repo-local. The important invariant is that
promotion requires executable gates plus a formal or fail-closed certificate,
not prose agreement.

## Applying This To Paper 2

For `higher-dimensional-geometry-recovery`, the next use of this stack should
begin with HDG-001: define the admissible higher-dimensional finite-capacity
causal-network class. The first rungs should clarify:

- the network family and dimensional indexing;
- local update, capacity, and transfer constraints;
- admissible intrinsic coarse-graining maps;
- dimension and metric-observable witness surfaces;
- no-hidden-continuum blockers;
- Rust guards that keep the repo non-promoting until those definitions close;
- Lean scaffolds that expose missing proof obligations explicitly.

Paper 2 should not attempt curvature, Einstein dynamics, matter, gauge fields,
quantum behavior, or unified-field synthesis until the higher-dimensional
geometry recovery theorem has its own closed conditional surface.
