---
name: ospp-proposal-writer
description: "Draft, revise, or audit an OSPP project application using the official template, project requirements, candidate evidence, and repository investigation. Use after a project has been selected and technically investigated; do not use for project discovery or repository exploration."
---

# OSPP Proposal Writer

Write a credible project application that shows what the project requires, how it fits the current repository, what the applicant will implement, and how the result will be verified within the official period. The application must be technically useful to a mentor, not merely polished prose.

## Inputs

Accept a natural-language request plus any available project URL, repository-investigation report, resume, official template, example application, existing draft, and mentor correspondence. Do not require the user to fill a form.

Before drafting, obtain enough evidence to identify:

- the current official project requirements and public selection status;
- the target repository, branch or revision, existing architecture, and likely change surface;
- mandatory outputs, evaluation criteria, duration, and environment constraints;
- the applicant's demonstrated experience and any completed repository validation;
- material questions that remain unresolved.

The official template and an OSPP-recommended excellent application are required drafting inputs, not optional inspiration. Read [source-policy.md](references/source-policy.md) and [template-example-calibration.md](references/template-example-calibration.md) before writing any application prose. Read [proposal-checklist.md](references/proposal-checklist.md) before finalizing a draft.

## Mandatory Material Calibration Gate

Do not begin the proposal body until both of these passes are complete:

1. **Official-template pass.** Inspect the current official template itself, extract every required field, output format, filename rule, and stated minimum-content requirement, and record them in a template compliance list. The current-year official template overrides remembered rules, previous-year templates, examples, and user drafts. Do not rename, merge, or omit a mandatory field merely because another structure reads better.
2. **Excellent-example pass.** Inspect at least one OSPP-recommended excellent application and record only its reusable writing decisions: document organization, technical-detail level, repository grounding, feasibility evidence, implementation specificity, validation style, and schedule granularity. Do not copy its sentences, diagrams, personal details, project-specific claims, or outdated tool choices.

Use the supplied `项目申请模板.pdf` and `项目申请书示例.pdf` as the baseline pair when they are available. Their extracted calibration is recorded in [template-example-calibration.md](references/template-example-calibration.md), but the agent must still inspect the actual files when accessible and must replace the template constraints with a newer official template when the application year provides one.

If either required source is unavailable, do not silently claim full compliance. The agent may produce a clearly labelled preliminary outline, but must state which calibration pass is missing; it must not present that outline as a submission-ready application.

When accepting a handoff, use its project snapshot, requirement mapping, baseline evidence, proposal-safe claims, contradictions, and material mentor questions. Do not convert `partial`, `inferred`, or `blocked` items into facts.

If code-level evidence is missing, do not silently invent an implementation plan. Produce a clearly marked outline with unresolved items and recommend running `ospp-repo-investigator` first. This skill does not clone repositories or perform code investigation.

## Optional Independent Review

External review is disabled unless the user explicitly enables it or has supplied a standing preference for this application. Natural-language instructions are the interface: for example, “启用独立审阅，由 Claude Code MCP 的 Opus 审一轮” enables it, while “不启用外部审阅” disables it. When enabled, ask for the reviewer only if it cannot be inferred from the user's instruction or an explicitly configured reviewer. The writer and reviewer may be any tools or models the user chooses; when possible, use a different model or provider for the review so it is genuinely independent. In the maintainer's local setup, Claude Code may be invoked through the available Claude review MCP, but this is an example rather than a repository dependency.

Read [review-workflow.md](references/review-workflow.md) before invoking a reviewer. Send only the minimum necessary, sanitized materials. Before transmission, identify the reviewer/provider and disclose any new paid usage and that a third-party service may retain request data under its own terms. Obtain confirmation unless the user already authorized that reviewer and cost for this application. If the reviewer is unavailable, do not pretend that an independent review occurred; finish the normal checklist-based review and report the external review as skipped.

## Eligibility and Evidence Gate

Recheck the official project page before substantial drafting. If it publicly shows a selected student, warn the user and stop unless they explicitly want to continue for archival or comparative purposes.

