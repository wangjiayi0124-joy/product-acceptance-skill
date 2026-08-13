# Product Acceptance Skill

A reusable Codex Skill that helps product managers turn requirement materials into a structured acceptance-test framework, execute tests safely, and deliver traceable test outputs.

它适用于网页、原型和其他可操作的功能验收场景。所有 PRD、链接、截图、会议记录和补充说明都被视为需求证据；测试框架会根据本次需求动态生成，而不是套用固定的角色、权限或终端清单。

## What it does

- Extracts verifiable rules, journeys, constraints, and open questions from requirement evidence.
- Builds a hierarchical test checklist: module → sub-module → feature / rule / journey → test case.
- Selects relevant coverage dimensions, such as permissions, routing, data states, exceptions, external handoffs, and compatibility.
- Requires confirmation of the test framework before execution and allows cases to be added during testing.
- Separates **Passed**, **Failed**, **Blocked**, and **Pending** results with clear evidence boundaries.
- Produces a complete checklist, a failed/blocked list, and readable CSV output for office suites such as DingTalk, Feishu, and WPS.

## Workflow

1. Provide the requirement materials and the acceptance target.
2. Review the generated test framework and confirm scope, accounts, test data, and allowed actions.
3. Let Codex execute the approved tests, pausing whenever expectations are ambiguous or an action may have external side effects.
4. Receive the checklist, issue/blocker list, pending cases, and import-ready CSV.

## Guardrails

- Do not assume that a change log, user role, login state, or device matrix applies unless the requirement evidence calls for it.
- Do not treat missing credentials, test data, permissions, external dependencies, or approval for side-effecting actions as product failures; record them as blockers.
- Ask before opening an external destination or performing actions such as create, submit, publish, pay, delete, change permissions, send messages, or download sensitive data.
- Keep issue descriptions readable: short facts, natural line breaks, and separate expected from actual behavior.
- Use native tables only when a target office product is specified. Otherwise, use portable CSV and do not assume a particular product.

## Install

Copy the `product-acceptance` folder into your Codex Skills directory:

```text
~/.codex/skills/product-acceptance/
```

Then start a new Codex task and say:

```text
Use $product-acceptance to create a test framework from my requirement materials and guide acceptance testing.
```

## Repository structure

```text
product-acceptance-skill/
├── README.md
├── LICENSE
└── product-acceptance/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/coverage-and-delivery.md
```

## License

MIT
