# Repository Guidelines

## Scope & Purpose

This workspace is the Codex control point for macro-level unified field theory research planning across `~/UnifiedFieldTheoryResearch`. Inspect sibling repositories, summarize the current theorem frontier, and recommend the next high-leverage research step. Do not treat this directory alone as the project.

When asked what to do next, read active state documents first, then answer at the research-program level: status, blockers, strongest next move, verification path, and risks.

## Project Structure & Module Organization

Primary repositories under `/Users/charlie/UnifiedFieldTheoryResearch`:

- `finite-capacity-causal-geometry/`: Paper 1/core finite-capacity causal-network theorem program. Key files: `AGENTS.md`, `README.md`, `GPD/STATE.md`, `GPD/ROADMAP.md`, `GPD/frontier-status.md`, `docs/proof_log.md`.
- `higher-dimensional-geometry-recovery/`: Paper 2 skeleton for higher-dimensional recovery from the frozen Paper 1 result. Key files: `README.md`, `UPSTREAM-CORE.json`, `docs/higher_dimensional_geometry_theorem.md`, `GPD/formal/FiniteCapacity/HigherDimGeometry.lean`.
- `unified-field-theory-codex/`: this meta guide workspace.

Respect each child repository’s own `AGENTS.md` before editing it.

## Build, Test, and Development Commands

Use repository-local commands from the relevant child repo:

- `cd finite-capacity-causal-geometry && make test-fast`: fast theorem-ladder smoke check.
- `cd finite-capacity-causal-geometry && make test TEST_FILTER=<rust_test_name>`: focused Rust regression.
- `cd finite-capacity-causal-geometry && make rust-build && make rust-test`: Rust implementation checks.
- `cd higher-dimensional-geometry-recovery && make test-fast`: Paper 2 guard checks.
- `cd higher-dimensional-geometry-recovery && make lean-build`: Lean scaffold verification.

Run full suites only before broad promotion, proof-log updates, or shared-kernel changes.

## Coding Style & Naming Conventions

The core repo is Rust-only for runtime, simulators, validators, theorem gates, experiments, tests, and tooling. Do not add Python artifacts to `finite-capacity-causal-geometry/`. Use Lean only in documented formal lanes. Keep theorem, obligation, and guard names explicit and searchable, matching patterns such as `obl-006-*`, `*_theorem.md`, and `*_gate.rs`.

## Research Planning Guidelines

Maintain the distinction between conditional mathematical progress and physical nature-level claims. The internal conditional theorem in `finite-capacity-causal-geometry/` is recorded as complete under the Lean/fail-closed audit surface; physical promotion remains blocked by OBL-006 external evidence. `higher-dimensional-geometry-recovery/` is non-promoting and starts with HDG-001 through HDG-007.

Favor next steps that close named obligations, reduce ambiguity, produce external-review evidence, or advance Paper 2 definitions. Avoid adding wrappers, aliases, catalogs, or hardening layers unless a concrete missing dependency or regression is identified.

Use `skills/theorem-ladder-research/SKILL.md` when a future Codex run needs the reusable proof-ladder workflow distilled from `finite-capacity-causal-geometry/`, especially for new paper rungs that should avoid rereading the whole Paper 1 repo.

## Commit & Pull Request Guidelines

Use concise Conventional Commit-style messages, for example `docs: update frontier synthesis` or `test: add higher-dimensional guard`. Pull requests should state the research obligation addressed, files changed, verification commands, and whether the change is mathematical, tooling-only, or physical-evidence related.
