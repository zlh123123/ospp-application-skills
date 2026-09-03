# Evidence Status

Use these labels consistently throughout an OSPP repository investigation.

| Status | Meaning | Acceptable evidence |
| --- | --- | --- |
| `verified` | Directly confirmed in the current investigation. | Official project page, source code at the recorded commit, successful command output, test result, or authoritative project documentation. |
| `partial` | Part of the claim is confirmed, but the full path or behavior was not demonstrated. | A component exists but integration was not run; build passes but the target flow was not exercised. |
| `inferred` | A reasoned proposal or likely conclusion, not existing verified behavior. | Architecture inference from call sites, proposed file placement, estimated implementation work. |
| `blocked` | Verification could not be completed for a named external reason. | Missing hardware, credential, paid service, dataset, unsupported architecture, or reproducible dependency failure. |
| `contradicted` | Two authoritative-looking sources disagree. | OSPP page versus repository documentation, or requirements versus supported platform metadata. |

Keep source types distinct:

- **Official requirement:** current OSPP project page.
- **Repository evidence:** code, tests, history, issues, pull requests, and documentation at a recorded revision.
- **Execution evidence:** an actual command and its observed result.
- **User-provided fact:** resume, environment, preference, or prior communication supplied by the user.
- **External reference:** another project, paper, or technical standard used for comparison.

Rules:

- Static code presence does not prove runtime behavior.
- A passing build does not prove a required feature works.
- An empty selected-student field does not prove low competition.
- A project description is not evidence that its dataset, benchmark, branch, or infrastructure is already available.
- Proposed file names, APIs, metrics, and schedules must be labeled `inferred` until confirmed.
- Preserve exact command errors when they change the feasibility conclusion, while omitting unrelated noise and secrets.

For baseline commands that can execute repository or dependency code, `verified` additionally requires the user's explicit confirmation of the command and its risk profile. If runtime verification was skipped for safety, use `partial` or `blocked` and explain why.
