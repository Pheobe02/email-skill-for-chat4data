# Chat4Data Skills Repository

This repository stores reusable Chat4Data agent skills, starting with the `customer-email` skill used to draft high-quality customer support replies.

The structure and writing style are tailored for Chat4Data workflows and operational needs.

## What Is In This Repo

- Production-ready skill definitions
- Operational writing rules for support scenarios
- Repeatable workflows for multilingual customer replies

Current skills:
- `customer-email`: customer support email drafting and response QA

## Repository Structure

```text
.
├── README.md
└── skills
    └── customer-email
        └── SKILL.md
```

## Skill Format

Each skill lives in its own folder under `skills/` and should include:

- `SKILL.md`: the canonical instruction file
- Optional support assets (for example `references/`, `scripts/`, `templates/`)

Recommended skeleton:

```text
skills/<skill-name>/
├── SKILL.md
├── references/
├── scripts/
└── templates/
```

## Included Skill: `customer-email`

Path: `skills/customer-email/SKILL.md`

This skill is designed for Chat4Data support operations and covers:

- Extraction-failure reply handling
- Speed-related inquiries
- Agent-intent misunderstanding cases
- Out-of-scope feature requests
- Subscription and payment issues
- Roadmap communication
- GDPR/account deletion response flow
- Bilingual output rules (Chinese + customer language)

It also includes:

- v3.0.0 (2026-04-21) upgrade guidance for extraction scenarios
- Subject-line quality requirements
- Strict pre-send self-check checklist
- Case logging rules for long-term quality improvement

## Quick Start

1. Open the target skill file under `skills/`.
2. Copy or adapt the instruction blocks for your support flow.
3. Keep outputs aligned with customer language and scenario-specific rules.
4. Validate reply quality with the self-check section before sending.

## Design Principles

This repository follows four practical principles:

- Specific over generic: give concrete causes and next steps
- Workflow-first: encode repeatable operational sequences
- Multilingual correctness: keep language output aligned with customer language
- Safety and traceability: include escalation and case logging requirements

## Contributing

When adding or updating a skill:

1. Create or update `skills/<skill-name>/SKILL.md`.
2. Keep sections explicit: trigger conditions, workflow, templates, and validation checklist.
3. If you add references/templates/scripts, place them in the same skill directory.
4. Update this `README.md` with the new skill summary.

## Roadmap

Planned future additions:

- More Chat4Data operation-focused skills (QA, billing ops, triage)
- Structured references for edge-case handling
- Lightweight tooling around skill validation

## License

No explicit license is defined yet. Add one before external reuse.
