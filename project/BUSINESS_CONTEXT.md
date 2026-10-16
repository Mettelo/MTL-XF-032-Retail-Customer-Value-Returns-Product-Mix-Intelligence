# MTL-XF-032 — Business context

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Organisation and problem

Confidential Multimarket Online Retailer is the fictional organisation. Sales totals hide cancellation activity, missing customer identities and concentrated product demand. Commercial managers need a reconciled view of gross sales, negative adjustments and customer value before assigning retention offers or changing the product range.

The Commercial Director needs a quarterly customer and merchandising review supporting **Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation.**

## Stakeholders

| Stakeholder | Decision | Required evidence |
| --- | --- | --- |
| Commercial Director | Approve scope, policy assumptions and next investigation/pilot. | D7 policy comparison, D11 recommendations, workload/risk and limitations. |
| Retail Commercial Analyst | Interpret observations and own action proposals. | K1–K7, source-supported dimensions, sensitivity and case lineage. |
| Data Governance Analyst | Approve source, freeze and interpretation rights. | S1 manifest, licence, actual schema and source-to-output support. |
| Operations / service owner | Accept workload and review/escalation responsibilities. | Action register, eligibility, owners, review dates and override reasons. |
| Retail Finance Assurance Analyst | Challenge correctness and release readiness. | DT1–DT10, UAT, reconciliations and clean rerun. |

## Workflow to improve

Current simulated process: separate extracts/headline totals → informal prioritisation → manual review with limited lineage. This is a teaching scenario, not an observed real client process.

Proposed process: acquire approved bytes → validate/freeze → curate at declared grain → calculate K1–K7 → compare policies → inspect uncertainty/exclusions → sponsor approves investigation/pilot → record disposition and review date. No score bypasses human approval.

## Questions to answer

1. What is the baseline positive sales value, and what defines its denominator?
2. Which supported groups/cases account for negative adjustment value, and with what sample support?
3. Which cases change between the baseline and alternative, and why?
4. How do the specified transformation, threshold, cost or capacity alternatives alter the decision?
5. Which recommendations remain unsupported and what evidence must be collected next?

## Decision and action evidence

Baseline ranks country × product combinations by positive sales value; alternative ranks by absolute negative-adjustment value / positive sales value with zero denominators unavailable. Customer action compares RFM quintile segments; top ten opportunities include known-customer coverage.

Every action record contains case/group key, snapshot, observed measure, eligibility, baseline and alternative rank/policy, evidence link, uncertainty, proposed next step, accountable owner, due/review date, disposition and override rationale. Use source-row IDs; do not invent real customer identities.

## Value and limits

Delivery success is evidence-backed acceptance of D1–D12, not guaranteed model superiority. Benefits remain hypotheses until an approved pilot specifies population, comparator, outcome window and guardrails. D11 includes three next actions and a case where the evidence does not justify action.

C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

**Risk to prevent:** Removing negative lines or missing customers before revenue accounting would overstate value and conceal coverage.

**Source boundary:** Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

Missing mandatory support blocks G1 or a dependent output until a governed scope/source decision is recorded.
