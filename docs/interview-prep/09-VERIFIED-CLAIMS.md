# Verified Claims

Prepared on 2026-09-15.

## Verified

- ShopSure uses Playwright Test and TypeScript.
- ShopSure includes UI tests, API tests, Page Object Model files, test data, QA docs, and GitHub Actions workflow.
- ShopSure final verification passed 11 Playwright tests after a small locator fix.
- Employee Shuttle Tracker uses Next.js App Router, React, TypeScript, Tailwind CSS, Leaflet, React Leaflet, OpenStreetMap tiles, Zod, and Vitest.
- Employee Shuttle Tracker has employee and driver/admin demo flows.
- AI Document Intelligence Platform uses React, Vite, Express, Prisma/SQLite, OpenAI SDK, Zod, pdf-parse, mammoth, tesseract.js, Tailwind, TanStack Query, and Vitest.
- AI Document Intelligence Platform supports PDF, DOCX, PNG, and JPG uploads.
- AI Document Intelligence Platform uses OpenAI `responses.parse` with Zod structured output when configured.
- Bookly AI, ReplyFlow AI, and Remindly AI use Express, React, Vite, OpenAI SDK, and demo fallback logic.
- Bookly AI has a WhatsApp-style booking flow and webhook endpoints.
- ReplyFlow AI drafts lead responses and has a human approval UI step.
- Remindly AI generates reminder copy and schedule steps.

## Partially Verified

- OpenAI integrations are verified from source code, fallback tests, and health endpoints, but live API-key calls were not manually tested during this pass.
- Employee Shuttle browser flows were previously smoke-tested locally, but no automated browser E2E suite exists for those flows.
- AI Document dashboard and API health were previously smoke-tested locally with seeded data, but fresh upload with a real document was not repeated in this pass.

## Do Not Claim

- Production authentication.
- Production database persistence for Employee Shuttle, Bookly AI, ReplyFlow AI, or Remindly AI.
- Real WhatsApp/SMS delivery.
- CRM, calendar, payroll, HR, payment, or fleet-provider integrations.
- OpenAI fine-tuning, embeddings, vector search, agents, or tool calling.
- Compliance certification.
- Cross-browser QA coverage for ShopSure; Chromium is the configured browser.
- That all code was manually written without AI assistance.

