# Downstream Handoff Schema

End an investigation with a compact packet that proposal and mail skills can consume without reopening the repository:

```yaml
project:
  id: "..."
  title: "..."
  url: "..."
  repository: "..."
  branch: "..."
  commit: "..."
decision: "continue | continue with conditions | do not continue"
verified_facts:
  - claim: "..."
    evidence: "file, command, or official page"
    status: "verified | partial | blocked | contradicted"
requirement_mapping:
  - requirement: "..."
    existing_code: "..."
    proposed_slice: "..."
    verification: "..."
proposal_safe_claims: ["..."]
candidate_strengths_to_emphasize: ["resume-backed only"]
contradictions: ["..."]
mentor_questions: ["material unresolved question only"]
```

Use `unknown` where a value was not verified. Keep local paths useful in the private report, but do not put them in a public email or application unless the user explicitly wants them.
