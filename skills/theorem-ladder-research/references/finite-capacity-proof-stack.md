# Finite-Capacity Proof Stack

This reference summarizes the reusable skills and technologies extracted from
`finite-capacity-causal-geometry`. It describes the architecture that proved
the internal conditional theorem; it does not assert physical/nature-level
proof, which remains gated by external evidence.

## Stack Matrix

| Layer | Technology / Skill | Role |
| --- | --- | --- |
| Research agent | Codex | Reads state, proposes rungs, edits code/docs, runs verification, commits after each rung. |
| State system | GPD files | Keeps `ROADMAP`, `STATE`, `state.json`, contracts, frontier indexes, and obligations synchronized. |
| Executable checks | Rust + Cargo | Implements simulators, validators, theorem gates, diagnostics, and non-promotion regression tests. |
| Project commands | Make | Provides stable entrypoints such as `make test-fast`, targeted Rust tests, and reproduction checks. |
| Formal certificate | Lean 4 + Lake | Kernel-checks stable theorem rungs, typed evidence rows, direct projections, and fail-closed blockers. |
| Structured data | JSON + jq | Validates machine-readable state, manifests, frontier indexes, and external evidence templates. |
| Manuscript/docs | Markdown, TeX, PDF | Records theorem targets, proof logs, audit summaries, review packets, and non-promotion boundaries. |
| Repository control | Git + GitHub | Preserves rung-by-rung history, public review surface, issues, releases, and external intake locators. |
| External review lane | OBL-style manifests | Separates internal theorem closure from physical evidence, reproduction, and reviewer claims. |

## Proving Pattern

The Paper 1 repo succeeded by turning broad claims into a ladder of typed,
checkable obligations:

1. Define the theorem target and forbidden proxies.
2. Split the target into named rungs and rows.
3. Add Rust gates that fail on missing rows, duplicate rows, shortcuts, and
   overpromotion.
4. Move stable rows into Lean as concrete definitions, typed evidence records,
   direct projections, and fail-closed blockers.
5. Replace broad supplied assumptions with smaller explicit witnesses.
6. Compose closed rungs into higher-level closure packages.
7. Record each rung in `docs/proof_log.md`, `GPD/STATE.md`, and machine-readable
   state/frontier files.
8. Keep physical or external-evidence flags false unless the exact external
   manifest rows close.

## Paper 1 Phases To Reuse

The finite-capacity roadmap used this sequence:

1. Restore proof frontier state and indexing.
2. Formalize the restricted model theorem.
3. Formalize the final ladder handoff.
4. Add an opt-in Lean/Lake lane.
5. Replace broad `Prop` fields with concrete definitions.
6. Prove row-level lemmas and closure packages.
7. Prove the final internal kernel handoff.

For a new paper, map these phases onto the new obligation IDs. For Paper 2,
start with the network class and intrinsic observables before attempting
causal cones, metric recovery, continuum-scale recovery, or theorem closure.

## Required Artifact Roles

- `AGENTS.md`: local rules, claim boundaries, and verification expectations.
- `GPD/ROADMAP.md`: phase structure and completion criteria.
- `GPD/STATE.md`: current position, focus, blockers, and session continuity.
- `GPD/state.json`: machine-readable contract/state when present.
- `docs/open_proof_obligations.md`: named open/closed obligations.
- `docs/proof_log.md`: validated rungs and obstructions with command evidence.
- `GPD/formal/`: Lean/Lake proof-certificate lane.
- `rust/*/tests/*_gate.rs`: Rust fail-closed theorem and non-promotion gates.
- `README.md`: public status and claim boundary.

## Promotion Rules

A rung can close when all are true:

- It has a named obligation ID.
- Its inputs, outputs, and forbidden shortcuts are explicit.
- Rust gates or equivalent executable checks reject malformed promotion.
- Lean/Lake or equivalent fail-closed evidence closes the mathematical claim.
- State, proof log, and open-obligation ledgers agree.
- Verification commands pass and are recorded.

A rung must remain open when any are true:

- It depends only on simulation, search, fit, or prose.
- It hides continuum geometry inside microscopic assumptions.
- It lacks a named blocker for missing evidence.
- It uses a broad assumption where a concrete witness is required.
- It tries to convert internal theorem closure into physical proof.

## Default Verification Bundle

Use local repo commands, but Paper 1's stable bundle was:

```bash
make test-fast
(cd GPD/formal && lake build)
cargo fmt --manifest-path rust/cclab_accel/Cargo.toml --check
jq empty GPD/state.json GPD/frontier-index.json
rg -n "sorry|admit|axiom|unsafe" GPD/formal
git diff --check
```

For a new paper with `make lean-build`, prefer:

```bash
make test-fast
make lean-build
git diff --check
```

Add targeted Rust tests and direct `lake env lean <module>.lean` checks for
the edited rung.
