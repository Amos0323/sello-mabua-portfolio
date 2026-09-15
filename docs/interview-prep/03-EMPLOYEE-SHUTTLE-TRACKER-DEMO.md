# Employee Shuttle Tracker Demo

## Positioning

Employee Shuttle Tracker is the strongest project to practice first. It is visual, role-based, operational, and easy to connect to Technical Operations Specialist, Systems Analyst, and QA conversations.

## Launch Commands

```powershell
cd C:\Users\SelloMa\Downloads\sello-portfolio\portfolio-project-audit\employee-shuttle-tracker
npm install
npm run dev
```

Open:

- Employee app: `http://localhost:3000`
- Driver/admin portal: `http://localhost:3000/driver`

## Demo Credentials

Employee:

```text
Employee number: 240001
Password: Demo123!
```

Driver/admin:

```text
Driver ID: DRIVER-DEMO
Password: Demo123!
```

## Demo Script

Say:

> This app solves an operations visibility problem: employees need to know where the shuttle is, whether service is delayed, and what stop is next. I built an employee tracker and a driver console so the same workflow can be seen from both sides.

Then show:

1. Employee login and live tracker.
2. Map, route line, next stop, ETA, distance, and status.
3. Driver portal login.
4. Start shift using the no-GPS demo mode.
5. Confirm stop reached and update service status.
6. Return to the employee view to explain how local demo state drives the tracker.

## Technical Talking Points

- Next.js App Router, React, TypeScript, Tailwind CSS.
- Leaflet and React Leaflet for map rendering.
- OpenStreetMap tiles.
- Zod for validation.
- LocalStorage-backed demo state.
- Unit tests for geo, time, and auth logic.

## Verified Results

- `npm run lint`: passed.
- `npm run typecheck`: passed.
- `npm test`: 3 files, 9 tests passed.
- `npm run build`: passed.
- Build completed with non-fatal webpack cache warnings.
- `npm audit --audit-level=moderate`: reported 13 vulnerabilities.

## Known Limits

- Demo authentication is local-only, not production auth.
- State is LocalStorage-backed, not database-backed.
- GPS quality depends on browser/device permissions.
- Demo data is fictional.
- Dependency maintenance is required before presenting this as production-ready.

