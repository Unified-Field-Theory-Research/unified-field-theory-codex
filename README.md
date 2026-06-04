# Unified Field Theory Codex Workspace

This repository is a macro-level Codex workspace for the
`UnifiedFieldTheoryResearch` local folder architecture. It is not the research project
by itself. It is the coordination layer that lets Codex inspect several sibling
repositories and answer program-level questions such as:

- What is the current theorem frontier?
- Which proof obligations or review gates are blocking promotion?
- What is the highest-leverage next research step?
- Which repo should be edited or audited next?

## Expected Local Layout

Use this repository inside a local root folder named:

```text
~/UnifiedFieldTheoryResearch/
```

The intended shape is:

```text
~/UnifiedFieldTheoryResearch/
  finite-capacity-causal-geometry/
  higher-dimensional-geometry-recovery/
  unified-field-theory-codex/
```

Each research repository should keep its own `AGENTS.md`, `README.md`, roadmap,
state files, proof logs, and verification commands. This Codex workspace reads
those local artifacts and synthesizes across them.

## Setup

Create the root folder, then clone the research repositories into it:

```bash
mkdir -p ~/UnifiedFieldTheoryResearch
cd ~/UnifiedFieldTheoryResearch

git clone https://github.com/Unified-Field-Theory-Research/finite-capacity-causal-geometry.git
git clone https://github.com/Unified-Field-Theory-Research/higher-dimensional-geometry-recovery.git
git clone https://github.com/Unified-Field-Theory-Research/unified-field-theory-codex.git
```

If your research program uses different repo names, keep the same pattern:
one root folder, multiple sibling research repos, and one meta Codex workspace.

## Using Codex At The Macro Level

Open Codex from `unified-field-theory-codex/` and ask questions that require
cross-repository context, for example:

```text
Look across ~/UnifiedFieldTheoryResearch and tell me what we should do next.
```

Codex should inspect each child repository's active state documents before
answering. For this project, the key files include:

- `finite-capacity-causal-geometry/AGENTS.md`
- `finite-capacity-causal-geometry/GPD/STATE.md`
- `finite-capacity-causal-geometry/GPD/ROADMAP.md`
- `finite-capacity-causal-geometry/GPD/frontier-status.md`
- `higher-dimensional-geometry-recovery/README.md`
- `higher-dimensional-geometry-recovery/docs/higher_dimensional_geometry_theorem.md`

## How To Adapt This Pattern

To reuse the architecture for another research program:

1. Keep a stable root folder name.
2. Put each research track in a sibling repository.
3. Give each repo its own `AGENTS.md` with local rules and claim boundaries.
4. Keep state, roadmap, proof, and review artifacts in predictable paths.
5. Use one meta Codex workspace to synthesize across all repos.

The important idea is separation of levels: child repos own implementation and
proof details; the meta workspace owns navigation, synthesis, and next-step
planning.

## Claim Boundary

This repository does not claim a completed unified field theory. It provides a
workflow for organizing AI-assisted research across repositories while keeping
claims tied to explicit artifacts, tests, formal checks, and external review
gates.
