# Taifoon Enterprise License (TEL)

**Version 1.0 — in force from 2026-10-20.** Licensor: Interop FZCA, Dubai, United Arab Emirates. The `.ee.` source files
reference this licence. It is the base of the countersigned agreement that enterprises and venue partners (n8n as a venue, an inference partner) sign. It carries the Taifoon Access Terms
and TSUL rule 9 inside it.

## 1. What it grants
1. The right to run the `.ee.` features and to resell Taifoon capacity under the partner's own brand to its customers, with
   negotiated cuts, under keys of the partner's tenant (child keys for customers), with the meter preserved (TSUL rule 9).
2. Postpaid invoicing under a credit limit (the partner's balance may run negative to the limit; invoiced monthly), a negotiated
   cut schedule (the partner's markup leg and Taifoon's fee leg per product), KYB of the partner, a DPA, liability caps.
3. Support and change notice as scheduled; the partner's SLA is the predicate of the Access Terms plus what the schedule adds.

## 2. The reseller schedule (every partner that resells)
- **Wholesale is prepaid from the reseller's plan or balance, debited per call** at the list price. (Never: "wholesale owed is paid
  out per batch".)
- **What is owed per batch is child → reseller (list + markup)**, and the reseller invoices that itself; Taifoon does not invoice
  the reseller's customers.
- **Taifoon's payout of the reseller's own earnings** (its share of the legs where it is a seller or a contributor) waits on the
  vault payout-choice step (`register/owner-steps.json#reseller-markup-payout`); until then the ledger accrues.
- A child key has no free allowance; every child call is a meter line debited from the reseller.
- The reseller can set caps at mint, re-cap, roll and revoke any child; a child's keys manage nothing. Termination of a customer
  is the revocation of its keys.
- Tiers (the defaults an n8n reseller sets; the partner may set its own): starter 1 / 20 USDC a day / month at 2,500 bps markup;
  pro 10 / 200 at 2,000 bps; team 50 / 1,000 at 1,500 bps.

## 3. Flow-down
The partner binds its customers to the Taifoon Access Terms or to terms at least as protective and stays primarily liable; an
upstream venue's terms (Venice ToS 7.3) flow through the partner to its customers.

## 4. Term, audit, law
Term and renewal, an audit right over the meter (read-only, through the partner's own `GET /v1/access/reseller` and the stream),
termination for a rule-9 breach. The countersigned agreement sets the term, the renewal and any negotiated terms. Governing law:
the laws of the Emirate of Dubai and the federal laws of the United Arab Emirates as applied in Dubai, with the competent courts of Dubai as the venue for any dispute; the licensor is Interop FZCA, Dubai, United Arab Emirates.

Contact: builders@taifoon.io.
