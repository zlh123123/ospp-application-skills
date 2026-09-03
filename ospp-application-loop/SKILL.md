---
name: ospp-application-loop
description: "Track an OSPP application from project selection through repository investigation, proposal, mentor correspondence, submission, and outcome review. Use when the user wants to continue, switch, or review an application workflow rather than perform one stage alone."
---

# OSPP Application Loop

Maintain a durable, human-readable record for each OSPP project application. This skill coordinates the four stage skills; it does not replace their domain work. Read [record-schema.md](references/record-schema.md) when creating or updating a record, and [transition-rules.md](references/transition-rules.md) when deciding what can happen next.

## Input

Accept a project URL or ID, an existing application record, a directory containing application materials, or a natural-language request such as “继续这个申请”“这个项目没中，帮我复盘” or “换一个项目”. If several records match, ask the user to choose one. Do not make the user fill a formal form.

## Core Workflow

Create one record per project and preserve its history. By default store it at `.ospp-applications/{application_id}/record.md` under the user's chosen workspace; if the user already has an application directory, use that instead and state the path. Do not silently put private records in a public Git repository. Store the official project snapshot, candidate constraints, selector handoff, repository-investigation handoff, proposal versions, mentor thread, submission state, and outcome. Record retrieval dates and source links so time-sensitive OSPP facts can be refreshed rather than silently reused.

At each request, report the current status first, identify the next permitted stage, and state missing evidence or user decisions. Route work to the relevant skill:

- project discovery or replacement -> `ospp-project-selector`;
- repository, branch, baseline, or scope investigation -> `ospp-repo-investigator`;
- application drafting, revision, or PDF checking -> `ospp-proposal-writer`;
- mentor first contact, reply, follow-up, or closing -> `ospp-mentor-mail`.

Individual skills produce their native outputs; they do not write this unified record when invoked independently. The loop reads those outputs and updates the record. Do not invoke later stages merely because an earlier stage exists. Sufficient investigation means the report concludes `continue` or `continue with conditions`, mandatory requirements have requirement-to-code mappings, and no unresolved `blocked` item prevents the proposed validation path. A mentor email may use verified project facts but must not claim unverified work. A submission is only recorded after the user confirms that it was submitted.

## State and History

Use the controlled states in [transition-rules.md](references/transition-rules.md). Every transition includes a timestamp, reason, source or artifact, and unresolved items. Never delete a rejected, withdrawn, or superseded record; mark it inactive and preserve the final materials and review notes. Keep secrets and unnecessary personal identifiers out of records intended for GitHub or other shared locations.

When incorporating a newer handoff, preserve verified evidence with its original source and retrieval date, replace partial or inferred claims only when newer evidence supports the replacement, and mark project-page, branch, commit, or deadline facts stale when their source changes. Never turn contradicted evidence into verified evidence without recording how the conflict was resolved.

## Failure and Resubmission

When a project is rejected, selected by someone else, withdrawn, or abandoned, distinguish the observed outcome from hypotheses about why it happened. Capture the final public status, what was actually submitted or sent, mentor feedback if any, evidence gaps, and one or two changes for the next attempt. Do not infer that wording, prior contributions, or competition caused rejection without evidence. Starting a new application may reuse general candidate evidence, but copy project-specific facts only after refreshing the official page and repository.

## Output

Return a concise status summary, the record path or proposed record location, the next action, and blockers or confirmations needed. When handing off, include the fields required by the downstream skill's schema. Do not clone repositories, edit applications, send email, upload files, or submit an application unless the user explicitly asks for that stage and its own safety conditions are satisfied.
