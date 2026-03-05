# Test Cases — CV Data Classification Tool

## TC-01: All Low Selections → Public

| Step | Action | Expected |
|------|--------|----------|
| 1 | Select Confidentiality = Low | Next button enabled |
| 2 | Select Integrity = Low, Availability = Low | Next button enabled |
| 3 | Select "No Personal Data" | View Results button enabled |
| 4 | View results | Overall = **Public**, all CIA cards show Low, GDPR = none, ISO controls = Information Classification only |

## TC-02: High Confidentiality + GDPR Personal Data → Confidential

| Step | Action | Expected |
|------|--------|----------|
| 1 | Select Confidentiality = High | — |
| 2 | Select Integrity = Medium, Availability = Low | — |
| 3 | Select "Personal Data" | — |
| 4 | View results | Overall = **Confidential**, ISO controls include: Information Classification, Information Labelling, Access Control Policy, Cryptography, GDPR Art. 32 TOMs |

## TC-03: Critical Across All + Special Category → Restricted

| Step | Action | Expected |
|------|--------|----------|
| 1 | Select Confidentiality = Critical | — |
| 2 | Select Integrity = Critical, Availability = Critical | — |
| 3 | Select "Special Category Data" + "Personal Data" | — |
| 4 | View results | Overall = **Restricted**, all ISO controls triggered (except DPIA which is excluded), GDPR flags show Art. 9 + Art. 4(1) |

## TC-04: Medium-High Confidentiality Maps to Confidential

| Step | Action | Expected |
|------|--------|----------|
| 1 | Select Confidentiality = Medium-High | — |
| 2 | Select Integrity = Low, Availability = Low | — |
| 3 | Select "No Personal Data" | — |
| 4 | View results | Overall = **Confidential** (medium-high maps to Confidential label) |

## TC-05: GDPR "None" Deselects All Other Categories

| Step | Action | Expected |
|------|--------|----------|
| 3 | Select "Personal Data" then "Financial Data" | Both highlighted |
| 3 | Select "No Personal Data" | All previous selections cleared, only "No Personal Data" active |

## TC-06: Selecting a GDPR Category Deselects "None"

| Step | Action | Expected |
|------|--------|----------|
| 3 | Select "No Personal Data" | Highlighted |
| 3 | Select "Children's Data" | "No Personal Data" deselected, "Children's Data" active |

## TC-07: Theme Toggle Persists Within Session

| Action | Expected |
|--------|----------|
| Load page in dark mode (default) | Dark background, white text, white logo |
| Click theme toggle | Light background, black text, black logo, sun icon → moon icon |
| Navigate through wizard steps | Theme persists across steps |

## TC-08: Navigation Flow

| Action | Expected |
|--------|----------|
| Load page | Step 1 active, Next button disabled |
| Try clicking Next without selection | Button remains disabled |
| Make selection, click Next | Advances to Step 2 |
| Click Back | Returns to Step 1 with selection preserved |
| Complete all steps, click "Start Over" | Returns to Step 1, all selections cleared |

## TC-09: Print / PDF Output

| Action | Expected |
|--------|----------|
| Navigate to Results, click Print | Print dialog opens, navigation buttons hidden, cards have borders, result page renders cleanly |

## TC-10: Responsive Layout

| Viewport | Expected |
|----------|----------|
| Desktop (>640px) | Dual-column layout for Integrity/Availability, 2-column GDPR grid |
| Mobile (<640px) | Single-column layout, stacked cards, readable text |
