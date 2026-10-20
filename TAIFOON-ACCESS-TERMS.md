# Taifoon Access Terms (TAT)

**Version 1.0 — in force from 2026-10-20.** Offered by Interop FZCA, Dubai, United Arab Emirates ("Taifoon", "we"). This is
the service contract that governs the use of a Taifoon key; the software is governed by the Taifoon Sustainable Use License
(`LICENSE.md`). The two share one rule: every billed unit carries a Taifoon key and produces a meter line whose legs include the
ecosystem cut (TSUL rule 9).

How you accept these terms: by minting a key (`POST /v1/register`, the cockpit, the n8n node's Register Free Key), by the signed
message your wallet makes when it accepts them (EIP-712), or by the written agreement that names them. A child key of a reseller
inherits the reseller's acceptance; the reseller remains primarily liable for its customers.

## 1. The key is the product
1. A key (`tfr_…`) is one metered account of your tenant: its scopes say what it may call, its balance or plan says what it may
   spend, its grant says under which agreement. It is shown once; only its hash is kept; nobody can read it back, Taifoon included.
2. You hold the key. A key in your store is yours to roll or revoke; a key you give to a customer is a child key, capped and
   revocable by you. You are responsible for every call a key of yours makes.
3. A key never signs. Nothing you do with a key moves value from a wallet. A payment to Taifoon is a transfer your wallet sends and
   signs; a payout from Taifoon is signed by Taifoon's vault key under its policy.

## 2. Scopes, balances, plans, allowances
1. Each product door names the scope a key needs (rpc · proofs · events · coordination-read · coordination-write · grades) and the
   balance it needs before a paid call. A free allowance exists only for a tenant's own keys and never for a resold child key.
2. A balance is prepaid (GRID: 100 GRID = 1 USDC) by a top-up you send and sign, or by a plan paid up front for 30 days. Billing is
   deferred while the balance covers the call; a meter line is a debit on the balance, never a transaction.
3. A captured line is final: a delivered call is not refunded. A call the content rule refuses is refunded by the same rule. Prices are
   the catalogue's (`GET /v1/access/products`), changed with thirty days' notice.
4. Where a venue upstream of Taifoon is paid per call or by a prepaid balance (Venice by x402, a GPU host by meter), its cost is a
   leg of your line; you never deal with the venue.

## 3. The SLA predicate and what Taifoon does not promise
1. Taifoon promises what the predicate says for a route: the route is complete (supply delivers, terms allow, the class is listed, the
   rail is live), the call is metered, the receipt is on the stream. Nothing else is promised. Proofs are recomputable from public data.
2. No warranty beyond the predicate; liability capped at the fees of the month in which the claim arose, to the extent the law allows.

## 4. Acceptable use and screening
1. No use that is unlawful, that targets a private individual, that evades a venue's terms, or that strips the key or the meter line
   from a billed unit (TSUL rule 9). No sharing of a key between tenants.
2. Wallets and tenants are screened against sanctions lists; a screened-out wallet gets no key and no payout. A reseller screens its
   customers to the level its grant names.

## 5. Upstream venue terms that flow down
1. Venice AI (inference): end users are bound by terms at least as protective as Venice's; the reseller stays primarily liable
   (Venice ToS 7.3). Private models carry Venice's privacy class; nothing is logged by Taifoon beyond the meter line.
2. GPU hosts on the grid: a host's terms (`POST /v1/resources/register`) flow to the buyer of its capacity through this document.
3. n8n Cloud or self-hosted n8n: n8n's own terms govern your instance; Taifoon's node and workflows are MIT.

## 6. Resale (the reseller's duties)
1. A reseller mints child keys for its customers (capped, scoped, revocable), flows these terms down in writing, invoices its
   customers itself (list + markup), and is debited at the list price per call from its own balance or plan.
2. The Vault Grant is the reseller's one signature for every key it mints; the Taifoon Enterprise License replaces it for enterprises
   and venues with negotiated terms.

## 7. Term, changes, law
1. These terms run while a key of yours exists; revoking every key ends them for that tenant, the record stays.
2. Changes with thirty days' notice on the site and in the acceptance record; continued use is acceptance.
3. Governing law and venue: these terms are made with Interop FZCA, Dubai, United Arab Emirates, and are governed by
   the laws of the Emirate of Dubai and the federal laws of the United Arab Emirates as applied in Dubai, with the competent courts of Dubai as the venue for any dispute.

Contact: builders@taifoon.io · the governing text lives in this repository; the site (`/legal/access-terms`) mirrors it.
