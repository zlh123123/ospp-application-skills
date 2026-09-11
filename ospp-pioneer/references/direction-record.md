# Pioneer Direction Record

领航方向不是固定项目需求。记录官方方向快照和学生提出的课题假设，避免把二者混为一谈。

```yaml
mode: pioneer
direction:
  title: "官方方向名称"
  organization: "社区"
  url: "官方方向或领航列表 URL"
  retrieval_date: "YYYY-MM-DD"
  official_description: "官方原文的事实性摘要"
  public_competition_signals: ["...或 unknown"]
candidate:
  strengths: ["简历支持的能力"]
  constraints: ["用户明确的限制"]
screening:
  exploration_value: "high | medium | low"
  engineering_burden: "high | medium | low"
  evaluation_readiness: "high | medium | low"
  scope_risk: "high | medium | low"
  recommendation: "recommend | conditional | do not recommend"
hypotheses:
  - id: "H1"
    question: "可证伪的问题"
    minimum_scope: "..."
    method: "..."
    validation: "数据、场景、指标和失败判据"
    dependencies: ["...或 none"]
    status: "candidate | primary | conditional_extension | rejected"
open_questions: ["需要导师确认的事项"]
```

`official_description` 只保存方向事实；`hypotheses` 是学生提出的方案，必须明确标为推断或计划。没有公开竞争数据时使用 `unknown`，不能用空字段替代。
