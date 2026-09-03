# Transition Rules

Use the narrowest state justified by evidence. A user request can move a record backward for revision, but do not erase the previous state.

| Current | Allowed next state | Required evidence or user action |
| --- | --- | --- |
| `discovery` | `selected`, `abandoned` | user selects a project, or explicitly drops the search |
| `selected` | `investigating`, `withdrawn` | project snapshot and selector handoff; user starts investigation or withdraws |
| `investigating` | `proposal`, `withdrawn` | report has requirement mapping and a `continue` decision; otherwise record conditions |
| `proposal` | `investigating`, `mentor_contact`, `submitted`, `withdrawn` | scope mismatch requires re-investigation, or user approves the version for contact/submission |
| `mentor_contact` | `investigating`, `proposal`, `submitted`, `withdrawn` | mentor reply reveals a requirement issue, requires proposal revision, or user decides next step |
| `submitted` | `selected_by_project`, `rejected`, `withdrawn` | official result or user-provided submission outcome |
| any active state | `abandoned` | user explicitly stops pursuing the project |

`continue with conditions` is not a state transition. Keep the record in `investigating` and put the conditions in `open_questions` until resolved. A rejected or unavailable project must not be returned to `selected` without a fresh official status check.

For a new attempt after rejection, create a new `application_id` or a clearly named successor record. Link the records, but do not overwrite the rejected attempt.
