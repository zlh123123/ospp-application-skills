# Application Record Schema

Use YAML front matter or an equivalent Markdown structure. Keep unknown values as `unknown`; preserve old values in `history` instead of overwriting them.

```yaml
record_version: 1
application_id: "stable local slug"
created_at: "YYYY-MM-DD"
updated_at: "YYYY-MM-DD"
status: "discovery | selected | investigating | proposal | mentor_contact | submitted | selected_by_project | rejected | withdrawn | abandoned"
mode: "classic | pioneer"
# Backward compatibility: if an older record has no mode field, treat it as classic.
project:
  id: "official ID"
  title: "official title"
  url: "official URL"
  organization: "..."
  retrieval_date: "YYYY-MM-DD"
  public_selection_status: "..."
candidate:
  resume_source: "private path or description"
  strengths: ["resume-backed evidence"]
  constraints: ["..."]
artifacts:
  selector_handoff: "path or unknown"
  pioneer_direction_record: "path or unknown"
  pioneer_proposal: "path or unknown"
  investigation_report: "path or unknown"
  proposal_versions: ["path and created date"]
  proposal_reviews: ["reviewer, model, reviewed version, and findings path"]
  mail_thread: "path or unknown"
  submission_receipt: "path, URL, or unknown"
evidence:
  verified: ["claim + source"]
  partial: ["claim + limitation"]
  blocked: ["claim + blocker"]
  contradicted: ["claim + conflicting sources"]
open_questions: ["user or mentor decision"]
history:
  - at: "YYYY-MM-DDThh:mm:ssZ"
    from: "previous state"
    to: "new state"
    reason: "..."
    evidence: "artifact, URL, or user statement"
review:
  outcome: "unknown"
  observed_facts: ["..."]
  hypotheses: ["..."]
  next_changes: ["..."]
```

The record is an index and audit trail, not a duplicate of every artifact. Keep full proposals and email threads in separate files and reference them here.
