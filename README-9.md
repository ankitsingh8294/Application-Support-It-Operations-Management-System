# SupportOps Management System

**Application Support & IT Operations Management System**

A single-page, front-end dashboard that demonstrates how a technical/
application support team manages users, application access requests,
support tickets, and plant/site information for a company that deploys
software solutions at industrial plants.

> **Disclaimer:** This project uses fictional/demo data and is created for
> educational and portfolio purposes. It is not connected to any real
> company, client, or employee data.

---

## Overview

Application support teams at manufacturing and industrial companies handle
a constant stream of day-to-day issues — login problems, hardware faults,
network errors, printer issues, and questions about reports — across
multiple plants and users. This project simulates a simple, practical
system a support/operations team could use to track that work in one
place.

It was built as a portfolio project to demonstrate the kind of day-to-day
work handled in **Application Support, Technical Support, Implementation/
Deployment Support, MIS, and IT Operations** roles.

---

## Purpose

- Show a working example of how support tickets are logged, assigned, and
  resolved.
- Show how user accounts and application access requests are managed and
  approved.
- Show how plant/site information ties into support activity.
- Provide simple, understandable reports that an operations team would
  actually look at.

---

## Key Features

- Single dashboard with live KPI cards and charts
- User & ID management — add, edit, search, filter, activate/deactivate
- Application access request workflow (Pending → Approved / Rejected)
- Support ticket workflow (Open → In Progress → Pending → Resolved → Closed)
- Plant/site overview with live active-user and open-ticket counts
- Seven operational reports with supporting charts
- Realistic, internally consistent fictional demo data, generated
  automatically in the browser every time the page loads
- No build step, no backend, no install — a single HTML file

---

## Modules

| Module | Description |
|---|---|
| **Dashboard** | Total/active users, ticket counts by status, average resolution time, and charts for priority, category, and plant. |
| **User & ID Management** | Manage employee application accounts — add, edit, search, filter, activate/deactivate. |
| **Application Access Requests** | Raise and review requests for application access, with an approve/reject workflow. |
| **Support Tickets** | Log tickets, assign to technicians, update status, and record resolutions. |
| **Plant / Site Management** | List of fictional plant/site locations with live active-user and open-ticket counts. |
| **Reporting** | Tickets by status/priority/category/plant, technician workload, access requests by status, and monthly ticket trend. |

---

## Technology Used

- **HTML5** — page structure
- **CSS3** — layout and styling (no framework, written from scratch)
- **Vanilla JavaScript** — all app logic, data generation, and DOM rendering
- **[Chart.js](https://www.chartjs.org/)** — charts, loaded from a public CDN

No backend, database, build tools, or frameworks are used — the entire
application is a single static file that runs in the browser.

---

## Project Structure

```
supportops-management-system/
│
├── index.html    # Complete application: markup, styles, and script in one file
├── README.md      # Project documentation (this file)
└── LICENSE         # MIT license
```

---

## How It Works

1. When `index.html` is opened, a script inside the page generates
   fictional demo data in memory: 30 users, 50 support tickets, 20 access
   requests, 8 plants, and 12 support technicians. A seeded random
   generator keeps the data consistent across page loads.
2. The sidebar controls which section is visible; switching sections just
   shows/hides the relevant `<section>` — there is no page reload.
3. Tables support live search and filtering, done entirely in JavaScript
   against the in-memory data.
4. Adding or updating a record (a user, a ticket, an access request) opens
   a small modal form. On submit, the in-memory data array is updated and
   the table/dashboard re-renders immediately.
5. Charts are drawn with Chart.js and are redrawn whenever the underlying
   data changes.
6. **Data is not saved anywhere.** Because this is a front-end-only demo
   with no backend or database, refreshing the page resets all data back
   to the original fictional dataset. This is expected behavior for a
   static portfolio demo, not a bug.

### Basic concepts used

- **Support ticket** — a record of a reported problem that needs to be
  tracked from creation to resolution.
- **Ticket priority** — helps the support team decide which issues to work
  on first (Critical/High issues before Low priority ones).
- **Ticket status** — shows where an issue currently stands in its
  lifecycle (Open → In Progress → Pending → Resolved → Closed).
- **User ID / access request** — every employee needs an application
  account with a defined role; access requests are how new accounts or
  role changes get reviewed and approved.
- **Plant/site tracking** — since the company supports multiple physical
  locations, knowing which plant a ticket or user belongs to helps route
  and prioritize support work.
- **DOM rendering** — JavaScript builds HTML strings from the data arrays
  and injects them into the page instead of hardcoding tables by hand.

---

## Installation

No installation is required. This is a static site with no dependencies
to install and no build step.

1. Clone or download this repository.
2. Open `index.html` directly in any modern browser (Chrome, Edge,
   Firefox, Safari).

Optionally, to run it through a local web server instead of opening the
file directly (useful for testing, and avoids any browser file:// quirks):

```bash
# Python 3
python -m http.server 8000

# or Node.js
npx serve .
```

Then visit `http://localhost:8000` in your browser.

---

## Deploying it for free

Since it's a single static file, you can host it for free in a couple of
clicks:

- **GitHub Pages** — in the repository settings, enable Pages and point it
  at the `main` branch (root folder). Your site will be live at
  `https://<your-username>.github.io/<repo-name>/`.
- **Netlify / Vercel** — drag and drop the project folder onto
  [Netlify Drop](https://app.netlify.com/drop) or import the repo into
  Vercel for an instant live link.

---

## Future Improvements

- Persist data with `localStorage` or a small backend/database so changes
  survive a page refresh
- Add basic login/authentication for different application roles
- Add ticket SLA tracking with breach alerts
- Add export-to-CSV option for reports and tables
- Add pagination for large tables
- Add form validation feedback inline instead of toast messages only

---

## Disclaimer

This project uses **fictional/demo data** and is created for
**educational and portfolio purposes** only. All employee names, plant/site
names, tickets, and access requests are randomly generated and do not
represent real people, companies, or events.
