# AI Document Intelligence Platform Demo

## Positioning

AI Document Intelligence Platform is the strongest AI and enterprise workflow project. It fits AI Automation Specialist, Systems Analyst, QA Analyst, and Technical Operations conversations.

## Launch Commands

```powershell
cd C:\Users\SelloMa\Downloads\sello-portfolio\portfolio-project-audit\ai-document-intelligence-platform
npm install
npm run setup
npm run dev
```

Open:

- Web app: `http://localhost:5173`
- API health: `http://localhost:3001/api/health`

## Optional AI Configuration

Create `.env.local` with:

```text
OPENAI_API_KEY=your_key_here
OPENAI_MODEL=gpt-5.4-mini
```

During this preparation pass, OpenAI credential testing was not performed. The source supports OpenAI mode, and the app also falls back to deterministic extraction when OpenAI is unavailable.

## Demo Script

Say:

> This platform models a document operations workflow: upload a business document, extract text, classify it, extract structured fields, validate the data, flag risks, send it to human review, and export approved results.

Then show:

1. Dashboard metrics and review queue.
2. Documents list with status, type, confidence, and risks.
3. Upload screen and supported formats: PDF, DOCX, PNG, JPG.
4. Review screen showing extracted text, extracted fields, risks, validation issues, and audit events.
5. Reviewer decision and export options.

## Verified AI/API Behaviour

- `server/services/text-extraction.ts` extracts text from PDF via `pdf-parse`, DOCX via `mammoth`, and images via `tesseract.js`.
- `server/services/ai-extraction.ts` uses the OpenAI SDK and `responses.parse`.
- The model output is constrained with Zod schemas through `zodTextFormat`.
- `server/services/pipeline.ts` falls back to deterministic extraction if OpenAI is unavailable.
- The pipeline validates extracted data, detects risks, updates document status, and writes audit events.

## Verified Results

- `npm run lint`: passed.
- `npm run typecheck`: passed.
- `npm test`: 5 files, 10 tests passed.
- `npm run build`: passed.
- Local app/API smoke test previously rendered the seeded dashboard and `/api/health` returned 200.
- `npm audit --audit-level=moderate`: reported 23 vulnerabilities.

## Do Not Claim

- Do not claim the OpenAI key path was manually tested with a real key during this pass.
- Do not claim OCR accuracy beyond Tesseract integration.
- Do not claim production-grade security, authentication, or compliance.
- Do not claim embeddings, vector search, fine-tuning, or tool calling.

