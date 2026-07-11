---
name: rust-compute-first
description: Use when adding computation, simulation, search, graph algorithms, validators, benchmark harnesses, data pipelines, or external solver orchestration for the unified-field-theory research repos. Prefer Rust crates and binaries over Python wherever practical, with Lean reserved for formal proof lanes.
---

# Rust Compute First

Use this skill before adding or recommending computational tooling for the
UnifiedFieldTheoryResearch repositories.

## Default Rule

Implement performance-sensitive or proof-adjacent computation in Rust first.
This includes finite-state enumeration, graph search, discrete dynamics,
validators, fail-closed gates, artifact generation, reproducibility manifests,
benchmarking, and SAT/SMT orchestration.

Use Python only for literature APIs, small exploratory checks, or external
scientific packages with no practical Rust equivalent. Python outputs are
diagnostic unless a Rust gate, Lean proof, or explicitly recorded fail-closed
audit reproduces the relevant claim.

## Preferred Rust Stack

- Graphs and finite structures: `petgraph`, `indexmap`, `fixedbitset`,
  `bitvec`, `smallvec`.
- Parallel search and enumeration: `rayon`, `crossbeam`, `itertools`.
- Numerics and sparse/linear algebra: `nalgebra`, `ndarray`, `faer`, `sprs`,
  `rug`.
- Rewrite and symbolic experiments: `egg`, `symbolica` when the problem is
  expression- or rewrite-heavy.
- SMT/SAT orchestration: external `z3`/`cvc5` commands, plus Rust wrappers such
  as `z3` or `rsmt2` when a stable API is useful.
- Artifact formats: `serde`, `serde_json`, `serde_with`, `csv`, `sha2`,
  `blake3`.
- CLIs and errors: `clap`, `anyhow`, `thiserror`.
- Testing and performance: `cargo-nextest`, `proptest`, `insta`, `criterion`,
  and `hyperfine`.

## Workflow

1. Read the target repo's `AGENTS.md` before changing dependencies.
2. Check whether a Rust implementation already exists in `rust/`.
3. Add the smallest Rust crate set that directly supports the current rung.
4. Expose computations through deterministic CLIs or tests, not ad hoc scripts.
5. Serialize outputs as JSON or stable text and hash artifacts when they feed a
   dossier or proof log.
6. Benchmark only after correctness gates exist.
7. Keep physical-success, known-limit, and validation claims false unless the
   repo's fail-closed gates say otherwise.

## Escalation

If a Python or CAS tool is needed, record one sentence in the artifact or proof
log explaining why Rust is not the primary implementation. Prefer using that
tool as an external oracle or cross-check, then reproduce the accepted result
with Rust/Lean before promotion.
