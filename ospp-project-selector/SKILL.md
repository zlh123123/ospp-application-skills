---
name: ospp-project-selector
description: "Screen OSPP projects that do not publicly show a selected student against a candidate resume and stated constraints. Use when choosing OSPP projects, not when auditing a selected repository or drafting an application."
---

# OSPP Project Selector

Recommend a small number of OSPP projects that suit the candidate and do not currently publicly show a selected student. Treat this public signal as a built-in eligibility condition, not a preference the user needs to state. It is not proof that a project remains open or low-competition. The goal is a defensible shortlist, not a prediction of acceptance.

## Inputs

Use the resume supplied by the user as the primary source of demonstrated skills and experience. Accept a local file, pasted resume, or a user-provided profile. Treat ordinary natural-language requests as the normal interface: users may simply say what they enjoy, what they do not want to do, and ask for several projects.

Extract useful constraints from that description, including topic interests, work-style preferences, duration, environment tolerance, and excluded communities. Do not require the user to fill a form or enumerate technical constraints. Ask one concise follow-up only when an unknown constraint would materially change the shortlist, for example when the candidate has not said whether they can use required hardware or a heavy cluster. Default to three recommendations when no quantity is given.

Read [candidate-profile.md](references/candidate-profile.md) when the resume is incomplete or the user wants a reusable profile format.

Do not infer experience, availability, or prior open-source contributions that the resume does not support. Treat a preference as a soft constraint only when the user says it is negotiable; otherwise exclude conflicting projects.

## Current Project Evidence

Use the current official OSPP project list and each candidate's official detail page. Record the retrieval date and preserve the project ID and URL. For each shortlisted project, verify at least:

- project name, organization, duration, difficulty, languages, and stated technical requirements;
- mandatory deliverables and evaluation criteria;
- whether the official page currently shows a selected student;
- repository and mentor contact information when listed.

Exclude a project that currently shows a selected student unless the user explicitly asks to analyze it. Do not equate an empty selected-student field, a low displayed heat label, or no public discussion with low competition. Describe these only as observable signals; private applicants and mentor commitments are not observable.

If the project list has changed since a prior snapshot, identify new IDs separately from merely newly noticed projects. If publication time is unavailable, say so rather than claiming the project was posted today.

## Screening Method

For each viable project, assess these dimensions using only source-backed claims:

| Dimension | What to assess |
| --- | --- |
| Candidate fit | Direct overlap with demonstrated skills, adjacent skills that can be learned within the period, and hard gaps. |
| Exploration value | Whether the task includes an open technical question, experimental comparison, benchmark, evaluation design, or systems investigation rather than only feature implementation. |
| Engineering burden | Required environment setup, external dependencies, integration surface, packaging, hardware, data construction, and expected debugging cost. |
| Evaluation readiness | Existing benchmark, dataset, acceptance criteria, reproducible scenario, or a credible plan to construct one. |
| Scope and schedule | Whether mandatory outputs realistically fit the announced duration; flag coupled deliverables that make the scope risky. |
| Competition signals | Only public evidence such as selected-student status, visible heat, publication timing if known, and mentor/community interaction supplied by the user. |

Avoid fabricated numerical acceptance probabilities. A compact qualitative rating is allowed only when the evidence and uncertainty are both stated: `high` requires direct resume alignment and few hard constraints; `medium` allows one bounded gap; `low` means a material gap, opaque scope, or unavailable environment. Prefer rejecting a superficially relevant project that is dominated by routine adaptation, CRUD work, platform migration, or an environment requirement the user has ruled out.

## Output

Return at most the number requested. Start with a brief recommendation statement, then provide one entry per project with:

1. Official project link and current availability status.
2. What the student would actually build or investigate in concrete terms.
3. Why it fits or conflicts with the candidate's resume and stated preferences.
4. Exploration value, engineering burden, evaluation readiness, and scope risk.
5. Observable competition signals and what remains unknowable.
6. A clear recommendation: `recommend`, `conditional`, or `do not recommend`.
7. The smallest next validation step, normally a targeted repository investigation rather than an application draft.

Also list strong near-misses and the explicit reason for excluding them. Separate verified facts, user-provided facts, and inferences. Never represent a project as easy to win merely because it is not yet selected.

## Handoff

When the user chooses a project, produce a concise handoff packet following [handoff-schema.md](references/handoff-schema.md). Do not clone repositories, contact mentors, or submit applications in this skill.
