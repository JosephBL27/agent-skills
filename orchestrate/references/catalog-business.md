# Catalog — business, finance, CRM

**Mostly dormant for Joseph.** He is a student with research and internship work,
not an SMB owner. These come bundled with connector plugins and most require an
authenticated connector (QuickBooks, PayPal, Square, Stripe, HubSpot, Apollo)
that is **not connected**. Route here only on an explicit ask.

**Before routing to any of these, check the connector is actually live.** Most
will fail at the first tool call otherwise, and saying "not connected" up front is
better than a half-run workflow.

## Genuinely useful to Joseph now

- `small-business:contract-review` — NDA, MSA, internship/research agreements.
  Reads local files, Gmail attachments, or DocuSign; flags non-standard terms in
  plain English; outputs a DOCX redline. **No connector needed for local files.**
- `small-business:job-post-builder` — job posts, structured interview guides,
  scoring rubrics. Useful in reverse: understanding what a rubric is screening for.
- `finance:financial-statements`, `finance:variance-analysis` — reading and
  explaining statements. Relevant to his econometrics and finance work as
  *analysis*, not bookkeeping.

## Requires a live connector — confirm first

- **Cash and close:** `cash-flow-snapshot`, `close-month`, `month-end-prep`,
  `month-heads-up`, `plan-payroll`, `invoice-chase`, `tax-prep`,
  `tax-season-organizer`, `quarterly-review`
- **Sales and CRM:** `lead-triage`, `call-list`, `crm-cleanup`, `crm-maintenance`,
  `sales-brief`, `apollo:prospect`, `apollo:enrich-lead`, `apollo:sequence-load`
- **Customer:** `customer-pulse`, `customer-pulse-check`, `handle-complaint`,
  `ticket-deflector`
- **Content:** `content-strategy`, `canva-creator`, `run-campaign`
- **Briefings:** `business-pulse`, `monday-brief`, `friday-brief`, `smb-onboard`,
  `smb-router`, `price-check`, `margin-analyzer`
- **Accounting practice:** `finance:reconciliation`, `journal-entry`,
  `journal-entry-prep`, `close-management`, `audit-support`, `sox-testing`

## Standing constraints

- **Never execute a trade, transfer, or payment.** Purchases with a saved payment
  method need explicit per-action confirmation; trades and transfers are refused
  outright regardless of authorisation.
- **No personalised investment advice.** Explain that you are not a licensed
  advisor.
- Budgeting and accounting apps may be *read and organised* freely — categorising
  transactions and generating reports is fine; moving money is not.
