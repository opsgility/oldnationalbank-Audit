# Exercise 3 — Population Analysis & Sampling Support

- **Workflow:** Profile a transaction population, stratify it, and scan for anomalies before selecting a sample
- **Workbook:** **Wire-Transfer-Population.xlsx** (tab: `Wires`, ~300 rows)
- **Estimated time:** 20 minutes
- **Difficulty:** Core

---

## Objective

Use Copilot to do the population legwork that precedes sampling: counts, totals, distributions, stratification bands, and a first-pass anomaly scan — while keeping the actual sampling decision exactly where it belongs: with the auditor.

## Before you start

- [ ] Workbook open in **Excel for the web**, AutoSave on, **working on a copy**.
- [ ] The population contains seeded anomalies (find them honestly — don't peek at the answer tab until done).

## What Copilot is doing here

In **Chat-only** mode Copilot answers questions about the data (counts, outliers, patterns). In **Allow editing** mode it adds the stratification column and highlights. The boundary you're practicing: Copilot **informs** sampling; it never **performs** it. Method, size, and selection are your documented judgment.

---

## Steps

### Step 1 — Population profile (Chat only)
```text
Act as an audit analyst. Profile the transaction population in this table: total count, total dollar value, min/max/average/median of Amount, date range of Posting Date, and a breakdown of count and value by Branch and by Transaction Type. Present as labeled tables.
```

**Expected result:** the workpaper "population" section, drafted. Verify count/total against the status bar before moving on.

### Step 2 — Stratification bands (Allow editing)
```text
Add a column "Amount Band" that classifies each transaction: Under $5,000; $5,000–$24,999; $25,000–$99,999; $100,000 and over. Then give me count and total value per band so I can document my stratification.
```

### Step 3 — Anomaly scan (Chat only)
```text
Scan this population for patterns an auditor would flag for follow-up: round-dollar amounts, amounts just under $10,000, transactions posted on weekends, duplicate Amount + Beneficiary combinations, and any branch whose volume is an outlier versus the others. List what you find with the supporting rows, and note that these are leads for testing, not conclusions.
```

**Expected result:** several seeded anomalies surface. For each, ask yourself: would I follow up? Why? That decision is the audit.

### Step 4 — Make the leads visible (Allow editing)
```text
Highlight in orange all rows with amounts between $9,000 and $9,999, and in yellow all rows posted on a Saturday or Sunday. Add a filtered view showing only highlighted rows.
```

### Step 5 — Document the population
```text
Draft a "Population and Sampling Considerations" paragraph for my workpaper describing this population: source, period covered, count, total value, composition by band, and notable characteristics. Leave the sampling method and sample size blank as [METHOD] and [N] — those are my decisions.
```

Fill in `[METHOD]` and `[N]` yourself, with one sentence of rationale. **Copilot must not write that sentence.**

---

## Deliverable

The stratified, highlighted population plus your completed Population and Sampling Considerations paragraph — with the method/size rationale in your own words.

## Verify before you rely on it

- [ ] Step 1 count and total tie to the status-bar figures.
- [ ] Band counts in Step 2 sum to the total population count.
- [ ] Spot-check two "anomalies" — is that row *actually* a weekend posting / just-under-threshold amount?
- [ ] Check the seeded-answers tab (instructor will unhide) — did the scan miss anything? What would you ask differently?

## Key takeaways

- Copilot compresses hours of population profiling into minutes — and drafts the documentation.
- **Leads, not conclusions:** every flagged item is a question, not a finding.
- The sampling method, size, and selection rationale are auditor judgment — keep them out of the prompt.

---

*Next: Exercise 4 — Pivots, Anomalies & Budget-vs-Actual.*
