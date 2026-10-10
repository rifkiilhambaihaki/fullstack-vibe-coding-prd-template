# Contributing

Thank you for helping improve the Full-Stack Vibe Coding PRD Template.

This repository is currently prepared for private review. A license has not yet been selected, so public contribution and redistribution terms are not yet established. Do not assume that planned public publication already makes the material open-source.

## Useful Contributions

We welcome reviewed proposals for:

- clearer PRD sections or instructions;
- profile-specific guidance;
- additional synthetic worked examples;
- ASCII wireframe corrections;
- Mermaid diagram corrections;
- stable-ID and traceability improvements;
- AI coding agent workflows and prompts;
- accessibility, security, privacy, or validation guidance;
- typo, navigation, and documentation fixes.

## Before Proposing a Change

1. Read the [README](README.md).
2. Review the [Master Template](templates/MASTER_FULLSTACK_PRD_TEMPLATE.md).
3. Use the [Worked Example](examples/RESEARCH_TASK_TRACKER_PRD.md) to understand cross-layer expectations.
4. Check the [PRD Workflow](docs/prd-workflow.md) and [AI Agent Guide](docs/ai-agent-guide.md).
5. Confirm that the proposal does not weaken approval, traceability, privacy, or anti-overclaim boundaries.

## Change Guidelines

### PRD section improvements

Explain:

- the ambiguity or missing use case;
- which project profiles are affected;
- whether the change is mandatory or conditional;
- which stable IDs or cross-references are affected;
- how a project author should validate the new guidance.

Avoid increasing complexity for every profile when the concern is only relevant to Complex applications.

### Examples

Examples must:

- be clearly fictional;
- use synthetic names, identifiers, records, and reserved domains such as `example.invalid`;
- distinguish proposed behavior from actual implementation evidence;
- include relevant scope, non-goals, decisions, and approval status;
- map critical features through requirements, UI/API/data, acceptance, and tests;
- avoid real research, customer, participant, financial, production, or credential data.

### Diagrams

Diagram changes should:

- retain valid Mermaid or readable ASCII structure;
- reference canonical IDs through metadata or nearby text;
- match route, API, service, data, and security contracts;
- show significant error or unauthorized branches where relevant;
- label proposed architecture honestly.

### AI-agent workflows

Agent prompts must be generic and environment-independent. They should:

- require PRD review before action;
- identify unresolved decisions;
- separate planning from implementation authority;
- require bounded scope and actual verification;
- prohibit fabricated test claims;
- require separate production/release approval.

## Privacy and Security

Never contribute:

- API keys, tokens, passwords, private keys, or credentials;
- `.env` or private configuration files;
- personal email addresses or private contact details;
- participant, customer, financial, or unpublished research records;
- internal hostnames, IP addresses, private paths, or private Drive links;
- production logs, database exports, backups, or service configuration;
- third-party material without confirmed redistribution rights.

If a sensitive value is discovered, do not quote it in an issue or review. Report only the affected file and finding type through an appropriate private channel.

## Documentation Checks

Before requesting review:

- confirm Markdown fences and tables are balanced;
- check relative links;
- preserve the 26-section master structure unless the proposal explicitly reviews a structural change;
- verify stable ID declarations and references;
- verify AC→FR and TEST→AC relationships;
- structurally validate Mermaid blocks;
- label actual Mermaid rendering separately from structural validation;
- scan the exact staged files for privacy and secrets;
- run `git diff --cached --check` when using Git.

Do not claim a check passed unless it was actually run.

## Commit and Review Style

Prefer small, focused changes. A proposed change should describe:

- problem and rationale;
- affected files/sections;
- validation performed;
- known limitations;
- any approval or versioning impact.

Suggested documentation commit types include:

```text
docs: clarify Small/MVP profile guidance
docs: correct API traceability example
docs: add synthetic accessibility-focused example
```

## License Proposals

License selection requires explicit owner approval. You may propose a license with rationale, but do not add or replace `LICENSE` without that approval.

## Code of Conduct

A formal Code of Conduct has not yet been adopted. Contributors should communicate respectfully, focus review on the artifact, and protect private or sensitive information.
