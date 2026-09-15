# Technical Interview Q&A

## Portfolio

Q: Which project should we look at first?

A: Employee Shuttle Tracker, because it demonstrates a full user workflow with two roles, operational status, map visibility, validation, tests, and a production build. For QA-specific roles I would also show ShopSure early because it is the clearest automation project.

Q: Did you use AI to build these projects?

A: I used AI-assisted development as a coding partner. I defined the requirements, reviewed the generated code, ran tests, debugged failures, validated the behaviour, and removed or downgraded claims that were not supported by the source. I should not say AI did everything, and I should not say I manually wrote every line without assistance.

## ShopSure

Q: Why use Page Object Model?

A: It keeps page interactions separate from the test intent. The tests read like business scenarios, while locator and interaction details live in page classes such as `LoginPage`, `InventoryPage`, `CartPage`, and `CheckoutPage`.

Q: What bug did you fix during preparation?

A: One cart assertion used a locator that could match multiple product names. I changed it to verify the requested product appears exactly once. The full suite then passed with 11 tests.

## Employee Shuttle Tracker

Q: Is the driver tracking real GPS?

A: The app supports browser GPS permission and also a no-GPS demo mode. For interview demos, I use no-GPS mode so the flow is reliable. I would not claim production fleet tracking.

Q: What would you improve next?

A: I would add a backend database, production authentication, route history, push notifications, and mobile end-to-end tests.

## AI Document Intelligence Platform

Q: What exactly does OpenAI do here?

A: The app extracts text first, then calls OpenAI Responses parsing with a Zod schema for the selected document type. OpenAI returns structured fields. If OpenAI is unavailable, deterministic fallback extraction runs so the review workflow can continue.

Q: How is risk handled?

A: The pipeline validates extracted fields, checks document-specific risk rules, stores risk flags, and sends the document to human review with audit events.

## Bookly AI

Q: What prevents the assistant from inventing slots?

A: The prompt restricts the available Friday slots, and the fallback logic only recognizes the configured `AVAILABLE_SLOTS` array.

## ReplyFlow AI

Q: Is the reply sent automatically?

A: The UI includes an approval step. For demo purposes, it shows "Approve & send", but I should not claim production WhatsApp delivery unless a real provider is configured.

## Remindly AI

Q: Is there a real scheduler?

A: The source creates schedule steps and timestamps through `/api/schedule`, but it does not include a persistent background job queue or delivery provider. I should present it as a workflow demo, not a production reminder service.

