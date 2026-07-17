# Instructor Notes

Audience assumption: business users comfortable with Excel basics, mixed AI experience, many coming from Copilot. Total runtime ~95 min hands-on + 15–20 min discussion.

## Before Class

- Verify every learner has a **paid Claude plan** (Pro/Max/Team/Enterprise). This is the #1 setup blocker. On Team/Enterprise, confirm the org owner has enabled Office agents in organization settings.
- Confirm supported Excel versions: Microsoft 365 desktop (Win/Mac) or web. Excel 2016/2019 perpetual, iPad, and Android will not work — have web Excel as the fallback.
- Have learners run the 5-minute setup check in the README *before* the session.
- Distribute a fresh copy of `acme_sales_fy2026.xlsx` — the planted data issues in Lab 2 must be intact.
- Optional: show learners the **Instructions** field in the add-in sidebar (persistent per-app preferences, e.g., "always format currency as $#,##0"). Nice differentiator demo.

## Planted Data Issues (Lab 2 answer key)

| Issue | Location | Expected fix |
|---|---|---|
| Region typed as "N.E." | 2 rows (originally rows 18 and 64 of the generated data; sorted by date, so positions vary — Claude will find them) | Standardize to "Northeast" |
| Missing Units | 1 row | Discuss: impute vs. exclude vs. chase the source. Best answer: flag and verify with the source system |
| Missing Discount | 1 row | Fill with 0% (reasonable default) — but note the assumption |
| Duplicate order | 2 identical rows, same Order ID | Flag, confirm, then remove one |

## Expected Outcomes by Exercise

- **1.1** A Net Revenue column, e.g. `=H2*I2*(1-J2)`, currency-formatted, with highlighted cells and an explanatory comment.
- **1.2** A lookup (commonly XLOOKUP or INDEX/MATCH) against Product Costs, plus a Gross Profit column. The "why this lookup" discussion lands the point that learners can interrogate design choices.
- **1.3** Nested IF or IFS for Deal Size; Commission combines a rate choice with Net Revenue. Verification of one Large+Field row is the graded moment.
- **1.4** Claude should identify the unquoted `Northeast` criterion and correct to `"Northeast"`. If a learner's Claude also questions column choices, celebrate it — that's the audit instinct you're teaching.
- **2.2–2.4** Answers vary with the fixes made in 2.1 — this is a feature: pairs who made different cleaning decisions get slightly different numbers, which sets up a great "data decisions are analysis decisions" discussion.
- **3.4** A one-screen dashboard with live links. The checkpoint (edit a transaction, watch the dashboard move) proves nothing was pasted as static values.

## Common Stumbling Points

1. **Sidebar won't sign in** → wrong Microsoft profile or no paid Claude plan. Check plan first.
2. **Claude edited more than expected** → teach the habit: read the highlighted cells and comments after every response; undo is available.
3. **Learners paste numbers from the chat into cells** → stop this early. The point is live formulas and add-in edits, not transcription.
4. **Vague prompts, vague results** → run a live contrast: "make a chart" vs. the audience+message prompt in 3.1.
5. **Overtrust** → keep repeating the loop: *prompt → read comment → click citation → spot-check one row.*

## Safety and Governance Talking Points

- **Trusted spreadsheets only.** Files from outside can carry hidden instructions (prompt injection) that manipulate an AI add-in into leaking or modifying data. Make this visceral: an "innocent" vendor file could contain invisible text.
- **Not for unreviewed final deliverables** or audit-critical calculations without verification.
- **No VBA/macros, no data tables** — set expectations before someone burns 10 minutes trying.
- Enterprise buyers will ask: activity is not included in Enterprise audit logs or the Compliance API, and the add-in does not inherit custom data-retention settings — route them to their admin and current official docs.

## Copilot → Claude Transfer Table

For cohorts trained on your "Top 3 Copilot Asks" framework:

| Copilot ask (Excel) | This lab | What to emphasize with Claude |
|---|---|---|
| Plain language → formula | Lab 1 | Explanatory comments on every edit + clickable cell citations for auditing |
| Trend & pattern identification | Lab 2 | Whole-workbook comprehension across tabs; conversational pivot creation/editing |
| Charts & dashboards from raw data | Lab 3 | Iterative chart refinement in dialogue; native chart/conditional-formatting operations |

Frame it as *transferable skill, different verification affordances* — the prompting skill carries over; Claude's citations and highlighted edits change how you verify.

## Discussion Questions

1. Which verification habit (comments, citations, spot-checks) will you actually keep under deadline pressure?
2. Where in your real workbooks would you *not* let an AI make edits? Why?
3. What did you have to specify precisely to get a good result — and what did the model infer well on its own?

## Sources to Keep Current

Product capabilities change quickly — re-verify before each delivery:

- https://support.claude.com/en/articles/12650343-use-claude-for-excel
- https://claude.com/claude-in-excel
