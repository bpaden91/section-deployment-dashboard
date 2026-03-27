# Section Deployment Dashboard

A self-serve, browser-only dashboard for viewing ProfAI and AI Academy deployment data. Customers paste their API key and everything runs client-side — no backend, no data stored on our systems.

## How it works

1. Customer opens the dashboard
2. Pastes their Section Reporting API key
3. Browser fetches data directly from the ProfAI API (`prof.ai`)
4. Key is saved in `localStorage` only — never sent to Section

## What it shows

- **ProfAI Program** — KPIs (users, onboarded, active, completed, use cases), completion funnel, onboarding timeline, skill completion grid
- **AI Academy** — course enrollment/completion, videos watched, course catalog
- **User Detail** — searchable/sortable table with per-user status
- Auto-detects single vs. multi-domain deployments and adjusts the UI accordingly

## Tech

- Single `index.html` — all HTML, CSS, JS in one file
- [Chart.js 4.5](https://www.chartjs.org/) via CDN
- Google Fonts (Montserrat + Inter)
- No build step, no dependencies, no server

## API Endpoints

All POST requests to `https://prof.ai`:

| Endpoint | Format | Returns |
|---|---|---|
| `/v1/reports/profai` | JSON | Users, skills, use cases, onboarding dates |
| `/v0/reports/courses` | CSV | Course catalog with enrollment/completion |
| `/v0/reports/employees` | CSV | Per-user video/course/badge counts |
| `/v0/reports/employee-course-map` | CSV | User-to-course mapping |

## Deploy

Host `index.html` anywhere that serves static files.

## License

MIT
