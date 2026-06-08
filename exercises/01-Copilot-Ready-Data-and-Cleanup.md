# Exercise 1 — Copilot-Ready Data & Cleanup

- **Workflow:** Turn a messy real-world worksheet into something Copilot can actually analyze
- **Workbook:** **RCSA-Control-Matrix.xlsx** (the `Messy_RCSA` tab)
- **Estimated time:** 15 minutes
- **Difficulty:** Foundational — do this one first

---

## Objective

Excel Copilot's #1 failure mode is data shape, not prompting. This exercise builds the habit every other exercise depends on: diagnose what blocks Copilot (merged cells, stacked headers, subtotal rows), fix it, and run **Clean Data** — so "Copilot doesn't work on my file" never happens to you.

## Before you start

- [ ] **RCSA-Control-Matrix.xlsx** is in your **Copilot Audit Session** OneDrive folder (see pre-work).
- [ ] Open it in **Excel for the web**; confirm **AutoSave** is on.
- [ ] **Make a copy first** (File → Save a Copy) — Copilot edits directly. Work in the copy.

## What Copilot is doing here

Copilot reads tables and "supported ranges": one header row, unique non-blank headers, no merged cells, no subtotals mixed into data, no blank rows/columns. The `Messy_RCSA` tab violates several of these on purpose — like most inherited audit workpapers do.

---

## Steps

### Step 1 — See the failure first
Open the `Messy_RCSA` tab, open **Copilot** (Home ribbon), set the toggle to **Chat only**, and ask:

```text
How many controls are listed on this sheet, and how many are SOX relevant?
```

**Expected result:** a wrong, partial, or hedged answer. That's the lesson — note *why* before fixing anything.

### Step 2 — Diagnose with Copilot
```text
Look at the data on this sheet and tell me what would prevent Copilot from analyzing it reliably. Check for merged cells, multiple header rows, subtotal rows mixed into the data, blank rows or columns, and inconsistent formats. List each issue and where it is.
```

### Step 3 — Restructure (switch toggle to **Allow editing**)
```text
Restructure the data on this sheet into a proper Excel table: a single header row with unique names, no merged cells, no subtotal rows, and consistent formats in each column. Put the result on a new sheet called CleanData and do not change the original sheet.
```

**Expected result:** a new `CleanData` sheet with a real table. Spot-check it against the original — count the rows.

### Step 4 — Run Clean Data
Go to **Data tab → Clean Data**. Apply or ignore each suggestion (spacing, capitalization, number-stored-as-text). Notice you approve each change — Copilot proposes, you decide.

### Step 5 — Re-ask the question from Step 1
```text
How many controls are in the CleanData table, and how many are SOX relevant? Break the SOX-relevant ones down by Frequency.
```

**Expected result:** a correct, confident answer. Same Copilot, same data — different shape.

---

## Deliverable

A `CleanData` sheet that answers Step 5 correctly, plus your one-line note of which formatting problem caused the Step 1 failure.

## Verify before you rely on it

- [ ] Row count in `CleanData` matches the number of controls on the original sheet (count manually — subtotal rows should be gone, data rows shouldn't be).
- [ ] No control IDs were merged, dropped, or duplicated in the restructure.
- [ ] Clean Data changes you applied didn't alter meaning (e.g., account numbers keeping leading zeros).

## Key takeaways

- **Data shape is the #1 success factor** — fix it before judging Copilot's answers.
- Chat-only first, editing second: explore safely, then let Copilot touch cells.
- The original sheet stays untouched; transformations land on new sheets. Make that your standard.

---

*Next: Exercise 2 — GL-to-Subledger Reconciliation.*
