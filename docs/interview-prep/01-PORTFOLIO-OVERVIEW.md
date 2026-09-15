# Portfolio Interview Overview

Prepared on 2026-09-15 from local source inspection and command verification.

## Strongest Projects Overall

1. Employee Shuttle Tracker: strongest visual full-stack demo for systems, operations, and workflow thinking.
2. ShopSure: strongest QA automation proof because it has Playwright UI/API coverage, Page Object Model, test data, HTML reporting, and CI workflow.
3. AI Document Intelligence Platform: strongest AI plus enterprise workflow project because it combines upload, extraction, validation, risk review, and export.

## Role Fit

| Role | Best Projects | Why |
| --- | --- | --- |
| Technical Operations Specialist | Employee Shuttle Tracker, AI Document Intelligence Platform, Remindly AI | Shows operational visibility, process status, validation, scheduling, and support-minded workflows. |
| QA Analyst | ShopSure, Employee Shuttle Tracker, AI Document Intelligence Platform | Shows UI/API automation, regression logic, validation checks, error states, and test discipline. |
| Junior QA Automation Engineer | ShopSure, Employee Shuttle Tracker, AI Document Intelligence Platform | Best evidence of automated tests, TypeScript, Page Object Model, Vitest, and build validation. |
| Software Test Analyst | ShopSure, AI Document Intelligence Platform, Employee Shuttle Tracker | Strongest mix of requirements traceability, validation rules, risk checks, and repeatable verification. |
| Systems Analyst | Employee Shuttle Tracker, AI Document Intelligence Platform, ReplyFlow AI | Shows workflow modelling, user roles, status transitions, data capture, and process automation. |
| AI Automation Specialist | AI Document Intelligence Platform, ReplyFlow AI, Bookly AI | Shows OpenAI-backed automation, structured extraction, draft generation, and fallback handling. |

## Demo Order

1. Practice Employee Shuttle Tracker first.
2. Practice ShopSure second.
3. Practice AI Document Intelligence Platform third.
4. Use ReplyFlow AI, Bookly AI, and Remindly AI as shorter AI automation examples.

## High-Level Positioning

Say:

> My portfolio focuses on QA automation, enterprise workflow validation, systems support, and practical AI-assisted automation. I chose projects that demonstrate how I analyse user workflows, identify risks, test core paths, and build small systems that make operations clearer.

## Important Honesty Rules

- Do not say all apps are production enterprise systems.
- Do not say the demo auth is production-ready.
- Do not say OpenAI was live-tested with a real API key during this preparation pass.
- Do not claim embeddings, vector search, tool calling, fine-tuning, payment processing, or production WhatsApp sending unless the source code actually includes it.
- Do say the AI projects support demo fallback mode when no `OPENAI_API_KEY` is configured.

## Verification Summary

| Project | Verification Result |
| --- | --- |
| ShopSure | `npm run typecheck` passed. `npm test` passed after a small locator fix. `npm audit` found 0 vulnerabilities. |
| Employee Shuttle Tracker | `npm run lint`, `npm run typecheck`, `npm test`, and `npm run build` passed. `npm audit` reported current dependency vulnerabilities. |
| AI Document Intelligence Platform | `npm run lint`, `npm run typecheck`, `npm test`, and `npm run build` passed. `npm audit` reported current dependency vulnerabilities. |
| Bookly AI | `npm test`, `npm run build`, and `npm audit` passed. |
| ReplyFlow AI | `npm test`, `npm run build`, and `npm audit` passed. |
| Remindly AI | `npm test`, `npm run build`, and `npm audit` passed. |

