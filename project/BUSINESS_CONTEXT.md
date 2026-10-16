# MTL-XF-032 — Business context and practical use case

## Organisation and accountable decision

Confidential Multimarket Online Retailer is the simulated sponsor. The Commercial Director owns the quarterly customer and merchandising review and must decide: **Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation.**

## The operational problem

The commercial director must decide where retention and merchandising effort should go next quarter. A product may appear attractive on positive invoice value while generating substantial negative adjustments; a market may appear to have valuable customers while many sales lack customer IDs. The team needs one reconciled commercial ledger before it can compare account value, product concentration and cancellation exposure. Ignoring anonymous lines or deleting negative quantities would produce attractive but misleading totals.

## How the finished product will be used

During quarterly trading review, the director compares markets and products on positive value, signed adjustments and customer coverage, then reviews customer RFM groups and approves a ten-item retention/merchandising investigation register.

**Current approach:** Compare gross sales extracts and customer lists with inconsistent treatment of cancellations and missing IDs.

**Required future approach:** Use one signed-value bridge and explicit customer-coverage view before prioritising account and product actions.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Commercial Director | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Retail Commercial Analyst | Approve cancellation versus adjustment classification, RFM rules and ten evidence-linked account/product investigation cards. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Retail Finance Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Monthly trading reconciliation ledger** to support the stated decision, with this evidence: Month × Country totals of positive sales, negative adjustment value, other adjustments, signed transaction value, invoice counts and known-customer coverage; separate December 2011 exclusions.
2. Can the sponsor use **Customer value and product concentration analysis** to support the stated decision, with this evidence: Customer RFM as of 2011-12-01, with recency/frequency/monetary fields and deterministic quintile ties; top-ten product concentration by country; missing-ID coverage report.
3. Can the sponsor use **Ten commercial investigation cases** to support the stated decision, with this evidence: Up to ten country/product or customer-segment cases with positive value, adjustment ratio, coverage, baseline/alternative rank, action hypothesis, owner and evidence needed.
4. Can the sponsor use **Quarterly trading dashboard** to support the stated decision, with this evidence: Trading bridge, customer RFM, product/market concentration and data-quality views with common cutoff and country filters.
5. Can the sponsor use **Retention and merchandising decision pack** to support the stated decision, with this evidence: Three proposed interventions covering account retention, product investigation and market strategy; each has eligibility, accountable role, estimated affected value and pilot evaluation plan.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Monthly trading reconciliation ledger | Month × Country totals of positive sales, negative adjustment value, other adjustments, signed transaction value, invoice counts and known-customer coverage; separate December 2011 exclusions. |
| D6 | Customer value and product concentration analysis | Customer RFM as of 2011-12-01, with recency/frequency/monetary fields and deterministic quintile ties; top-ten product concentration by country; missing-ID coverage report. |
| D7 | Ten commercial investigation cases | Up to ten country/product or customer-segment cases with positive value, adjustment ratio, coverage, baseline/alternative rank, action hypothesis, owner and evidence needed. |
| D8 | Quarterly trading dashboard | Trading bridge, customer RFM, product/market concentration and data-quality views with common cutoff and country filters. |
| D11 | Retention and merchandising decision pack | Three proposed interventions covering account retention, product investigation and market strategy; each has eligibility, accountable role, estimated affected value and pilot evaluation plan. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Monthly trading reconciliation ledger | Every original workbook line is retained/excluded/quarantined once; valid signed values reconcile exactly before rounding; +100 and −20 give 80; anonymous sales remain in trading totals. |
| SC2 | D6 — Customer value and product concentration analysis | No invoice on/after the cutoff affects RFM; frequency counts distinct eligible invoices; anonymous lines never receive invented customer IDs; no profit/margin claim without cost data. |
| SC3 | D7 — Ten commercial investigation cases | Both ranking approaches use the same declared population; zero positive value yields unavailable adjustment ratio; every case distinguishes cancellation/adjustment evidence from confirmed physical returns. |
| SC4 | D8 — Quarterly trading dashboard | Five full-cohort and five filtered measures reconcile; a reviewer traces one cancellation-heavy product and one high-value RFM segment to source lineage. |
| SC5 | D11 — Retention and merchandising decision pack | Five findings cite tested numbers; affected value is not forecast uplift; every proposal states missing cost/return-reason evidence and an owner/date for obtaining it. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

**Failure to prevent:** Removing negative lines or missing customers before revenue accounting would overstate value and conceal coverage.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
