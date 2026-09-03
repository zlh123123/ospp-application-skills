---
name: ospp-repo-investigator
description: "Investigate a chosen OSPP project by mapping its official requirements to the actual repository, branch, code paths, tests, benchmarks, and delivery risks. Use after project selection and before drafting an application or contacting the mentor."
---

# OSPP Repo Investigator

Determine what a chosen OSPP project really requires, where the work belongs in the current codebase, whether the baseline can run, and whether the mandatory scope is credible within the announced period. Produce evidence that a proposal writer and mentor-mail skill can reuse.

## Input and Default Behavior

Accept an OSPP project URL, project ID, project name, or a handoff from a project-selection skill. A natural-language request such as “调研这个项目，看看具体要改哪里” is sufficient. Resolve missing public information yourself; ask one concise question only when multiple repositories or branches remain genuinely ambiguous.

Treat a request for repository investigation as permission to perform read-only web research, clone the public repository into a new scoped directory, and inspect it. Build, test, setup, and execution commands require separate confirmation under the safety rules below. It does not authorize sending messages, opening issues, submitting pull requests, changing an existing user worktree, using paid services, or implementing the requested OSPP project.

Before starting, read [evidence-status.md](references/evidence-status.md). Use [investigation-report.md](references/investigation-report.md) when producing the final report or a persistent artifact.

## Verify the Project First

Read the current official OSPP project page and record its URL, project ID, retrieval date, duration, difficulty, languages, repository, mentor, required outputs, technical requirements, optional work, and explicit acceptance criteria.

Recheck whether the page publicly shows a selected student. If it does, stop before substantial repository work and explain that the project is no longer normally eligible, unless the user explicitly wants the investigation anyway. Note contradictions in the page instead of silently choosing one version of the requirements.

## Resolve the Repository and Revision

Verify the repository from the official page and project documentation. Do not assume the default branch is the target branch. Inspect repository branches, recent commits, contribution instructions, development documentation, and any repository-local agent instructions before running or editing anything.

Search relevant documentation, issues, pull requests, branches, and code to determine whether the requested capability already exists, is in progress, or has a related implementation. Public discussion is evidence of activity, not proof that another applicant has been selected.

Clone into a new, narrowly named directory such as `.ospp-workdir/{project-id}/` under the current workspace. If a local clone already exists, inspect its remote, branch, commit, and working-tree status before reuse. Preserve all user changes; never reset, overwrite, or clean them to make the investigation easier. Record the exact remote, branch, and commit used.

## Establish the Baseline

Identify the real project root and relevant manifests before choosing build commands. Inspect setup and dependency scripts before executing them. Before any command that installs dependencies, compiles code, runs tests, downloads models or data, opens services or ports, starts containers, or consumes substantial CPU, memory, disk, network, or credentials, state the exact operation and its risk profile, then wait for the user's explicit confirmation. Treat package managers, build systems, test runners, `setup.py`, `build.rs`, Makefiles, Dockerfiles, and downloaded scripts as potentially executable code. Read-only inspection such as `git status`, file listing, and source search may proceed without confirmation. Prefer documented, reproducible commands and isolated environments when dependencies are heavy or untrusted. Never use `sudo`, write outside the scoped clone or its normal dependency cache, or execute unchecked downloaded scripts. Ask separately before any privileged, system-wide, paid, destructive, or special-hardware operation. If confirmation or isolation is unavailable, default to static inspection and mark runtime evidence `partial` or `blocked`.

Attempt the smallest useful baseline in this order as applicable:

1. dependency or toolchain verification;
2. compilation or package build;
3. existing unit tests near the target module;
4. an official example or minimal service startup;
5. one current execution path closest to the OSPP requirement.

Do not confuse repository compilation with target-feature validation. Record commands, relevant versions, exit status, and concise output. Distinguish source failures from missing credentials, network restrictions, unavailable hardware, paid APIs, incompatible architecture, and other infrastructure blockers. Never claim an execution path was verified when only static inspection succeeded.

Do not expose or reuse secrets found in local configuration. Do not invoke paid APIs, provision cloud resources, or run on special hardware without the user's explicit authorization.

## Map Requirements to Code

Convert every mandatory project requirement into a requirement-to-code-to-verification entry. Trace the current execution path from its entry point through relevant interfaces, state, configuration, extension hooks, persistence, external calls, and tests.

For each requirement, identify:

- existing behavior and its evidence;
- relevant directories, files, types, functions, or interfaces;
- the likely integration point and compatibility boundary;
- what is missing versus what only needs extension or configuration;
- the smallest credible implementation slice;
- how the result can be tested or benchmarked;
- unresolved questions and their evidence status.

Be specific enough that another agent can open the named files and continue. Avoid vague conclusions such as “modify the Agent module” when the call path can be located. Do not invent exact APIs or file paths for a proposed design; label proposals separately from existing code.

## Evaluate Scope and Evidence

Separate mandatory work, optional work, already-implemented capability, adaptation of mature solutions, and genuinely new design. Evaluate engineering burden from environment setup, integration surface, data or benchmark construction, packaging, hardware, model services, and debugging cost.

Investigate external approaches only when they address a concrete project requirement. For each useful reference, state what can be reused, what must be adapted to this repository, and what dependency or design cost it introduces. A list of popular repositories is not a technical plan.

Identify existing tests, fixtures, datasets, benchmark scripts, baselines, and acceptance metrics. If evaluation data is missing, describe the smallest defensible validation set and mark any mentor-provided resource as unresolved rather than assuming it exists.

Finish with one of these conclusions, using the decision guide in [investigation-report.md](references/investigation-report.md):

- `continue`: the mandatory scope and environment appear credible;
- `continue with conditions`: specific questions or resources must be resolved first;
- `do not continue`: the project is unavailable, materially mismatched, or implausible within its period.

Do not produce numerical acceptance probabilities.

## Contribution Opportunities

Suggest at most two small, evidence-backed ways to demonstrate readiness, such as reproducing a real issue, adding a missing test, correcting a verified documentation problem, or publishing a requirement-related experiment. Suggest them only when they are distinct from the proposed OSPP scope and contribution guidance indicates that they are welcome. Do not recommend cosmetic or speculative contributions merely to attract attention. Do not implement, publish, or submit them unless the user separately asks.

## Deliverables and Handoff

Lead with the decision, then provide the report structure in [investigation-report.md](references/investigation-report.md). Include precise local file links when reporting on a cloned repository.

End with two compact handoff blocks:

- **Proposal evidence:** verified repository facts, feasible implementation slices, tests, benchmarks, and claims safe to include in an application.
- **Mentor questions:** only questions that remain material after public documentation and code inspection, especially about branches, datasets, infrastructure, expected baselines, evaluation, or scope.

Do not draft the application or mentor email in this skill.
