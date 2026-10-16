# MTL-XF-032 — Deliverables and metric contracts

**Decision:** Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for quarterly customer and merchandising review.

**Pass evidence:** All eight link source support, D/AC/DT and Commercial Director approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: Invoice line with worksheet and original row number; do not assume Invoice + StockCode is unique. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address Removing negative lines or missing customers before revenue accounting would overstate value and conceal coverage.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — Monthly trading reconciliation ledger

**Due:** Week 4 · **Owner:** Retail Commercial Analyst · **Business reviewer:** Commercial Director · **Independent reviewer:** Retail Finance Assurance Analyst

**Required artefact:** data/curated/monthly-trading-reconciliation-ledger.csv and docs/05-kpi-catalogue/monthly-trading-reconciliation-ledger.md.

Month × Country totals of positive sales, negative adjustment value, other adjustments, signed transaction value, invoice counts and known-customer coverage; separate December 2011 exclusions.

**Mandatory pass condition (SC1):** Every original workbook line is retained/excluded/quarantined once; valid signed values reconcile exactly before rounding; +100 and −20 give 80; anonymous sales remain in trading totals.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D6 — Customer value and product concentration analysis

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Business reviewer:** Commercial Director · **Independent reviewer:** Retail Finance Assurance Analyst

**Required artefact:** docs/06-analysis/customer-value-and-product-concentration-analysis.md plus machine-readable evaluation_results.csv.

Customer RFM as of 2011-12-01, with recency/frequency/monetary fields and deterministic quintile ties; top-ten product concentration by country; missing-ID coverage report.

**Mandatory pass condition (SC2):** No invoice on/after the cutoff affects RFM; frequency counts distinct eligible invoices; anonymous lines never receive invented customer IDs; no profit/margin claim without cost data.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D7 — Ten commercial investigation cases

**Due:** Week 6 · **Owner:** Retail Commercial Analyst · **Business reviewer:** Commercial Director · **Independent reviewer:** Retail Finance Assurance Analyst

**Required artefact:** docs/07-decision-framework/ten-commercial-investigation-cases.csv plus policy.md.

Up to ten country/product or customer-segment cases with positive value, adjustment ratio, coverage, baseline/alternative rank, action hypothesis, owner and evidence needed.

**Mandatory pass condition (SC3):** Both ranking approaches use the same declared population; zero positive value yields unavailable adjustment ratio; every case distinguishes cancellation/adjustment evidence from confirmed physical returns.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D8 — Quarterly trading dashboard

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Business reviewer:** Commercial Director · **Independent reviewer:** Retail Finance Assurance Analyst

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

Trading bridge, customer RFM, product/market concentration and data-quality views with common cutoff and country filters.

**Mandatory pass condition (SC4):** Five full-cohort and five filtered measures reconcile; a reviewer traces one cancellation-heavy product and one high-value RFM segment to source lineage.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Retail Finance Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Retention and merchandising decision pack

**Due:** Week 8 · **Owner:** Business Analyst / Delivery Lead with domain specialist · **Business reviewer:** Commercial Director · **Independent reviewer:** Retail Finance Assurance Analyst

**Required artefact:** deliverables/retention-and-merchandising-decision-pack.pdf plus editable slides and supporting cards/runbook.

Three proposed interventions covering account retention, product investigation and market strategy; each has eligibility, accountable role, estimated affected value and pilot evaluation plan.

**Mandatory pass condition (SC5):** Five findings cite tested numbers; affected value is not forecast uplift; every proposal states missing cost/return-reason evidence and an owner/date for obtaining it.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Positive sales value | Σ Quantity×UnitPrice for Quantity>0, UnitPrice>0 and non-C invoices, GBP; separate zero-price and non-product exceptions. | month × country × StockCode |
| K2 | Negative adjustment value | Σ Quantity×UnitPrice for negative-valued lines, GBP, displayed signed; do not assert physical returns. | month × country |
| K3 | Signed transaction value | Σ Quantity×UnitPrice across valid numeric lines; reconcile to positive + negative + separately classified adjustments. | core period |
| K4 | Cancellation invoice share | distinct C-prefixed invoice IDs / distinct nonmissing invoice IDs; document country/sheet collisions. | month |
| K5 | Known-customer value coverage | positive sales with nonmissing CustomerID / all positive sales. | country |
| K6 | RFM | recency=days since last eligible invoice to 2011-12-01; frequency=distinct eligible invoices; monetary=positive sales GBP; document quintile ties. | known customer |
| K7 | Product concentration | positive sales of top ten StockCodes / total positive sales; include ranking tie rule. | country |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. Retail Commercial Analyst owns interpretation; Engineer implements; Retail Finance Assurance Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

Descriptive/RFM core requires no predictive model. Use reference date 2011-12-01 and positive, non-cancellation invoices for RFM. Optional forecasting must use chronological rolling holdouts, never random line splitting.

Baseline ranks country × product combinations by positive sales value; alternative ranks by absolute negative-adjustment value / positive sales value with zero denominators unavailable. Customer action compares RFM quintile segments; top ten opportunities include known-customer coverage.

**Interpretation boundary:** C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
