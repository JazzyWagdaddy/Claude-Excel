# Lab 1 — Formulas from Plain Language

**Use case #1: describe what you need; get a working, explained formula.**
⏱ ~30 minutes | Workbook: `acme_sales_fy2026.xlsx`

## Learning Objectives

By the end of this lab, you can:

1. Ask Claude to write formulas from a plain-language description.
2. Have Claude build cross-sheet lookups without memorizing lookup syntax.
3. Audit a formula Claude wrote — using its comments and clickable cell citations.
4. Ask Claude to explain and fix a broken formula.

---

## Exercise 1.1 — Your First Generated Formula (5 min)

The Transactions sheet has Units, Unit Price, and Discount — but no revenue column.

1. Open the Claude sidebar in Excel.
2. Prompt:
```
   Add a "Net Revenue" column to the Transactions sheet that calculates Units × Unit Price × (1 − Discount).
   Format it as currency.
```

3. **Observe:** Claude highlights the cells it filled and adds a comment explaining the formula.
4. Click into any cell in the new column and read the formula in the formula bar. Can you map each piece back to your request?

**✋ Checkpoint:** Row 2 of Net Revenue should equal Units × Unit Price × (1 − Discount) for that row. Spot-check one row with a calculator.

## Exercise 1.2 — Cross-Sheet Lookup (8 min)

Profit requires unit costs — which live on the **Product Costs** sheet.

1. Prompt:
```
   Add a "Unit Cost" column to Transactions that looks up each product's cost from the Product Costs sheet.
   Then add a "Gross Profit" column: (Unit Price × (1 − Discount) − Unit Cost) × Units.
```

2. **Observe:** Ask Claude *"Explain the lookup formula you just wrote."* Its explanation includes clickable citations — click one and watch Excel jump to the referenced cell.
3. Discussion: which lookup approach did Claude choose (XLOOKUP, INDEX/MATCH, VLOOKUP)? Ask it *why* it chose that one.

## Exercise 1.3 — Conditional Logic Without the Syntax Pain (7 min)

1. Prompt:
```
   Add a "Deal Size" column that labels each order: "Large" if Net Revenue is $1,000 or more,
   "Medium" if $250–$999, otherwise "Small."
```

2. Then push further:
```
   Now add a "Commission" column: reps earn 3% of Net Revenue,
   but 5% on Large deals in the Field channel.
```

3. **Audit it:** Ask Claude — *"Walk me through the Commission formula for row 10, citing the cells you used."*

**✋ Checkpoint:** Find one Large + Field row and verify its commission is 5% of Net Revenue.

## Exercise 1.4 — Debug a Broken Formula (7 min)

1. In an empty cell, type this deliberately broken formula (missing quote, wrong range):

   ```
   =SUMIF(Transactions!C:C, Northeast, Transactions!H:H)
   ```

2. Prompt:
```
   There's an error in the formula I just typed. Find it, explain what's wrong, and fix it so it totals Units for the Northeast region.
```

3. **Observe:** Claude identifies the unquoted criterion, explains the failure, and corrects it — this is the everyday "why is my formula broken?" workflow.

## Exercise 1.5 — Stretch: One-Prompt Summary Block (3 min)

> On a new sheet called "Quick Stats," build a small summary: total Net Revenue, average discount, order count, and Net Revenue by Category — all as live formulas, not pasted values.

Verify the numbers change if you edit a transaction row.

---

## Key Takeaways

- Describe the **business rule**, not the syntax — Claude translates.
- Always **read the comment, click the citations, spot-check one row.** Trust, then verify.
- Claude can explain and repair formulas it didn't write — great for inherited workbooks.

**Next:** [Lab 2 — Data Analysis](Lab-2-Data-Analysis.md)
