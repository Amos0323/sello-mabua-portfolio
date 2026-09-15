# Bookly AI Demo

## Positioning

Bookly AI is a focused AI automation demo for booking conversations. It is useful for AI Automation Specialist interviews and for explaining practical WhatsApp-style workflow automation.

## Launch Commands

```powershell
cd C:\Users\SelloMa\Downloads\sello-portfolio\portfolio-project-audit\bookly-ai
npm install
npm run dev
```

Open:

- Web app: `http://127.0.0.1:4311`
- API health: `http://127.0.0.1:4312/api/health`

## Demo Script

Say:

> Bookly AI shows a booking assistant pattern. A customer sends a message, the app detects booking intent and available slots, and the assistant replies without inventing unavailable times.

Then show:

1. The WhatsApp-style chat UI.
2. Send: `Can I book a haircut on Friday at 15:30?`
3. Show the assistant reply and selected slot.
4. Open the booking drawer and confirm the booking UI.
5. Show `/api/health` to explain OpenAI mode vs demo mode.

## Verified AI/API Behaviour

- `server/index.mjs` uses the OpenAI SDK when `OPENAI_API_KEY` is present.
- It calls `client.responses.create`.
- It loads `.env.local` from the project or shared workspace.
- It has `/api/respond`, `/api/health`, and WhatsApp webhook routes.
- `server/logic.mjs` provides deterministic fallback slot detection and replies.

## Verified Results

- `npm test`: 3 tests passed.
- `npm run build`: passed.
- `npm audit --audit-level=moderate`: found 0 vulnerabilities.
- Prior API smoke test returned demo-mode booking response and 400 validation for missing message.

## Do Not Claim

- Do not claim real WhatsApp Business delivery is fully configured.
- Do not claim database persistence.
- Do not claim payments, calendars, or staff scheduling integrations.

