# MTL-XF-032 — References and mappings

Retain source documentation, licence/citation notices and required codebooks for Online Retail II. Read both workbook worksheets with explicit header mapping (Invoice, Price, Customer ID). Preserve sheet and original row lineage; source-line identity is not Invoice×StockCode.

Version each reference with ID, official URL, retrieval date/version, content checksum, rights, raw→display mapping, rationale, owner and reviewer. Unknown categories remain visible; validate mapping completeness/uniqueness and all many-to-many joins.

**Interpretation rule:** C-prefixed invoices identify cancellations; negative quantities are adjustment evidence, not confirmed physical returns. There is no cost of goods, profit margin, marketing spend or confirmed return reason. Missing CustomerID rows remain in commercial totals but cannot be assigned to customer RFM.

**Project policy assumptions:** Baseline ranks country × product combinations by positive sales value; alternative ranks by absolute negative-adjustment value / positive sales value with zero denominators unavailable. Customer action compares RFM quintile segments; top ten opportunities include known-customer coverage.

Keep choices separate from publisher facts. Register categorical/segment/class labels, unit conversions and any financial or capacity assumptions. Do not invent operational history absent from S1.

A reference explains the source; it cannot supply an unmeasured outcome. Register supplements and scope changes in [SOURCE_REGISTER.md](../SOURCE_REGISTER.md) before dependent work.
