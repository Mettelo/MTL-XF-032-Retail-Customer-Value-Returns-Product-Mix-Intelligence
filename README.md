# MTL-XF-032 — Retail Customer Value Returns Product Mix Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 3–5 · **Duration:** 8 weeks

## The business problem

The commercial director must decide where retention and merchandising effort should go next quarter. A product may appear attractive on positive invoice value while generating substantial negative adjustments; a market may appear to have valuable customers while many sales lack customer IDs. The team needs one reconciled commercial ledger before it can compare account value, product concentration and cancellation exposure. Ignoring anonymous lines or deleting negative quantities would produce attractive but misleading totals.

**Simulated organisation:** Confidential Multimarket Online Retailer. **Accountable decision owner:** Commercial Director.

## Practical use case

During quarterly trading review, the director compares markets and products on positive value, signed adjustments and customer coverage, then reviews customer RFM groups and approves a ten-item retention/merchandising investigation register.

**Decision the project must enable:** Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation.

**Current approach:** Compare gross sales extracts and customer lists with inconsistent treatment of cancellations and missing IDs.

**Required future approach:** Use one signed-value bridge and explicit customer-coverage view before prioritising account and product actions.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Monthly trading reconciliation ledger | Month × Country totals of positive sales, negative adjustment value, other adjustments, signed transaction value, invoice counts and known-customer coverage; separate December 2011 exclusions. |
| D6 | Customer value and product concentration analysis | Customer RFM as of 2011-12-01, with recency/frequency/monetary fields and deterministic quintile ties; top-ten product concentration by country; missing-ID coverage report. |
| D7 | Ten commercial investigation cases | Up to ten country/product or customer-segment cases with positive value, adjustment ratio, coverage, baseline/alternative rank, action hypothesis, owner and evidence needed. |
| D8 | Quarterly trading dashboard | Trading bridge, customer RFM, product/market concentration and data-quality views with common cutoff and country filters. |
| D11 | Retention and merchandising decision pack | Three proposed interventions covering account retention, product investigation and market strategy; each has eligibility, accountable role, estimated affected value and pilot evaluation plan. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Monthly trading reconciliation ledger | Every original workbook line is retained/excluded/quarantined once; valid signed values reconcile exactly before rounding; +100 and −20 give 80; anonymous sales remain in trading totals. |
| SC2 | D6 — Customer value and product concentration analysis | No invoice on/after the cutoff affects RFM; frequency counts distinct eligible invoices; anonymous lines never receive invented customer IDs; no profit/margin claim without cost data. |
| SC3 | D7 — Ten commercial investigation cases | Both ranking approaches use the same declared population; zero positive value yields unavailable adjustment ratio; every case distinguishes cancellation/adjustment evidence from confirmed physical returns. |
| SC4 | D8 — Quarterly trading dashboard | Five full-cohort and five filtered measures reconcile; a reviewer traces one cancellation-heavy product and one high-value RFM segment to source lineage. |
| SC5 | D11 — Retention and merchandising decision pack | Five findings cite tested numbers; affected value is not forecast uplift; every proposal states missing cost/return-reason evidence and an owner/date for obtaining it. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [Online Retail II](https://archive.ics.uci.edu/dataset/502). **Required input:** online_retail_II.xlsx. **Expected source population:** 1,067,371 source invoice lines across two worksheets.

Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

**Download:** https://archive.ics.uci.edu/static/public/502/online+retail+ii.zip

C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Descriptive/RFM core requires no predictive model. Use reference date 2011-12-01 and positive, non-cancellation invoices for RFM. Optional forecasting must use chronological rolling holdouts, never random line splitting.

Baseline ranks country × product combinations by positive sales value; alternative ranks by absolute negative-adjustment value / positive sales value with zero denominators unavailable. Customer action compares RFM quintile segments; top ten opportunities include known-customer coverage.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Retail Commercial Analyst: Approve cancellation versus adjustment classification, RFM rules and ten evidence-linked account/product investigation cards.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Retail Finance Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Commercial Director, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Retail Commercial Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Commercial Director reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Retail Finance Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
