# Hands-On Lab: Claude for Excel

A three-part, instructor-ready lab that teaches the **top three Excel AI use cases** — formulas, data analysis, and visualization — using the **Claude for Excel add-in** from Anthropic.

These three use cases mirror the most-requested Copilot asks in Excel (natural-language formulas, trend/pattern analysis, and charts from raw data), so learners coming from a Copilot background will find the skills directly transferable — while seeing what Claude does differently: cell-level citations, highlighted edits with explanatory comments, and whole-workbook comprehension.

---

## Lab at a Glance

| Module | Use Case | Time | Skills |
|---|---|---|---|
| [Lab 1](lab-guide/Lab-1-Formulas.md) | **Formulas** — plain language → working formula, with explanation | 30 min | Prompting for formulas, cross-sheet lookups, auditing what Claude wrote |
| [Lab 2](lab-guide/Lab-2-Data-Analysis.md) | **Data Analysis** — find trends, patterns, and data-quality issues | 35 min | Data cleaning, pivot-style questions, drill-down prompting |
| [Lab 3](lab-guide/Lab-3-Visualization.md) | **Visualization** — charts and a mini-dashboard from raw data | 30 min | Chart prompting, iteration, dashboard layout |

**Total time:** ~95 minutes plus discussion. Each module stands alone if you need a shorter session.

---

## Prerequisites

1. **A paid Claude plan** — Pro, Max, Team, or Enterprise. The add-in is free to install, but signing in requires one of these plans. (On Team/Enterprise, an org owner may need to enable Office agents in organization settings.)
2. **Microsoft Excel** — Microsoft 365 desktop (Windows or Mac) or Excel on the web. *Not supported:* Excel 2016/2019 perpetual licenses, Excel on iPad, and Excel on Android.
3. **The Claude for Excel add-in** — install "Claude by Anthropic" from the Microsoft Marketplace / the Add-ins button on Excel's Home ribbon.
4. **The lab workbook** — download [`data/acme_sales_fy2026.xlsx`](data/acme_sales_fy2026.xlsx) from this repo.

> **Setup check (5 min):** Open the workbook, open the Claude sidebar from the ribbon, sign in, and ask: *"What's in this workbook?"* If Claude describes the Transactions and Product Costs sheets, you're ready.

---

## The Dataset

`acme_sales_fy2026.xlsx` — a fictional office-equipment distributor's FY2026 sales log.

- **Transactions** (241 rows): Order ID, Order Date, Region, Sales Rep, Channel, Product, Category, Units, Unit Price, Discount
- **Product Costs** (10 rows): Product, Category, Unit Cost, Launch Year

The data contains **intentional quality issues** (inconsistent region labels, missing values, a duplicate order). Don't fix them before class — Lab 2 depends on them.

---

## Repo Structure

```
Claude-Excel/
├── README.md
├── lab-guide/
│   ├── Lab-1-Formulas.md
│   ├── Lab-2-Data-Analysis.md
│   └── Lab-3-Visualization.md
├── data/
│   └── acme_sales_fy2026.xlsx
└── instructor/
    └── Instructor-Notes.md
```

---

## Good Habits to Model Throughout

- **Review every edit.** Claude highlights the cells it changes and leaves explanatory comments — teach learners to read them, not skip them.
- **Click the citations.** When Claude explains a calculation, its cell citations are clickable and jump to the referenced cells. This is the fastest way to verify an answer.
- **Trusted files only.** Spreadsheets from external sources can contain hidden instructions that manipulate an AI add-in. Use the add-in only with files you trust.
- **Human review before delivery.** AI-assisted workbooks still need a human check before they become client deliverables or audit-critical calculations.
- **Know the limits.** The add-in doesn't run or write VBA macros and doesn't support Excel data tables.

---

## For Instructors

See [`instructor/Instructor-Notes.md`](instructor/Instructor-Notes.md) for expected outcomes, common stumbling points, discussion questions, and a Copilot-vs-Claude talking-points table.

## Official Documentation

- Claude for Excel help article: https://support.claude.com/en/articles/12650343-use-claude-for-excel
- Product page: https://claude.com/claude-in-excel
- Plans and pricing: https://claude.com/pricing
