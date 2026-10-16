# MTL-XF-032 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Retail Finance Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Commercial Director approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | Every original workbook line is retained/excluded/quarantined once; valid signed values reconcile exactly before rounding; +100 and −20 give 80; anonymous sales remain in trading totals. |
| AC6 | D6 / SC2 | No invoice on/after the cutoff affects RFM; frequency counts distinct eligible invoices; anonymous lines never receive invented customer IDs; no profit/margin claim without cost data. |
| AC7 | D7 / SC3 | Both ranking approaches use the same declared population; zero positive value yields unavailable adjustment ratio; every case distinguishes cancellation/adjustment evidence from confirmed physical returns. |
| AC8 | D8 / SC4 | Five full-cohort and five filtered measures reconcile; a reviewer traces one cancellation-heavy product and one high-value RFM segment to source lineage. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Five findings cite tested numbers; affected value is not forecast uplift; every proposal states missing cost/return-reason evidence and an owner/date for obtaining it. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Monthly trading reconciliation ledger

**Accountable delivery role:** Retail Commercial Analyst. **Business reviewer:** Commercial Director. **Independent assurance:** Retail Finance Assurance Analyst.

**Required artefact:** data/curated/monthly-trading-reconciliation-ledger.csv and docs/05-kpi-catalogue/monthly-trading-reconciliation-ledger.md.

**Content:** Month × Country totals of positive sales, negative adjustment value, other adjustments, signed transaction value, invoice counts and known-customer coverage; separate December 2011 exclusions.

**Pass condition:** Every original workbook line is retained/excluded/quarantined once; valid signed values reconcile exactly before rounding; +100 and −20 give 80; anonymous sales remain in trading totals.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Customer value and product concentration analysis

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Commercial Director. **Independent assurance:** Retail Finance Assurance Analyst.

**Required artefact:** docs/06-analysis/customer-value-and-product-concentration-analysis.md plus machine-readable evaluation_results.csv.

**Content:** Customer RFM as of 2011-12-01, with recency/frequency/monetary fields and deterministic quintile ties; top-ten product concentration by country; missing-ID coverage report.

**Pass condition:** No invoice on/after the cutoff affects RFM; frequency counts distinct eligible invoices; anonymous lines never receive invented customer IDs; no profit/margin claim without cost data.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Ten commercial investigation cases

**Accountable delivery role:** Retail Commercial Analyst. **Business reviewer:** Commercial Director. **Independent assurance:** Retail Finance Assurance Analyst.

**Required artefact:** docs/07-decision-framework/ten-commercial-investigation-cases.csv plus policy.md.

**Content:** Up to ten country/product or customer-segment cases with positive value, adjustment ratio, coverage, baseline/alternative rank, action hypothesis, owner and evidence needed.

**Pass condition:** Both ranking approaches use the same declared population; zero positive value yields unavailable adjustment ratio; every case distinguishes cancellation/adjustment evidence from confirmed physical returns.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Quarterly trading dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Commercial Director. **Independent assurance:** Retail Finance Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Trading bridge, customer RFM, product/market concentration and data-quality views with common cutoff and country filters.

**Pass condition:** Five full-cohort and five filtered measures reconcile; a reviewer traces one cancellation-heavy product and one high-value RFM segment to source lineage.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Retention and merchandising decision pack

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Commercial Director. **Independent assurance:** Retail Finance Assurance Analyst.

**Required artefact:** deliverables/retention-and-merchandising-decision-pack.pdf plus editable slides and supporting cards/runbook.

**Content:** Three proposed interventions covering account retention, product investigation and market strategy; each has eligibility, accountable role, estimated affected value and pilot evaluation plan.

**Pass condition:** Five findings cite tested numbers; affected value is not forecast uplift; every proposal states missing cost/return-reason evidence and an owner/date for obtaining it.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Signed arithmetic | Lines +100 and −20 GBP produce signed value 80 and negative adjustment −20. |
| DT2 | Missing identity | A positive anonymous 50 GBP line remains in totals and reduces known-customer coverage. |
| DT3 | Repeated item | Two identical-looking invoice-item lines retain separate source row identities pending a documented duplication decision. |
| DT4 | C invoice | An invoice starting c or C is flagged cancellation irrespective of case. |
| DT5 | Core boundary | 2011-12-01 00:00 is excluded; 2011-11-30 23:59 is included. |
| DT6 | RFM leakage | A post-cutoff invoice cannot affect recency, frequency or monetary scores. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** During quarterly trading review, the director compares markets and products on positive value, signed adjustments and customer coverage, then reviews customer RFM groups and approves a ten-item retention/merchandising investigation register. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Five full-cohort and five filtered measures reconcile; a reviewer traces one cancellation-heavy product and one high-value RFM segment to source lineage. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
