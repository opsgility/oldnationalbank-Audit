# Exercise 5 — RCSA & Findings Tracker Build

- **Workflow:** Structured audit documentation — RCSA worksheets, control-description quality, findings/action-plan tracking
- **Workbook:** **RCSA-Control-Matrix.xlsx** (the `CleanData` table from Exercise 1) + a new tracker built from scratch
- **Estimated time:** 20 minutes
- **Difficulty:** Core — template building

---

## Objective

Use Copilot to build and maintain the structured documentation that runs the audit shop: a standardized RCSA worksheet with validation dropdowns, a control-description quality check, and a findings tracker with live aging — repeatable templates instead of one-off spreadsheets.

## Before you start

- [ ] **RCSA-Control-Matrix.xlsx** (with your Exercise 1 `CleanData` sheet) open in Excel for the web, AutoSave on, **working on a copy**.

---

## Steps

### Step 1 — Standardize the RCSA structure (Allow editing)
```text
Create a Risk & Control Self-Assessment worksheet as a table on a new sheet called RCSA_Template with columns: Control ID, Process, Risk Description, Control Description, Control Owner, Frequency (Daily/Weekly/Monthly/Quarterly/Annual), Control Type (Preventive/Detective), SOX Relevant (Y/N), Evidence Location, Last Test Date, Test Result, and Notes. Add data validation dropdowns for Frequency, Control Type, SOX Relevant, and Test Result (Effective / Ineffective / Not Tested).
```

**Expected result:** a reusable template with working dropdowns. Test one dropdown manually.

### Step 2 — Migrate the existing controls
```text
Copy the controls from the CleanData table into the RCSA_Template table, mapping the matching columns and leaving the new columns blank. Tell me how many controls you moved and which template columns have no source data.
```

### Step 3 — Control-description quality check (Chat first, then apply)
```text
Review the Control Description column in the RCSA_Template table. For each entry, assess whether it states who performs the control, what they do, how often, and what evidence is produced. Add a column "Description Gaps" listing what's missing from each. Do not rewrite the descriptions — the control owners do that.
```

**Why the boundary:** Copilot can grade description completeness; rewriting a control description changes what the control *is* — that's the owner's call.

### Step 4 — Build the findings tracker
```text
On a new sheet called Findings_Tracker, build a findings tracker table with columns: Finding ID, Audit, Rating (High/Medium/Low), Finding Summary, Management Action Plan, Owner, Due Date, Status (Open/In Progress/Closed/Overdue), and Days to Due. Make Days to Due a formula based on today's date, and apply conditional formatting: Overdue rows red, items due within 30 days yellow. Add five realistic sample rows so I can see the formatting work.
```

### Step 5 — Committee roll-up
```text
From the findings tracker, create a summary for the audit committee package: open findings by rating, overdue items by owner, and average days open by rating. Present as a small table plus one chart. I will verify the counts before it goes in the deck.
```

### Step 6 — Version history walk-through (manual — your safety net)
File → **Version History**. Find the version from before Step 1 and preview it (don't restore). This is how you recover from any Copilot edit you didn't want — and why workpapers live in OneDrive/SharePoint.

---

## Deliverable

The workbook with `RCSA_Template` (dropdowns working, controls migrated, gaps column), `Findings_Tracker` (live aging + formatting), and the committee roll-up.

## Verify before you rely on it

- [ ] Control count in `RCSA_Template` equals `CleanData` — nothing dropped in migration.
- [ ] Dropdowns reject free-text entries (try typing an invalid value).
- [ ] Days to Due recalculates (check one row's math against today's date).
- [ ] Roll-up counts tie to the tracker rows.

## Key takeaways

- Copilot turns "the spreadsheet someone built years ago" into **standardized, validated templates** in minutes.
- Quality-checking descriptions ≠ rewriting them — keep ownership boundaries explicit in the prompt.
- Version history is the Excel safety net. Know where it is before you need it.

---

*That's the full set. Keep the prompt library handy — every prompt here generalizes to your real workpapers (on copies, inside the tenant, verified before reliance).*
