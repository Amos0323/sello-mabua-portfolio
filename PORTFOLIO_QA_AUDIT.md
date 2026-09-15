# Portfolio QA Audit

Audit date: 2026-09-15  
Portfolio: https://sello-mabua-portfolio.vercel.app/  
GitHub user: Amos0323

## Summary Table

| Project | Repository | Install | Lint | Typecheck | Tests | Build | Runtime | Main Flow | Status | Portfolio Decision |
|---------|------------|---------|------|-----------|-------|-------|---------|-----------|--------|-------------------|
| ShopSure | https://github.com/Amos0323/ShopSure | PASS | N/A | PASS | PASS, 11 Playwright tests | N/A | PASS via external test targets | PASS, login/cart/checkout/API tests | PASS | KEEP |
| Employee Shuttle Tracker | https://github.com/Amos0323/employee-shuttle-tracker | PASS, audit warnings | PASS | PASS | PASS, 9 Vitest tests | PASS | PASS | PASS, employee login/map and driver demo shift | PASS WITH ISSUES | KEEP |
| AI Document Intelligence Platform | https://github.com/Amos0323/ai-document-intelligence-platform | PASS, audit warnings | PASS | PASS | PASS, 10 Vitest tests | PASS | PASS | PASS, dashboard/API/seeded review data | PASS WITH ISSUES | KEEP |
| Relay - AI Workflow Studio | https://github.com/Amos0323/ai-workflow-studio | PASS, audit warnings | N/A | PASS via build | PASS, 4 Vitest tests | PASS | FAIL, dev/database setup unreliable | FAIL, Prisma db push fails | FIXABLE | REMOVE |
| AI Learning Support Ticket Automation | https://github.com/Amos0323/ai-learning-support-ticket-automation | FAIL | N/A | N/A | N/A | N/A | FAIL | FAIL, repository is empty | FAIL | REMOVE |
| Bookly AI | https://github.com/Amos0323/bookly-ai | PASS | N/A | N/A | PASS, 3 Node tests | PASS | PASS | PASS, built UI and booking API fallback | PASS WITH ISSUES | KEEP |
| ReplyFlow AI | https://github.com/Amos0323/replyflow-ai | PASS | N/A | N/A | PASS, 3 Node tests | PASS | PASS | PASS, built UI and lead draft API fallback | PASS WITH ISSUES | KEEP |
| Remindly AI | https://github.com/Amos0323/remindly-ai | PASS | N/A | N/A | PASS, 3 Node tests | PASS | PASS | PASS, built UI, reminder API, schedule API | PASS WITH ISSUES | KEEP |
| Sello Mabua Portfolio Website | https://github.com/Amos0323/sello-mabua-portfolio | N/A, static site | N/A | N/A | N/A | N/A, static site | PASS | PASS, navigation/cards/assets verified | PASS | KEEP |
| Cote Noire Course Website | https://github.com/Amos0323/New2 | PASS, audit warnings | N/A | N/A | N/A | PASS | PASS | PASS with content quality concern | PASS WITH ISSUES | REMOVE |

## 1. Projects Verified As Working

- ShopSure: TypeScript passes. Playwright suite passed after network access was allowed for `saucedemo.com` and `dummyjson.com`.
- Employee Shuttle Tracker: Lint, typecheck, Vitest, production build, employee sign-in, Leaflet map, driver sign-in, and no-GPS shift flow passed.
- AI Document Intelligence Platform: Lint, typecheck, Vitest, production build, local bootstrap, seed data, dashboard render, and `/api/health` passed.
- Bookly AI: Node tests, production build, built UI render, `/api/health`, `/api/respond`, and validation error handling passed in demo mode.
- ReplyFlow AI: Node tests, production build, built UI render, `/api/health`, `/api/draft`, and validation error handling passed in demo mode.
- Remindly AI: Node tests, production build, built UI render, `/api/health`, `/api/reminder`, `/api/schedule`, and validation error handling passed in demo mode.
- Portfolio Website: Static site renders, project cards link to existing retained repositories, and assets load.

## 2. Projects Repaired

