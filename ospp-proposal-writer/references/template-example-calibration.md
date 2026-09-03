# Official Template and Excellent-Example Calibration

This reference records the reusable findings extracted from the maintainer-supplied baseline PDFs. It does not replace inspecting the actual source files for a real application.

## Baseline Sources

- `项目申请模板.pdf`, SHA-256 `41ed8deb371c4a675fc7c45b6b012e6401a7cc459ec1a0c3ba9a858123a3ae50`.
- `项目申请书示例.pdf`, SHA-256 `9c4a60ab189a530796c53bac7d88360704ffb3fcf2604ac54d78d92697d6762b`.

The template PDF is an official application-material sheet. The example PDF is an OSPP-recommended application example for a GitHub Actions automation project. Treat the former as a requirement source and the latter only as a writing-calibration source.

## Template Compliance List

Before drafting, extract and record the current official wording for each item below:

| Constraint | Baseline extraction | Enforcement |
| --- | --- | --- |
| Application format | Project application must be submitted as PDF | A non-PDF source may be drafted, but submission readiness cannot pass until a PDF is produced and checked |
| Required content | Project name; detailed project plan or technical plan; detailed development schedule | Each item must appear explicitly and contain substantive content |
| Separate resume | Resume is submitted separately as PDF | Do not use proposal sections as a substitute for the resume |
| Filename | The official sheet defines the proposal and resume filenames | Copy the current-year rule exactly; do not rely on the baseline's older ordering |

The minimum fields are a floor, not a complete writing outline. Repository links, technical methods, implementation details, tests, and evaluation may sit inside the detailed technical plan. Optional sections must not obscure the official fields.

At the end, mark every extracted constraint as `PASS`, `FAIL`, or `UNKNOWN`. Any `FAIL` or material `UNKNOWN` means the document is not submission-ready.

## Excellent-Example Lessons

The baseline example supports the following mandatory calibration dimensions:

| Dimension | Reusable lesson | What not to copy |
| --- | --- | --- |
| Organization | Start from project requirements and related repositories, then explain technical feasibility, implementation details, and schedule | Its exact numbered headings or table of contents |
| Requirement decomposition | Give each published requirement a visible implementation discussion | Its project-specific GitHub Actions subtasks |
| Repository grounding | Name the relevant repositories and explain the observed workflow before proposing changes | Repository-specific claims, links, or architecture from ShardingSphere |
| Technical detail | Explain triggers, state or data flow, APIs, libraries, permissions, and integration points where they affect feasibility | Old dependency versions, copied code blocks, or unnecessary low-level detail |
| Feasibility evidence | Connect a technology choice to concrete prior experience, inspection, prototype, build, or test evidence | Personal history or proficiency claims belonging to the example applicant |
| Reuse analysis | When citing an existing solution, state which part can be reused and which part still requires adaptation | A link-only catalogue of tools |
| Implementation specificity | Move from current behavior to the intended behavior and describe the change boundary | Length for its own sake or speculative interfaces |
| Schedule | Assign concrete technical outputs, integration, testing, and documentation to dated stages | The example's old dates or its two-stage split when unsuitable |

These lessons are not permission to imitate the example's prose. The new application must be written from the target project's current requirements, repository evidence, applicant evidence, and official schedule.

## Required Pre-draft Note

Before writing, maintain a short internal note containing:

```text
Official template: <source, year, retrieval date>
Required fields: <exact list>
Output and filename rules: <exact rules>
Excellent example: <source and year>
Patterns to apply: <project-specific choices>
Patterns rejected as outdated or irrelevant: <choices and reasons>
```

Do not expose this note in the proposal unless the user requests it. Its purpose is to prevent drafting from starting with a generic structure or remembered OSPP conventions.

## Final Comparison

After drafting, compare the finished application against both sources:

- Template comparison: confirm every required field, format rule, filename rule, and schedule requirement.
- Example calibration: confirm the proposal has comparable requirement coverage, repository grounding, technical specificity, feasibility evidence, and schedule concreteness.
- Non-copying check: confirm no distinctive wording, diagram, personal data, or project-specific claim was transferred from the example.

Report the result concisely. Template compliance is pass/fail. Example comparison is a calibration judgment, not a requirement to reproduce the example's length or section layout.
