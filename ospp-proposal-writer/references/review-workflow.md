# Optional Independent Review

Use this workflow only when the user enables external review. The reviewer may be Claude Code through an MCP, GPT through another agent or API, or another user-specified model. Do not require a particular vendor.

## Review Package

Give the reviewer the current draft plus the minimum evidence needed to judge it: official requirements, repository-investigation handoff, requirement-coverage matrix, unresolved facts, and user writing preferences. Remove private contact details, credentials, local-only paths, and unrelated resume content unless the user explicitly agrees to share them.

Before invoking a paid reviewer that the user has not already authorized, state the provider/model, the available cost estimate or that the cost is unknown, and wait for confirmation. Explain that third-party API or hosted-model services may retain request data according to their own terms. Treat an application and its repository findings as competitive material: do not transmit them to a new external provider without the user's informed confirmation.

Ask the reviewer to identify concrete defects rather than rewrite the application. It should check:

- factual claims against the supplied evidence and evidence status;
- coverage of every mandatory requirement and acceptance criterion;
- consistency between repository structure, proposed changes, tests, and schedule;
- feasibility within the official duration;
- unsupported metrics, invented interfaces, overclaiming, and hidden dependencies;
- prose that sounds generic, inflated, fragmented, or mechanically AI-generated.

The reviewer must cite the affected section and explain why a change is needed. It must not reward length, extra headings, symmetrical bullet lists, generic risk sections, exaggerated innovation claims, or numerical targets unsupported by a benchmark.

## Apply the Review

## Required Review Evidence and Verdicts

Supply the official template constraints, the user's presentation preferences, and the actual relevant excerpts of the excellent example (or a source-grounded extraction with page references), alongside the draft and technical evidence. Do not ask the reviewer whether a draft matches an example it has not received. User-provided drafts may calibrate desired breadth and presentation without being labelled successful applications.

Require separate PASS / FAIL / NOT VERIFIED verdicts for: official requirement coverage; technical mechanism depth; repository and reference grounding; example-relative breadth; visual explanation; rendered readability; and applicant-facing prose. Each verdict must identify a section, figure, or supplied source. A quoted test count is not independently verified merely because it appears in the draft. Missing sources require NOT VERIFIED, not approval.

For broad multi-module proposals, check that the overview and key sequence/state diagram required by the writer exist, explain distinct relationships, and agree with the prose. Inspect rendered figures when the reviewer supports images; a text-only reviewer must mark rendered readability NOT VERIFIED and leave that check to an image-capable reviewer or the writer. No blanket submission-ready verdict while a required dimension is FAIL or NOT VERIFIED; distinguish technical content approval from presentation approval.

Check that the proposal explains the positive design and a concrete usage/example path, rather than accumulating disclaimers, class names, and failure conditions. Reject review residue in the applicant-facing body. Review notes remain in a separate artifact; accepted technical corrections belong in the relevant sections.

## Apply Findings

Default to one review round unless the user requests more. Classify each finding as accepted, rejected, or requiring user/mentor confirmation. Apply only findings supported by the official requirements, repository evidence, candidate evidence, or a clear readability defect.

Preserve the applicant's voice and formatting preferences. Do not let the reviewer replace concrete prose with ceremonial language, add facts or experience, broaden the promised scope, or rewrite unaffected sections merely to make the document look polished. When a suggestion is only stylistic preference, keep the existing wording.

Save a new draft version rather than overwriting the reviewed version. Report the reviewer/model, review round, accepted changes, rejected suggestions with brief reasons, unresolved questions, and the path to the revised artifact. Never describe a self-review as independent review.
