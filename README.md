# Finara — Finance Dashboard

A clean, dark-themed personal finance dashboard built with vanilla HTML, CSS, and JavaScript — no framework dependencies, no build step required.

---

## Setup

Just open `index.html` in any modern browser. No installation needed.

```bash
# Or serve locally with:
npx serve .
# or
python -m http.server 8080
```

---

## Features

### Dashboard Overview
- **4 summary cards** — Total Balance, Total Income, Total Expenses, This Month's net
- **Balance Trend chart** (Line) — switchable between 1M / 3M / 6M views
- **Spending Breakdown chart** (Doughnut) — top 6 categories with percentages
- **Income vs Expenses chart** (Bar) — 6-month side-by-side comparison

### Transactions
- Full transaction list with **date, description, category, type, amount**
- **Search** by description or category
- **Filter** by category, type (income/expense)
- **Sort** by date or amount (asc/desc)
- **Pagination** — 10 records per page with smart pagination controls
- **Add transaction** (Admin only) — inline form with all fields
- **Delete transaction** (Admin only) — per-row delete button

### Role-Based UI
Switch roles via the dropdown in the sidebar:
- **Admin** — sees Add and Delete buttons, can mutate data
- **Viewer** — read-only, no action controls shown

No backend required. Role is simulated on the frontend for demonstration.

### Insights
- Highest spending category with percentage and progress bar
- Savings rate (%) with contextual advice
- Highest spend month across 6 months
- Income-to-Expense ratio
- Top categories breakdown
- Monthly comparison bar chart

### State Management
- All state held in plain JavaScript variables (`transactions`, `role`, `currentPage`, `currentSort`)
- Transactions persisted to `localStorage` — survive page reloads
- Filters, role, and pagination are in-memory runtime state

---

## Design Decisions

**Dark-first aesthetic** — financial dashboards benefit from low-light interfaces for extended use. Uses a near-black base (`#0c0c0e`) with layered surface cards.

**Typography** — DM Serif Display for headings (editorial feel), DM Sans for UI text, JetBrains Mono for numbers (monospace ensures amounts align cleanly in tables and cards).

**Color encoding** — each spending category has a fixed color used consistently across charts, legends, and table badges. Semantic green/red only used for income/expense type indicators.

**No framework** — keeps the project dependency-free. Chart.js loaded via CDN for all visualizations.

**Responsive** — sidebar collapses on mobile, replaced with a compact header. Cards and charts reflow using CSS grid `auto-fit`.

---

## File Structure

```
finance-dashboard/
└── index.html       # Single file — all HTML, CSS, and JS included
```

---

## Tech Stack

| Layer | Choice |
|---|---|
| Markup | HTML5 |
| Styles | Vanilla CSS with custom properties |
| Logic | Vanilla JavaScript (ES2020) |
| Charts | Chart.js 4.4 (CDN) |
| Fonts | Google Fonts — DM Serif Display, DM Sans, JetBrains Mono |
| Persistence | localStorage |

---

## Assumptions

- Currency is INR (₹). Trivial to change to any currency.
- "This month" in summary cards references the current calendar month.
- Roles are frontend-only simulations — no auth, no backend.
- Mock data covers Aug–Dec 2025 for realistic multi-month charting.

---

## Optional Enhancements Implemented

- Data persistence via `localStorage`
- Dark mode (default theme)
- Responsive layout for mobile
- Category color system consistent across all charts and UI elements

---

*Built for the Zorvyn Frontend Developer Internship assignment.*
