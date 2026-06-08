# Exercise 4 — Pivots, Anomalies & Budget-vs-Actual

- **Workflow:** PivotTables and trend analysis by prompt; engagement hours variance tracking
- **Workbooks:** **Wire-Transfer-Population.xlsx** (Part 1) and **Audit-Hours-Budget-vs-Actual.xlsx** (Part 2)
- **Estimated time:** 20 minutes
- **Difficulty:** Core

---

## Objective

Two analyses every ONB audit group runs: pivot-driven pattern detection on a transaction population, and budget-vs-actual hours tracking across the audit plan — both built and explained by Copilot, both tied out by you.

## Before you start

- [ ] Both workbooks in OneDrive, AutoSave on, **working on copies**.
- [ ] Exercise 3 completed (Part 1 builds on the wire population).

---

## Part 1 — Pivot-driven pattern detection (`Wire-Transfer-Population.xlsx`)

### Step 1 — PivotTable by prompt (Allow editing)
```text
Create a PivotTable on a new sheet showing total Amount with Branch in rows and Month in columns, including row and column totals. Then tell me which branch-month combination is the largest outlier relative to that branch's average.
```

**Expected result:** a real, refreshable PivotTable plus a named outlier. Verify the outlier by reading the pivot yourself.

### Step 2 — Interrogate the pattern (Chat only)
```text
For the branch you identified as the outlier, what is driving the spike: more transactions, larger transactions, or both? Compare its transaction count and average amount in that month to its other months.
```

### Step 3 — Chart it
```text
Add a chart showing monthly total Amount by branch as lines, so the outlier month is visible. Put it next to the PivotTable.
```

## Part 2 — Budget vs. actual hours (`Audit-Hours-Budget-vs-Actual.xlsx`)

### Step 4 — Variance columns
```text
In the engagement hours table, add columns "Hours Variance" = Actual Hours minus Budget Hours and "Variance %" = variance divided by budget, formatted as a percentage. Highlight engagements more than 15% over budget in red and more than 15% under in yellow.
```

### Step 5 — Plan-level summary
```text
Summarize hours performance across the audit plan: total budget vs. actual, the three engagements with the largest overruns and their variance %, and any pattern by Audit Type or Quarter. Show a chart of variance % by engagement, sorted worst to best.
```

### Step 6 — The "why" stays human (Chat only)
```text
List the questions an audit manager should ask about the three largest overruns before drawing any conclusion about scoping or performance.
```

Note what Copilot does here: it frames questions, it doesn't answer them. The answers come from the engagement leads.

---

## Deliverable

The pivot + chart with the outlier identified (Part 1), and the variance-formatted hours workbook with the plan summary (Part 2).

## Verify before you rely on it

- [ ] Pivot grand total equals the table's total Amount (status-bar check).
- [ ] Re-perform one Variance % by hand: (Actual − Budget) ÷ Budget.
- [ ] The "three largest overruns" really are the three largest — sort and confirm.
- [ ] Conditional formatting thresholds fire on the right rows (find a 14% and a 16% engagement).

## Key takeaways

- Pivots and charts by prompt are fast — but **read the pivot yourself** before repeating its story.
- Variance mechanics are Copilot's job; variance *explanations* belong to the people who did the work.
- Everything Copilot built here is native Excel (real PivotTables, real formulas, real conditional formats) — it refreshes and recalculates like anything you'd build by hand.

---

*Next: Exercise 5 — RCSA & Findings Tracker Build.*
