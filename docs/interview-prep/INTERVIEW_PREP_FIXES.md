# Interview Prep Fixes

Prepared on 2026-09-15.

## Fixed

### ShopSure locator assertion

Issue: The full Playwright suite initially had 10 passing tests and 1 failing test. The failure was in `CartPage.expectProductInCart`, where a broad product-name locator could resolve to multiple elements.

Fix: Changed the assertion to filter by the expected product name and require exactly one matching item.

Result: Full ShopSure suite passed with 11 tests.

## Remaining Non-Blocking Items

### Employee Shuttle Tracker dependency audit

`npm audit --audit-level=moderate` currently reports 13 vulnerabilities. The app still passed lint, typecheck, tests, and production build, but dependency upgrades should be completed before claiming production readiness.

### AI Document Intelligence Platform dependency audit

`npm audit --audit-level=moderate` currently reports 23 vulnerabilities. The app still passed lint, typecheck, tests, and production build, but dependency upgrades should be completed before production use.

### OpenAI live credential testing

The OpenAI integrations were verified from source code and fallback behaviour. A live `OPENAI_API_KEY` call was not manually tested during this preparation pass.

### Browser E2E coverage

Bookly AI, ReplyFlow AI, and Remindly AI have unit/API logic tests and successful builds, but they do not currently include browser E2E tests.

