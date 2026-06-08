# Exercise 2 — GL-to-Subledger Reconciliation

- **Workflow:** Reconcile two system exports, flag and quantify every difference
- **Workbook:** **GL-Subledger-Reconciliation.xlsx** (tabs: `GL`, `Subledger`)
- **Estimated time:** 25 minutes
- **Difficulty:** Core — the headline use case

---

## Objective

Build a complete two-way reconciliation with Copilot: match columns, difference columns, status flags, exception highlighting, and a workpaper-ready summary — the work of an hour of XLOOKUP wrangling, in minutes, with you verifying every step.

## Before you start

- [ ] Workbook open in **Excel for the web**, AutoSave on, **working on a copy**.
- [ ] Both tabs are formatted as tables (they are — that's Exercise 1's lesson applied).
- [ ] Note the seeded issues: some IDs exist only in GL, some only in Subledger, and a handful of amounts differ.

## What Copilot is doing here

Copilot generates real XLOOKUP/IF formulas into new columns and explains them. **Key constraint:** Copilot only sees the *open workbook* — that's why both exports live as tabs in one file. (On desktop Excel, Copilot can import a table from another workbook via a refreshable Power Query connection; in the web you consolidate first. Your instructor may demo this.)

---

## Steps

### Step 1 — Record control totals (manual, 1 minute)
Before Copilot touches anything, note: GL row count and total Amount; Subledger row count and total Amount. (Select the columns — the status bar shows count and sum.) These are your tie-out anchors.

### Step 2 — Build the match column (**Allow editing**)
```text
On the GL sheet, add a column called "Subledger Amount" that uses XLOOKUP to find each Transaction ID in the Subledger table and return its Amount. If the ID is not found, return "NOT IN SUBLEDGER". Explain the formula you used.
```

**Expected result:** a new column plus a plain-English explanation. Read the explanation — that's your review of the formula.

### Step 3 — Difference and status columns
```text
Add two columns to the GL table: "Difference" = Amount minus Subledger Amount (blank if the item is missing from the subledger), and "Recon Status" with the value "Matched" if the difference is zero, "Amount Variance" if nonzero, and "Missing from Subledger" if not found.
```

### Step 4 — Reverse direction
```text
Now check the other direction: on the Subledger sheet, add a column "In GL?" that flags any Transaction ID that does not appear in the GL table. Then tell me how many items are missing from each side.
```

**Why this matters:** one-direction recons miss the items that exist only on the other side. Always reconcile both ways.

### Step 5 — Highlight and isolate exceptions
```text
In the GL table, highlight rows where Recon Status is not "Matched" in light red, and apply a filter to show only those rows. Then summarize the exceptions: count and total dollar amount by Recon Status.
```

### Step 6 — Explain an inherited formula (Chat only — bonus habit)
Click any formula cell Copilot created, or one of the pre-built formulas on the `Legacy` tab, and ask:
```text
Explain what the formula in this cell does, step by step, in plain language for an auditor reviewing this workbook. Note anything fragile about it, such as hard-coded ranges or values.
```

### Step 7 — Workpaper summary
```text
Write a short reconciliation summary I can paste into my workpaper: population counts and totals for both sources, number of matched items, number and dollar value of variances, number and value of one-sided items, and a list of the five largest differences with their Transaction IDs. I will verify each figure against the sheet.
```

---

## Deliverable

The reconciled workbook (match/difference/status columns both directions, exceptions highlighted) plus the verified summary paragraph.

## Verify before you rely on it

- [ ] Control totals from Step 1 still match — no rows dropped or duplicated.
- [ ] Pick **two** flagged variances and re-perform them by hand: GL amount minus Subledger amount.
- [ ] Pick one "Missing from Subledger" item and confirm by searching the Subledger tab for the ID.
- [ ] Summary figures (Step 7) tie to the filtered counts on the sheet.

## Key takeaways

- **One workbook, multiple tabs** — consolidate before reconciling; Copilot can't see your second file.
- Always reconcile **both directions**.
- "Explain the formula you used" turns every Copilot build into a reviewable one.
- Copilot found the differences; **you** decide which ones are reportable.

---

*Next: Exercise 3 — Population Analysis & Sampling Support.*
