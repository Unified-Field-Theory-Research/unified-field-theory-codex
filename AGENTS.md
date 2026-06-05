# Repository Guidelines

## Scope & Purpose

This workspace is the Codex control point for macro-level unified field theory research planning across `~/UnifiedFieldTheoryResearch`. Inspect sibling repositories, summarize the current theorem frontier, and recommend the next high-leverage research step. Do not treat this directory alone as the project.

When asked what to do next, read active state documents first, then answer at the research-program level: status, blockers, strongest next move, verification path, and risks.

## Project Structure & Module Organization

Primary repositories under `/Users/charlie/UnifiedFieldTheoryResearch`:

- `finite-capacity-causal-geometry/`: Paper 1/core finite-capacity causal-network theorem program. Key files: `AGENTS.md`, `README.md`, `GPD/STATE.md`, `GPD/ROADMAP.md`, `GPD/frontier-status.md`, `docs/proof_log.md`.
- `higher-dimensional-geometry-recovery/`: Paper 2 skeleton for higher-dimensional recovery from the frozen Paper 1 result. Key files: `README.md`, `UPSTREAM-CORE.json`, `docs/higher_dimensional_geometry_theorem.md`, `GPD/formal/FiniteCapacity/HigherDimGeometry.lean`.
- `curvature-from-finite-capacity-causal-networks/`: Paper 3 skeleton for network-native curvature recovery from the closed Paper 2 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/network_curvature_theorem.md`, `GPD/formal/FiniteCapacity/NetworkCurvature.lean`.
- `gravitational-dynamics-from-finite-capacity-causal-networks/`: Paper 4 skeleton for network-native gravitational-dynamics or field-law analogues from the closed Paper 3 curvature result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/gravitational_dynamics_theorem.md`, `GPD/formal/FiniteCapacity/GravitationalDynamics.lean`.
- `quantum-compatible-local-dynamics-from-finite-capacity-causal-networks/`: Paper 5 skeleton for quantum-compatible local dynamics from the closed Paper 4 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/quantum_compatible_local_dynamics_theorem.md`, `GPD/formal/FiniteCapacity/QuantumCompatibleLocalDynamics.lean`.
- `matter-gauge-observables-from-finite-capacity-causal-networks/`: Paper 6 skeleton for matter/gauge observables from the closed Paper 5 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/matter_gauge_observables_theorem.md`, `GPD/formal/FiniteCapacity/MatterGaugeObservables.lean`.
- `particle-excitation-observables-from-finite-capacity-causal-networks/`: Paper 7 skeleton for particle-excitation observables from the closed Paper 6 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/particle_excitation_observables_theorem.md`, `GPD/formal/FiniteCapacity/ParticleExcitationObservables.lean`.
- `standard-model-candidate-observables-from-finite-capacity-causal-networks/`: Paper 8 skeleton for Standard-Model-candidate observables from the closed Paper 7 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/standard_model_candidate_observables_theorem.md`, `GPD/formal/FiniteCapacity/StandardModelCandidateObservables.lean`.
- `observed-catalog-comparison-observables-from-finite-capacity-causal-networks/`: Paper 9 skeleton for observed-catalog comparison observables from the closed Paper 8 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/observed_catalog_comparison_observables_theorem.md`, `GPD/formal/FiniteCapacity/ObservedCatalogComparisonObservables.lean`.
- `external-evidence-manifest-from-finite-capacity-causal-networks/`: Paper 10 skeleton for external-evidence manifests from the closed Paper 9 result. Key files: `README.md`, `UPSTREAM-PAPERS.json`, `docs/external_evidence_manifest_theorem.md`, `GPD/formal/FiniteCapacity/ExternalEvidenceManifest.lean`.
- `unified-field-theory-codex/`: this meta guide workspace.

Respect each child repository’s own `AGENTS.md` before editing it.

## Build, Test, and Development Commands

Use repository-local commands from the relevant child repo:

- `cd finite-capacity-causal-geometry && make test-fast`: fast theorem-ladder smoke check.
- `cd finite-capacity-causal-geometry && make test TEST_FILTER=<rust_test_name>`: focused Rust regression.
- `cd finite-capacity-causal-geometry && make rust-build && make rust-test`: Rust implementation checks.
- `cd higher-dimensional-geometry-recovery && make test-fast`: Paper 2 guard checks.
- `cd higher-dimensional-geometry-recovery && make lean-build`: Lean scaffold verification.
- `cd curvature-from-finite-capacity-causal-networks && make test-fast`: Paper 3 guard checks.
- `cd curvature-from-finite-capacity-causal-networks && make lean-build`: Paper 3 Lean scaffold verification.
- `cd gravitational-dynamics-from-finite-capacity-causal-networks && make test-fast`: Paper 4 guard checks.
- `cd gravitational-dynamics-from-finite-capacity-causal-networks && make lean-build`: Paper 4 Lean scaffold verification.
- `cd quantum-compatible-local-dynamics-from-finite-capacity-causal-networks && make test-fast`: Paper 5 guard checks.
- `cd quantum-compatible-local-dynamics-from-finite-capacity-causal-networks && make lean-build`: Paper 5 Lean scaffold verification.
- `cd matter-gauge-observables-from-finite-capacity-causal-networks && make test-fast`: Paper 6 guard checks.
- `cd matter-gauge-observables-from-finite-capacity-causal-networks && make lean-build`: Paper 6 Lean scaffold verification.
- `cd particle-excitation-observables-from-finite-capacity-causal-networks && make test-fast`: Paper 7 guard checks.
- `cd particle-excitation-observables-from-finite-capacity-causal-networks && make lean-build`: Paper 7 Lean scaffold verification.
- `cd standard-model-candidate-observables-from-finite-capacity-causal-networks && make test-fast`: Paper 8 guard checks.
- `cd standard-model-candidate-observables-from-finite-capacity-causal-networks && make lean-build`: Paper 8 Lean scaffold verification.
- `cd observed-catalog-comparison-observables-from-finite-capacity-causal-networks && make test-fast`: Paper 9 guard checks.
- `cd observed-catalog-comparison-observables-from-finite-capacity-causal-networks && make lean-build`: Paper 9 Lean scaffold verification.
- `cd external-evidence-manifest-from-finite-capacity-causal-networks && make test-fast`: Paper 10 guard checks.
- `cd external-evidence-manifest-from-finite-capacity-causal-networks && make lean-build`: Paper 10 Lean scaffold verification.

Run full suites only before broad promotion, proof-log updates, or shared-kernel changes.

## Coding Style & Naming Conventions

The core repo is Rust-only for runtime, simulators, validators, theorem gates, experiments, tests, and tooling. Do not add Python artifacts to `finite-capacity-causal-geometry/`. Use Lean only in documented formal lanes. Keep theorem, obligation, and guard names explicit and searchable, matching patterns such as `obl-006-*`, `*_theorem.md`, and `*_gate.rs`.

## Research Planning Guidelines

Maintain the distinction between conditional mathematical progress and physical nature-level claims. The internal conditional theorem in `finite-capacity-causal-geometry/` is recorded as complete under the Lean/fail-closed audit surface; physical promotion remains blocked by OBL-006 external evidence. `higher-dimensional-geometry-recovery/` closes the named Paper 2 conditional theorem for an explicit finite three-axis package at HDG-027 while remaining non-physical and non-unified. `curvature-from-finite-capacity-causal-networks/` closes the conditional Paper 3 curvature certificate at CURV-007 while remaining non-physical and non-unified. `gravitational-dynamics-from-finite-capacity-causal-networks/` closes the conditional Paper 4 dynamics certificate at DYN-008 while remaining non-physical and non-unified. `quantum-compatible-local-dynamics-from-finite-capacity-causal-networks/` closes the conditional Paper 5 quantum-compatible local dynamics certificate at QLD-008 while remaining non-physical and non-unified. `matter-gauge-observables-from-finite-capacity-causal-networks/` closes the conditional Paper 6 matter/gauge observables certificate at MGO-008 while remaining non-physical and non-unified. `particle-excitation-observables-from-finite-capacity-causal-networks/` closes the conditional Paper 7 particle-excitation observables certificate at PEO-008 while remaining non-physical and non-unified. `standard-model-candidate-observables-from-finite-capacity-causal-networks/` closes the conditional Paper 8 Standard-Model-candidate observables certificate at SMC-008 while remaining non-physical and non-unified. `observed-catalog-comparison-observables-from-finite-capacity-causal-networks/` closes the conditional Paper 9 observed-catalog comparison observables certificate at OCC-008 while remaining non-physical, non-unified, and non-promoting. `external-evidence-manifest-from-finite-capacity-causal-networks/` starts Paper 10 with EEM-001 closed as an upstream-binding and claim-boundary scaffold only.

Favor next steps that close named obligations, reduce ambiguity, produce external-review evidence, or advance the active paper frontier. For Paper 10, the strongest first move is EEM-002: define a finite external evidence record manifest without importing observed particle catalog recovery, physical Standard Model content, physical particle excitations, continuum quantum field theory, external Hilbert bundles, physical matter fields, physical gauge fields, physical quantum dynamics, simulation-only promotion, fit-only calibration, fit shortcuts, physical nature promotion, or unified-field-theory claims. Avoid adding wrappers, aliases, catalogs, or hardening layers unless a concrete missing dependency or regression is identified.

Use `skills/theorem-ladder-research/SKILL.md` when a future Codex run needs the reusable proof-ladder workflow distilled from `finite-capacity-causal-geometry/`, especially for new paper rungs that should avoid rereading the whole Paper 1 repo.

## Commit & Pull Request Guidelines

Use concise Conventional Commit-style messages, for example `docs: update frontier synthesis` or `test: add higher-dimensional guard`. Pull requests should state the research obligation addressed, files changed, verification commands, and whether the change is mathematical, tooling-only, or physical-evidence related.
