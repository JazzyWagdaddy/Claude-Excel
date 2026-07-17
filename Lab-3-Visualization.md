# Lab 3 — Visualization: Charts and a Mini-Dashboard

**Use case #3: from raw rows to charts your stakeholders actually read.**
⏱ ~30 minutes | Workbook: `acme_sales_fy2026.xlsx` (ideally continued from Labs 1–2)

## Learning Objectives

1. Generate charts by describing the message, not the chart settings.
2. Iterate on a chart conversationally (type, labels, colors, emphasis).
3. Assemble multiple charts into a one-screen dashboard.
4. Choose chart types deliberately — and ask Claude to justify its choice.

---

## Exercise 3.1 — First Chart, Message First (6 min)

1. Prompt:

   > Create a chart that shows how quarterly net revenue trended across FY2026. The audience is executives — keep it clean, title it clearly, and label the axis in dollars.

2. **Observe:** you specified *audience and message*; Claude picked type, ranges, and formatting.
3. Ask: *"Why did you choose this chart type? What would be a worse choice and why?"*

## Exercise 3.2 — Iterate Conversationally (7 min)

Refine the chart without touching a single Excel menu:

1. > Change it to a column chart and add data labels showing revenue in $K.
2. > Highlight the strongest quarter in a distinct color and add a one-line takeaway as the chart subtitle.
3. **Discussion:** Compare this loop to hunting through Chart Design ribbons. What's faster? What still deserves manual control?

## Exercise 3.3 — Comparison and Composition Charts (7 min)

1. > Create a chart comparing net revenue by region, sorted highest to lowest.
2. > Now show category mix as a share of total revenue. Pick the best chart type for part-to-whole and explain your pick.
3. **Teachable moment:** if Claude offers a pie chart with many slices, push back — *"Would a bar chart communicate this more accurately?"* Learners should see that they can (and should) challenge AI design choices.

## Exercise 3.4 — Build the Mini-Dashboard (8 min)

1. Prompt:

   > Create a new sheet called "Dashboard." Arrange: (1) quarterly revenue trend, (2) revenue by region, (3) category mix, and (4) a KPI block at the top with total revenue, order count, and average deal size. Make it fit one screen, consistent fonts and colors, dashboard-style.

2. Iterate once:

   > Apply a consistent blue color scheme and add a "Data through June 2026" note in the footer area.

**✋ Checkpoint:** Change one transaction's Units value. Do the KPI numbers and charts update? (They should — everything is live.)

## Exercise 3.5 — Stretch: Conditional Formatting as Visualization (2 min)

> On the pivot table from Lab 2, add a color scale so the strongest region–category cells stand out, and add data bars to the grand total column.

---

## Key Takeaways

- Prompt with **audience + message**; let the tool handle mechanics.
- Charts are drafts — **iterate in conversation** the way you'd iterate with a designer.
- You are the design authority: challenge chart choices, demand justification.
- A dashboard is one prompt plus a few refinements — but the *thinking* about what belongs on it is still yours.

---

## Wrap-Up for the Full Lab

Ask each learner to complete this sentence three ways: *"On Monday, the first thing I'll hand to Claude in Excel is ___."* Collect them — they're your adoption roadmap.
