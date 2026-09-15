# ReplyFlow AI Demo

## Positioning

ReplyFlow AI is a lead-response automation demo. It is strongest for AI Automation Specialist, Systems Analyst, and Technical Operations interviews where speed, triage, and controlled drafting matter.

## Launch Commands

```powershell
cd C:\Users\SelloMa\Downloads\sello-portfolio\portfolio-project-audit\replyflow-ai
npm install
npm run dev
```

Open:

- Web app: `http://127.0.0.1:4321`
- API health: `http://127.0.0.1:4322/api/health`

## Demo Script

Say:

> ReplyFlow AI turns incoming leads into a controlled response workflow. It drafts a reply, classifies interest and urgency, summarises the lead, and keeps a human approval step before sending.

Then show:

1. Lead inbox.
2. Select a lead.
3. Generate reply.
4. Review interest, urgency, and summary.
5. Approve and send to show the human-in-the-loop step.

## Verified AI/API Behaviour

- `server/index.mjs` uses OpenAI only when `OPENAI_API_KEY` exists.
- It calls `client.responses.create`.
- It requests a JSON object with keys `reply`, `summary`, `interest`, and `urgency`.
- It validates urgency against Low, Medium, and High before returning data.
- It has fallback lead classification and draft generation in `server/logic.mjs`.
- It exposes `/api/draft`, `/api/health`, and a WhatsApp webhook route.

## Verified Results

- `npm test`: 3 tests passed.
- `npm run build`: passed.
- `npm audit --audit-level=moderate`: found 0 vulnerabilities.
- Prior API smoke test returned demo-mode draft response and 400 validation for missing lead fields.

## Do Not Claim

- Do not claim CRM persistence.
- Do not claim production WhatsApp sending.
- Do not claim advanced lead scoring beyond the local rules and AI prompt.

