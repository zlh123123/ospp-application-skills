# Handoff Schema

Use this compact packet when a user selects a project. Keep unknown values as `unknown`; do not fill gaps with inference.

```yaml
project:
  id: "official project ID"
  title: "official title"
  url: "official project URL"
  retrieval_date: "YYYY-MM-DD"
  public_selection_status: "not publicly shown selected | selected | unknown"
  repository: "URL or unknown"
  target_branch: "branch or unknown"
scope:
  mandatory_outputs: ["..."]
  acceptance_criteria: ["..."]
  duration: "..."
candidate:
  relevant_strengths: ["resume-backed evidence only"]
  hard_constraints: ["..."]
investigation:
  questions_to_verify: ["code-level or environment question"]
  claims_needing_evidence: ["claim that must not enter the proposal yet"]
  competition_signals: ["observable facts only"]
```

The repository investigator returns verified code facts, feasibility, validation evidence, contradictions, proposal-safe claims, and only material mentor questions. The proposal and mail skills consume those outputs rather than re-deriving repository facts.
