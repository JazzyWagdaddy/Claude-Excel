# Lab 2 — Data Analysis: Trends, Patterns, and Dirty Data

**Use case #2: turn a raw transaction log into insight — and catch the data problems first.**
⏱ ~35 minutes | Workbook: `acme_sales_fy2026.xlsx` (continue from Lab 1, or start fresh)

## Learning Objectives

1. Use Claude to audit data quality before analyzing.
2. Ask analytical questions in plain language and get cited, verifiable answers.
3. Build pivot-table summaries by describing the view you want.
4. Practice drill-down prompting: broad question → follow-up → root cause.

---

## Exercise 2.1 — Data-Quality Audit First (8 min)

This dataset ships with planted problems. Find them before they poison your analysis.

1. Prompt:

   > Before I analyze this data, audit the Transactions sheet for data-quality issues: inconsistent labels, missing values, duplicates, or anything suspicious. List what you find with the cell locations.

2. **Expected finds:** inconsistent region labels ("N.E." vs "Northeast"), at least one missing Units value, a missing Discount, and a duplicated order row.
3. Fix them conversationally:

   > Standardize the region labels to "Northeast", fill the missing discount with 0%, flag—but don't delete—the duplicate row by highlighting it yellow, and tell me what you'd recommend for the missing Units value.

4. **Discussion:** Why did we ask Claude to *flag* rather than delete the duplicate? (Answer: destructive changes deserve a human decision.)

## Exercise 2.2 — Plain-Language Analysis (8 min)

1. Ask a broad question:

   > Which region generated the most net revenue this fiscal year, and how big is the gap to the weakest region?

2. Then a trend question:

   > Is revenue trending up or down across the year? Summarize by quarter and tell me the story in two sentences.

3. **Verify:** Claude's answer should cite cells/ranges. Click through at least one citation chain to confirm the numbers are grounded in the sheet, not invented.

## Exercise 2.3 — Pivot Thinking Without Pivot Clicking (8 min)

1. Prompt:

   > Create a pivot table on a new sheet showing Net Revenue by Region (rows) and Category (columns), with a grand total.

2. Iterate on it:

   > Add Channel as a filter, and sort regions by total revenue, highest first.

3. **Observe:** the add-in can create and edit pivot tables, sort, filter, and apply conditional formatting directly — you describe the view; it builds the mechanics.

## Exercise 2.4 — Drill-Down Prompting (8 min)

Practice the analyst's loop — each answer seeds the next question:

1. > Which sales rep has the highest average discount, and is their discounting buying them more revenue than their peers?
2. > For that rep, break down their discounts by product category. Where are they discounting most aggressively?
3. > Play devil's advocate: give me an alternative explanation for this pattern besides "the rep discounts too much."

**Discussion:** Step 3 is the habit that separates AI-assisted analysis from AI-dictated analysis. The model proposes; the analyst disposes.

## Exercise 2.5 — Stretch: Executive Summary (3 min)

> Write a 5-bullet executive summary of FY2026 sales performance on a new sheet called "Summary," covering revenue, best/worst region, category mix, discount behavior, and one risk you see in the data. Note any caveats from the data-quality issues we found.

---

## Key Takeaways

- **Audit before analysis** — one prompt catches issues that would silently skew every downstream number.
- Cited answers are **checkable answers**; click through before you repeat a number in a meeting.
- Pivot tables become a description problem, not a drag-and-drop problem.
- Drill down, and ask for counter-explanations.

**Next:** [Lab 3 — Visualization](Lab-3-Visualization.md)
