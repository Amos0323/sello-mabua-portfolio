# ShopSure Demo

## Positioning

ShopSure is a compact QA automation framework for public e-commerce demo flows. It is the best first project for QA Analyst, Software Test Analyst, and QA Automation interviews.

## What To Show

- Playwright UI tests against Sauce Demo.
- REST API tests against DummyJSON.
- Page Object Model classes in `pages/`.
- Reusable users and product data in `fixtures/` and `test-data/`.
- QA documentation in `docs/`.
- GitHub Actions workflow in `.github/workflows/playwright.yml`.

## Launch Commands

```powershell
cd C:\Users\SelloMa\Downloads\sello-portfolio\portfolio-project-audit\ShopSure
npm install
npx playwright install chromium
npm run typecheck
npm test
npm run report
```

## Demo Script

Say:

> ShopSure demonstrates how I structure a maintainable automation suite. I separated page interactions into page objects, kept test data reusable, and covered login, cart, checkout, validation, and REST API behaviours.

Then show:

1. `tests/cart.spec.ts` for end-to-end shopping coverage.
2. `pages/CartPage.ts` and `pages/InventoryPage.ts` for Page Object Model structure.
3. `tests/api/products-api.spec.ts` for API validation.
4. The Playwright HTML report after `npm test`.

## QA Talking Points

- Positive and negative login coverage.
- Cart add/remove scenarios.
- Required checkout field validation.
- Product name and price consistency checks.
- API status and payload assertions.
- Failure screenshots configured through Playwright.

## Verified Results

- `npm run typecheck`: passed.
- Initial `npm test`: 10 passed, 1 failed due a broad locator in `CartPage.expectProductInCart`.
- Fix applied: `expectProductInCart` now checks the matching product locator count.
- Final `npm test`: 11 passed.
- `npm audit --audit-level=moderate`: found 0 vulnerabilities.

## Do Not Claim

- Do not claim cross-browser coverage; Chromium is the configured browser.
- Do not claim production e-commerce ownership; Sauce Demo and DummyJSON are public demo systems.
- Do not claim private credentials; the Sauce Demo password is public demo data read at runtime.

