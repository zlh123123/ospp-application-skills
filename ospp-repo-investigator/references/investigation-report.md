# Investigation Report

Use this structure for the final response or a saved Markdown report. Keep prose compact and expand only sections that materially affect the decision.

## Decision

State `continue`, `continue with conditions`, or `do not continue`, followed by the two or three decisive reasons.

- `continue`: no unresolved blocker affects a mandatory requirement, baseline environment, or feasible validation path.
- `continue with conditions`: a bounded uncertainty remains, but a concrete mentor answer, public resource, or fallback can resolve it without changing the core project.
- `do not continue`: the project is publicly unavailable, a mandatory requirement lacks a credible implementation or validation path, or the remaining uncertainty would change the core scope.

## Project Snapshot

- Project ID, title, organization, official URL, and retrieval date
- Public selection status
- Duration, difficulty, languages, mentor, repository, and target branch if verified
- Mandatory outputs, optional work, and explicit acceptance criteria
- Contradictions or ambiguities in official information

## Baseline Verification

| Check | Command or evidence | Result | Status |
| --- | --- | --- | --- |
| Repository revision | remote, branch, commit | value | `verified` |
| Build | exact command | concise result | status |
| Tests | exact command | pass/fail/blocked | status |
| Minimal runtime path | exact command or scenario | observed behavior | status |

Explain infrastructure failures separately from source-code failures. Do not paste large logs unless the user requests them.

## Current Architecture and Call Path

Describe the shortest useful call path and link the relevant local files. Identify extension points, persistence, configuration, hooks, external services, and tests that constrain the implementation.

## Requirement Mapping

| Requirement | Existing behavior | Code location | Proposed change | Verification | Status |
| --- | --- | --- | --- | --- | --- |

Cover every mandatory requirement. Separate existing code from proposed design.

## Evaluation and Benchmark

List available tests, fixtures, datasets, baselines, metrics, and reproducibility controls. If something is absent, state the smallest credible substitute and whether mentor input is required.

## Feasibility

Explain the dominant engineering work, genuine exploration, environment cost, coupled risks, and whether the mandatory scope fits the official period. Identify work that should be narrowed or treated as optional.

## Relevant External Approaches

Include only approaches that solve a named requirement. State the reuse boundary and adaptation cost for each one.

## Small Contribution Opportunities

Suggest no more than two real, scoped contributions and cite the evidence that makes each useful. Do not perform them automatically.

## Handoff

### Proposal Evidence

List claims safe to reuse, their evidence, implementation slices, and validation plan.

### Mentor Questions

List only unresolved questions whose answers would change the design, evaluation, resources, or decision to apply.

Use the field names in `ospp-project-selector`'s handoff schema where available. Preserve contradictory evidence rather than selecting the more convenient version, and flag it for mentor confirmation before it appears as fact in an application.