Maintain an internal evidence ledger using the schema in [evidence-ledger.md](references/evidence-ledger.md). Every statement about existing code, successful builds, tests, contributions, experience, benchmark availability, or mentor agreement must be supported by repository evidence, execution evidence, the resume, or correspondence supplied by the user.

Never upgrade:

- static code inspection into runtime validation;
- a passing build into a working target feature;
- a proposed design into an existing interface;
- planned work into prior experience;
- an unsubmitted local change into an open-source contribution;
- silence or an empty public field into evidence of low competition.

## Structure

Follow the current official template exactly for required fields and submission form. The OSPP 2026 official minimum is project name, a detailed technical plan, and a detailed development schedule. Add only sections that improve the mentor's ability to judge feasibility, and keep all additions subordinate to the official fields.

A strong default structure is:

1. project background and concise requirement summary;
2. target repository and relevant external references;
3. technical method and feasibility;
4. implementation details organized around the project's mandatory requirements and current source structure;
5. testing, benchmark, and validation plan where these are not already integrated into implementation details;
6. schedule aligned with the official duration.

Do not force this structure when the official template or user specifies another. Do not add generic sections such as risk management, innovation, personal statement, or deliverable lists unless they provide project-specific information or are requested.

## Technical Content

For each mandatory requirement, explain in connected prose:

- what the repository already provides;
- which current files, modules, interfaces, or call paths constrain the work;
- the proposed change and why it belongs there;
- compatibility with existing hooks, protocols, persistence, configuration, or tests;
- the smallest credible implementation boundary;
- how the result will be tested or measured.

Use external projects, papers, standards, and industrial approaches only when they solve a named requirement. Link the original source and state the reuse boundary and adaptation cost. Do not produce a bibliography of famous tools without explaining their role.

Prefer a scoped, complete plan over an ambitious catalogue. Separate mandatory work from optional extensions. If the published requirements exceed the period, narrow the implementation honestly and identify the point requiring mentor confirmation rather than hiding the mismatch.

## Evaluation and Schedule

Map every promised feature to a test, benchmark, report, or observable behavior. Use existing repository tests and official datasets when available. When no benchmark exists, propose the smallest reproducible validation set and mark any mentor-provided data or infrastructure as unresolved.

The schedule must cover the full official period and reflect dependencies. Include repository familiarization only when it produces a concrete outcome. Reserve time for integration, tests, documentation, reports, and upstream review. Do not assign multiple high-risk subsystems to the same short interval merely to make the table fit.

## Writing Style

Use formal, direct Chinese or the language requested by the user. Match the language and register of the user's existing material. Prefer paragraphs for reasoning and bullets or tables only for true enumerations, mappings, or schedules. Preserve the user's preferred level of detail and heading style when revising an existing draft.

Remove AI-like writing patterns:

- ceremonial openings and broad claims about rapid technological development;
- repeated “首先、其次、最后” scaffolding;
- symmetrical lists created only for appearance;
- marketing adjectives without evidence;
- restating the project page at length;
- fake certainty, invented metrics, or unnecessary numerical targets;
- excessive headings and fragmented bullet points.

Do not imitate wording from successful examples. Extract structural lessons and evidence standards, then write specifically for the current project and applicant.

## Revision Mode

When revising an existing application, preserve sound content and the user's explicit formatting choices. Diagnose problems before rewriting. Change only the requested sections. List material factual defects outside the requested scope separately; do not rewrite them without the user's approval.

## Final Deliverables

Return or save, as requested:

- the application draft in Markdown or the user's required format;
- a concise requirement-coverage matrix;
- unresolved mentor questions kept outside the application unless the user requests otherwise;
- a fact-check summary listing claims that remain partial, inferred, or blocked.
- a brief material-calibration result confirming that every official template constraint passed and identifying which excellent-example patterns were applied or deliberately not applied.
- when independent review is enabled, the reviewer identity, findings, accepted and rejected suggestions, and resulting draft version.

Do not overwrite an existing application without preserving or clearly naming the new version. If the user requests PDF output, render it to page images and inspect every page for clipped text, malformed tables, illegible diagrams, and broken links. If rendering is unavailable, deliver the source artifact and explicitly state that PDF appearance is unverified.

Do not contact the mentor or submit the application in this skill.
