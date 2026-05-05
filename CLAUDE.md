# CLAUDE.md — AmanaTrade HQ

## Project Identity

AmanaTrade is a startup project focused on building trust infrastructure for social commerce in Northern Nigeria, starting in Kano.

The initial product is a mobile-first PWA that helps small professional sellers and individual buyers secure WhatsApp-based transactions using an escrow-like flow.

Initial MVP scope:
- Geography: Kano first, then Northern Nigeria.
- Language: Hausa-first, English second.
- Users: small professional sellers and individual buyers.
- Product categories: clothing and shoes only.
- Channel: WhatsApp/social commerce.
- Payment priority: Nigerian bank transfer / USSD / payment provider integrations, not card-first.
- Goal: validate trust, payment behavior, and merchant adoption before scaling.

## Repository Purpose

This repository is the strategic headquarters of the project.

It is NOT the application code repository.

This repository is used to create:
- business strategy
- market research
- finance and funding strategy
- legal and regulatory analysis
- product requirements
- UX and design briefs
- technical architecture
- marketing and operations planning
- research backlog
- decision tracking
- human action tracking

Do not build app code in this repository.

## Operating Rules

1. Never invent facts, numbers, laws, market data, or funding sources.
2. Always distinguish between facts, assumptions, recommendations, and open questions.
3. Any weak or missing information must be recorded.
4. Any research need must be added to `docs/00_master/RESEARCH_BACKLOG.md`.
5. Any question for Aboubakar must be added to `docs/00_master/AGENT_QUESTIONS.md`.
6. Any task requiring human action must be added to `docs/00_master/HUMAN_ACTIONS.md`.
7. Any strategic decision must be added to `docs/00_master/DECISION_LOG.md`.
8. Do not create new files or folders outside the planned structure without asking first.
9. Do not make legal conclusions. Prepare questions for qualified Nigerian legal counsel.
10. Do not assume direct fund custody is legal. Treat escrow and payment flows as high-risk until validated.
11. Keep the MVP narrow: Kano, WhatsApp sellers, clothing and shoes, small transaction values.
12. Prioritize execution, clarity, and decision-making over long theoretical reports.

## Output Style

Write in clear French unless the file requires English for technical reasons.

Use structured Markdown:
- context
- objectives
- key assumptions
- findings
- open questions
- recommended next actions

Avoid vague advice. Every recommendation should lead to a decision, research task, or action.

## Research Rules

When reviewing research files:
1. Identify useful facts.
2. Assess source quality.
3. Extract implications for AmanaTrade.
4. Flag missing information.
5. Create research requests when needed.
6. Update the relevant business, finance, legal, product, tech, or marketing files.

Raw research goes into:
`docs/08_research/[category]/raw/`

Reviewed research goes into:
`docs/08_research/[category]/reviewed/`

## Handoff Philosophy

The future app repository will be separate from this HQ repository.

This HQ repository must eventually produce:
- `docs/04_product/PRD.md`
- `docs/04_product/MVP_SCOPE.md`
- `docs/04_product/DESIGN_BRIEF.md`
- `docs/05_tech/TECH_ARCHITECTURE.md`
- `docs/05_tech/PAYMENT_FLOW.md`
- `docs/05_tech/DEVELOPMENT_HANDOFF.md`

These files will guide the future PWA development.