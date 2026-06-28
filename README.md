# WC 2026 — Official² Ticket Partner

> *Real tickets. Real matches. Honest prices — which are, to be transparent, exactly double what you should be paying.*

A satirical, single-page HTML ticket marketplace for the 2026 FIFA World Cup. The entire premise is radical transparency: every ticket is sold at exactly **2× the official face value**, and the site makes absolutely no attempt to hide this.

---

## Features

**Matches tab** — Browse 6 available matches across all tournament stages (Group Stage through the Final). Each ticket card shows the match, venue, date, available seat tiers, official face value, and the fully-disclosed marked-up price. "Hot" matches are flagged accordingly.

**Standings tab** — Group stage standings for Group A and Group B, with illustrative data. Includes a helpful note reminding visitors that prices increase as teams advance — at double markup, every round.

**Pricing FAQ** — An accordion-style FAQ answering questions like *"Why are tickets double the price?"* and *"Is this legal?"* with admirably honest answers.

**Purchase modal** — Clicking any match opens a modal to select a seat tier, review the breakdown (face value vs. markup), and confirm the purchase. A confirmation screen shows a full receipt, including a line item for *"Our honest markup: +100%"*.

---

## Matches & Pricing

| Match | Stage | Venue | Date | Tiers (face value) |
|---|---|---|---|---|
| Brazil vs Argentina | Group Stage | MetLife Stadium | 14 Jun | $150 / $350 / $650 |
| France vs Spain | Group Stage | Rose Bowl, LA | 16 Jun | $120 / $300 / $900 |
| England vs Portugal | Round of 16 | SoFi Stadium, LA | 18 Jun | $200 / $500 |
| Germany vs Morocco | Quarter-Final | AT&T Stadium, Dallas | 20 Jun | $280 / $600 |
| Semi-Final 1 | Semi-Final | MetLife Stadium | 3 Jul | $350 / $850 |
| The Grand Final | World Cup Final | MetLife Stadium | 19 Jul | $500 / $900 / $2000 |

All prices shown in the UI are **2× the values above**.

---

## Tech Stack

- **Vanilla HTML, CSS, JavaScript** — no build step, no frameworks, no dependencies to install
- **Fonts** — [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue) (headings) and [Inter](https://fonts.google.com/specimen/Inter) (body), loaded via Google Fonts
- **Icons** — [Tabler Icons](https://tabler.io/icons) webfont via jsDelivr CDN

---

## Getting Started

No installation required. Just open the file in a browser:

```bash
open worldcup-tickets.html
```

Or serve it locally:

```bash
npx serve .
# then visit http://localhost:3000
```

---

## Project Structure

Everything lives in a single self-contained file:

```
worldcup-tickets.html
├── <head>          — Fonts, icons, all CSS styles
├── <header>        — Sticky nav with Matches / Standings / FAQ tabs
├── <section.hero>  — Hero banner with tagline and disclosure pills
├── <div.alert>     — Mandatory pricing disclosure banner
├── <main>
│   ├── #panel-matches    — Ticket grid (rendered via JS)
│   ├── #panel-standings  — Group A & B tables
│   └── #panel-faq        — Accordion FAQ
├── <footer>        — Disclaimer and "100% Authentic · 200% Price · 0% Shame"
├── .modal-overlay  — Purchase modal with tier selection & confirmation screen
└── <script>        — Match data, grid rendering, modal logic, tab switching
```

---

## Customisation

**Adding or editing matches** — Update the `matches` array in the `<script>` block. Each entry accepts:

```js
{
  teams: "Team A vs Team B",
  venue: "Stadium Name",
  date: "DD Mon",
  time: "HH:MM",
  stageLabel: "Group Stage",   // display label
  stageClass: "stage-group",   // CSS class (stage-group | stage-r16 | stage-qf | stage-sf | stage-final)
  hot: true,                   // shows the 🔥 Hot badge
  tiers: [
    { name: "General Admission", emoji: "🟢", real: 150 },
  ]
}
```

**Changing the markup multiplier** — Search for `* 2` in the script block. The multiplier is applied inline wherever prices are displayed and in the purchase confirmation.

---

## Disclaimer

This project is a satirical demo. It is not affiliated with FIFA, the 2026 World Cup, or any official ticketing partner. No real transactions are processed. The "double markup" is the joke.

*© 2026 Official² Ticket Partner · Not affiliated with FIFA · Prices are exactly double · Always*
