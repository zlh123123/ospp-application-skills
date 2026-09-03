# Candidate Profile

Use this only when the user's resume and natural-language request do not provide enough information to distinguish suitable OSPP projects. It is an optional reusable profile format, not a form users must complete.

```yaml
candidate:
  resume_source: "path, pasted text, or summary"
  demonstrated_skills:
    - "language or technology with evidence"
  demonstrated_projects:
    - "project, role, and relevant outcome"
  open_source_evidence:
    - "optional PR, issue, or contribution link"
preferences:
  recommendation_count: 3
  preferred_topics:
    - "agent evaluation"
  excluded_topics:
    - "routine frontend work"
  preferred_work_style: "research-heavy | balanced | implementation-heavy"
  acceptable_durations:
    - "2 months"
    - "3 months"
  acceptable_languages:
    - "Python"
  environment_limits:
    - "no required physical hardware"
  infrastructure_tolerance: "low | medium | high"
  weekly_availability: "optional"
  excluded_communities:
    - "optional"
```

Interpret this as a decision aid, not a scoring formula. A missing field is unknown; do not replace it with assumptions about the candidate.
