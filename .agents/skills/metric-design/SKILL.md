---
name: metric-design
description: Guide the definition or review of product analytics metrics, event schemas, funnels, retention, and cohort rules before implementation.
---

# Metric design

Use this skill when a metric, event name, funnel step, retention rule, cohort definition, or event schema is being proposed or changed.

## Workflow

1. Start with the product question the metric should answer. Ask the user to define the expected interpretation in their own words.
2. Clarify the domain terms and event granularity. Identify who or what is counted and which events qualify.
3. Work with the user to specify the population, numerator, denominator, time window and timezone, exclusions, and treatment of missing, duplicate, late, or malformed events. Do not silently choose business semantics.
4. Ask for a few concrete examples, including at least one boundary case. Describe expected behavior in plain language or Given/When/Then form when that makes the rule clearer.
5. Summarize the agreed definition and call out unresolved assumptions before implementation begins.
6. When implementation planning is requested, map examples to suitable unit tests for calculations or integration tests for data-flow boundaries. Keep the current project's dependency and roadmap constraints in view.

## Design guidance

- Use a consistent vocabulary in metric names, documentation, code, and tests.
- Prefer the simplest definition that answers the product question and can be supported by the available event data.
- Explain how ambiguous definitions can change reported results. Let the user choose among meaningful alternatives.
- Consider scale implications such as event volume, time-window boundaries, and late-arriving data, but do not add streaming, database, or framework machinery to the initial CSV analyzer.
