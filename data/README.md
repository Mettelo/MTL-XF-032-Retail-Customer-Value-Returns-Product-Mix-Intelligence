# MTL-XF-032 — Data acquisition and engineering

## Approved S1

[Online Retail II](https://archive.ics.uci.edu/dataset/502); required files: **online_retail_II.xlsx**. Expected source population: 1,067,371 source invoice lines across two worksheets.

Exact official download:

https://archive.ics.uci.edu/static/public/502/online+retail+ii.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

**Grain:** Invoice line with worksheet and original row number; do not assume Invoice + StockCode is unique.

**Required fields:** Invoice/InvoiceNo, StockCode, Description, Quantity, InvoiceDate, Price/UnitPrice, Customer ID/CustomerID, Country; map actual worksheet headers explicitly.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Read both workbook worksheets with explicit header mapping (Invoice, Price, Customer ID). Preserve sheet and original row lineage; source-line identity is not Invoice×StockCode.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Descriptive/RFM core requires no predictive model. Use reference date 2011-12-01 and positive, non-cancellation invoices for RFM. Optional forecasting must use chronological rolling holdouts, never random line splitting.

## Interpretation and quality

C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
