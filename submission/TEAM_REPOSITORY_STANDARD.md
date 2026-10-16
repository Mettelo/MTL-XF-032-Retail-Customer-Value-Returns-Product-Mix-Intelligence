# MTL-XF-032 — Team repository standard

Create **MTL-XF-032-<team-name>** under **Mettelo** and add individual member accounts. Record [master URL](https://github.com/Mettelo/MTL-XF-032-Retail-Customer-Value-Returns-Product-Mix-Intelligence), reviewed master specification commit and final team commit/tag.

## Required areas

- README.md and CONTRIBUTIONS.md
- data/SOURCE_REGISTER.md; data/raw/README.md; data/reference/; data/metadata/; data/curated/
- docs/01-discovery/; docs/02-data-governance/; docs/03-data-model/; docs/04-data-quality/
- docs/05-kpi-catalogue/; docs/06-analysis/; docs/07-decision-framework/
- docs/08-assurance-uat/; docs/09-technical-handover/
- src/; tests/; dashboard/; deliverables/; submission/FINAL_SUBMISSION.md

Use sql/notebooks/analysis folders where useful; explain unused areas and avoid duplicate implementations. Pin free toolchain/dependencies and one documented run entry point. Keep raw payloads in approved storage outside Git, with verified manifest and reviewer access; never embed credentials.

## README and contribution evidence

State Choose up to ten customer segments, product groups or country markets for retention and merchandising investigation. Name Commercial Director as simulated sponsor. Include cohort, acquisition/restore, environment/run instructions, five findings, baseline/alternative, assumptions, UAT/rerun and evidence links. Preserve the simulated-client declaration and this limit: C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

Assign named people to all seven [brief roles](../project/PROJECT_BRIEF.md). Every member links authored artefacts, at least one substantive review, and demo/handover contribution. Issues, commits, PRs and review records support evidence; commit count or one person's bulk upload is insufficient.

## Project-specific handover

Approve cancellation versus adjustment classification, RFM rules and ten evidence-linked account/product investigation cards.

Maintain D1–D12/AC1–AC12/DT1–DT10 evidence index with owner, distinct reviewer, state and final-commit path. Connect numeric claims to frozen source and code/configuration. Record all manual adjustments, excluded cases and limitations; preserve an insufficient-evidence case.

## Required business-output artefacts

- **D5 Monthly trading reconciliation ledger:** data/curated/monthly-trading-reconciliation-ledger.csv and docs/05-kpi-catalogue/monthly-trading-reconciliation-ledger.md.
- **D6 Customer value and product concentration analysis:** docs/06-analysis/customer-value-and-product-concentration-analysis.md plus machine-readable evaluation_results.csv.
- **D7 Ten commercial investigation cases:** docs/07-decision-framework/ten-commercial-investigation-cases.csv plus policy.md.
- **D8 Quarterly trading dashboard:** dashboard/README.md, runnable dashboard/prototype and static review export.
- **D11 Retention and merchandising decision pack:** deliverables/retention-and-merchandising-decision-pack.pdf plus editable slides and supporting cards/runbook.

Index these under SC1–SC5 with author, distinct reviewer, executed result and final commit. Treat these paths as the default delivery contract; an equivalent tool-specific format requires an explicit documented mapping.
