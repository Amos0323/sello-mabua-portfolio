# Remindly AI Demo

## Positioning

Remindly AI is a scheduling and reminder automation demo. It is useful for operations and AI automation roles because it shows a simple workflow that reduces missed appointments.

## Launch Commands

```powershell
cd C:\Users\SelloMa\Downloads\sello-portfolio\portfolio-project-audit\remindly-ai
npm install
npm run dev
```

Open:

- Web app: `http://127.0.0.1:4331`
- API health: `http://127.0.0.1:4332/api/health`

## Demo Script

Say:

> Remindly AI automates reminder copy and scheduling steps for appointments. It keeps the workflow simple: create an appointment, generate a concise reminder, and schedule confirmation, 24-hour, and 2-hour reminder steps.

Then show:

1. Weekly calendar.
2. Appointment list.
3. Generate reminder copy.
4. Send reminder.
5. Explain the schedule API and two reminder offsets.

## Verified AI/API Behaviour

- `server/index.mjs` uses OpenAI only when `OPENAI_API_KEY` exists.
- It calls `client.responses.create` for reminder text.
- The prompt instructs the assistant to stay below 55 words and not invent information.
- `server/logic.mjs` builds a confirmation, 24-hour reminder, and 2-hour reminder schedule.
- It exposes `/api/reminder`, `/api/schedule`, and `/api/health`.

## Verified Results

- `npm test`: 3 tests passed.
- `npm run build`: passed.
- `npm audit --audit-level=moderate`: found 0 vulnerabilities.
- Prior API smoke tests returned demo-mode reminder and valid schedule response.

## Do Not Claim

- Do not claim real SMS or WhatsApp delivery.
- Do not claim calendar provider integration.
- Do not claim background worker or queue processing.