- No project repositories were fully repaired and pushed during this audit.
- Portfolio website cleanup was completed by removing non-recruiter-ready project cards and correcting README accuracy.
- Relay repair attempt: updated Prisma packages inside the temporary audit clone and retried `db:push`, tests, and build. Tests and build still passed, but `prisma db push` continued to fail, so the project remains removed from the portfolio until fixed in its own repository.

## 3. Projects Removed From Portfolio

- Relay - AI Workflow Studio: removed because fresh local database setup fails at `prisma db push`, making the app unreliable for recruiter demonstration.
- AI Learning Support Ticket Automation: removed because the GitHub repository is empty.
- Cote Noire Course Website: removed because, although it builds and renders, it is weaker for the target QA/systems roles, has no README or test scripts, and contains unprofessional visible copy.

## 4. Projects Requiring Manual Verification

- Bookly AI, ReplyFlow AI, Remindly AI, AI Document Intelligence Platform, and Relay all contain OpenAI integration code. This audit verified their no-key demo or fallback paths, but did not verify live OpenAI calls because no credentials were used.
- ShopSure depends on public third-party targets. It passed when network access was approved, but future runs depend on `saucedemo.com` and `dummyjson.com` availability.

## 5. Bugs Discovered

- `ai-learning-support-ticket-automation` is an empty repository while the portfolio described a complete LMS ticket automation dashboard.
- `ai-workflow-studio` fails fresh database setup with `prisma db push`.
- `ai-workflow-studio` `db:seed` does not load `.env` when run as a plain `tsx prisma/seed.ts` script.
- `New2` displays "Welcome homies", which is not recruiter-safe language.
- Several repositories reported `npm audit` vulnerabilities during install: Employee Shuttle Tracker, AI Document Intelligence Platform, Relay, and New2.

## 6. Tests Performed

- `npm ci` or `npm install` for every non-empty Node project.
- `npm run typecheck` for ShopSure, Employee Shuttle Tracker, and AI Document Intelligence Platform.
- `npm run lint` for Employee Shuttle Tracker and AI Document Intelligence Platform.
- `npm test` for ShopSure, Employee Shuttle Tracker, AI Document Intelligence Platform, Relay, Bookly AI, ReplyFlow AI, and Remindly AI.
- `npm run build` for Employee Shuttle Tracker, AI Document Intelligence Platform, Relay, Bookly AI, ReplyFlow AI, Remindly AI, and New2.
- Browser checks for Employee Shuttle Tracker, AI Document Intelligence Platform, Bookly AI, ReplyFlow AI, Remindly AI, New2, and the portfolio website.
- API checks for AI Document Intelligence Platform, Bookly AI, ReplyFlow AI, and Remindly AI.

## 7. Missing Automated Tests

- Portfolio Website has no automated tests, which is acceptable for a static portfolio but should have link/asset checks if it grows.
- Bookly AI, ReplyFlow AI, and Remindly AI have backend logic tests but no browser/end-to-end tests.
- New2 has no declared test script.
- Relay has limited backend tests but lacks a reliable database setup and browser-level end-to-end tests.

## 8. Security And Configuration Concerns

- No secrets were printed or committed.
- AI projects correctly keep OpenAI usage on backend routes, but live OpenAI behavior still needs credential-based manual verification.
- Several repos report `npm audit` vulnerabilities. Do not run `npm audit fix --force` casually because it may introduce breaking dependency changes.
- Demo credentials in Employee Shuttle Tracker are clearly local demo credentials and are acceptable for a portfolio demo.

## 9. Recommended Portfolio Improvements

- Add a short "How to run locally" section to each retained repo.
- Add hosted demo URLs for the strongest apps.
- Add browser-level tests for Employee Shuttle Tracker and the three smaller AI apps.
- Fix Relay in its own repository before re-adding it.
- Consider consolidating the three small AI apps into one stronger case-study section if the portfolio starts to feel repetitive.
- Add screenshots or demo GIFs to each retained project README.

## 10. Strongest Projects For Recruiters

1. ShopSure
2. Employee Shuttle Tracker
3. AI Document Intelligence Platform
4. Bookly AI
5. ReplyFlow AI
6. Remindly AI
