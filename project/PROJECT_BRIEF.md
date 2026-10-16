# MTL-XF-032 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Multimarket Online Retailer · **Sponsor:** Commercial Director · **Team:** 6–8 · **Duration:** 8 weeks · **Cycle:** quarterly customer and merchandising review

## Problem and commission

Sales totals hide cancellation activity, missing customer identities and concentrated product demand. Commercial managers need a reconciled view of gross sales, negative adjustments and customer value before assigning retention offers or changing the product range.

> Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation.

## Core scope

Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

Required source: online_retail_II.xlsx. Model grain: Invoice line with worksheet and original row number; do not assume Invoice + StockCode is unique.

C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Removing negative lines or missing customers before revenue accounting would overstate value and conceal coverage. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: Invoice line with worksheet and original row number; do not assume Invoice + StockCode is unique. |
| Retail Commercial Analyst | Approve cancellation versus adjustment classification, RFM rules and ten evidence-linked account/product investigation cards. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Descriptive/RFM core requires no predictive model. Use reference date 2011-12-01 and positive, non-cancellation invoices for RFM. Optional forecasting must use chronological rolling holdouts, never random line splitting. |
| BI / Decision Product Developer | Four views for the quarterly customer and merchandising review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Retail Finance Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Descriptive/RFM core requires no predictive model. Use reference date 2011-12-01 and positive, non-cancellation invoices for RFM. Optional forecasting must use chronological rolling holdouts, never random line splitting.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Baseline ranks country × product combinations by positive sales value; alternative ranks by absolute negative-adjustment value / positive sales value with zero denominators unavailable. Customer action compares RFM quintile segments; top ten opportunities include known-customer coverage.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Commercial Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Retail Commercial Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Commercial Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Retail Finance Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).
