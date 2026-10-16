# MTL-XF-032 — Source register

## S1 — Online Retail II

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/502 |
| Exact download | https://archive.ics.uci.edu/static/public/502/online+retail+ii.zip |
| Required inputs | online_retail_II.xlsx |
| Source population | 1,067,371 source invoice lines across two worksheets |
| Decision owner | Commercial Director |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5CG6D

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **45622418 bytes**; SHA-256 **572e36277c2390fbfde10664750731e0a86f55e33470d91919085f0408e67bfb**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| online_retail_II.xlsx | 45622278 | bcbe73b35f5b7babf197fb0cb983a11f5d9ff929078d4aa53d171b1f2df2e980 |

Member names and byte hashes were inspected; CSV record counts were checked where present. Actual cohort transformations and business analysis remain team delivery work.

Read both workbook worksheets with explicit header mapping (Invoice, Price, Customer ID). Preserve sheet and original row lineage; source-line identity is not Invoice×StockCode.

## Cohort and field support

Read both original workbook worksheets. Core complete-month window is 2009-12-01 00:00 inclusive to 2011-12-01 00:00 exclusive; retain December 2011 rows outside core with explicit exclusion counts. Freeze customer segmentation at 2011-12-01.

**Grain:** Invoice line with worksheet and original row number; do not assume Invoice + StockCode is unique.

**Required mapping:** Invoice/InvoiceNo, StockCode, Description, Quantity, InvoiceDate, Price/UnitPrice, Customer ID/CustomerID, Country; map actual worksheet headers explicitly.

**Interpretation limits:** C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5CG6D); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
