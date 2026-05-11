# Taifoon Sustainable Use License

**Version 1.0 — May 2026**

This license governs the source code in this repository, except for files
explicitly marked otherwise (see `## Scope` below). It is fair-code: source is
open, distribution is open, internal use is permitted, the platform stays
sovereign, and revenue routing is enforced on-chain.

The Taifoon Sustainable Use License (TSUL) is derived from
[n8n's Sustainable Use License](https://github.com/n8n-io/n8n/blob/master/LICENSE.md)
and the broader [fair-code](https://faircode.io/) model, with one structural
addition: **donut routing is enforced on-chain** by the BuildersRegistry
contract. Any commercial deployment that strips, bypasses, or substitutes the
donut is a license violation enforceable both legally and via the registry's
revocation hooks.

If you have license questions, email **taifooon@proton.me**.

---

## The four rules

The license grants you the free right to use, modify, create derivative works,
and redistribute, with **four** limitations:

1. **You may use or modify the software only for your own internal business
   purposes or for non-commercial or personal use.**

2. **You may distribute the software or provide it to others only if you do so
   free of charge for non-commercial purposes.**

3. **You may not alter, remove, or obscure any licensing, copyright, donut
   routing, or other notices of the licensor in the software.** Any use of the
   licensor's trademarks ("Taifoon", the orbital trace, the singularity glow) is
   subject to applicable law.

4. **Any deployment that routes value through Taifoon's adapter fleet must
   preserve the on-chain donut.** A 49 bps skim of every settled call is routed
   through `BuildersRegistry.recordRevenueTouch()` and split: 70% to the
   contributor whose adapter routed the value, 20% to the reviewer agents that
   certified it, 10% to the ecosystem treasury. Removing, circumventing, or
   substituting donut routing — including via fork-and-rehost, calldata
   pre-processing that bypasses the registry, or proxy patterns that hide the
   adapter call — constitutes a license violation.

---

## Scope

This license applies to all source code in this repository EXCEPT:

- Files under `templates/adapter-v1/` — these are the contributor templates and
  are licensed under **Apache License 2.0**. The contributions you ship using
  these templates inherit TSUL when they merge through `BuildersRegistry`.
- Branches other than the default branch — only the canonical branch is
  covered.
- Source code files that contain `.ee.` in their file name — these are licensed
  under the separate Taifoon Enterprise License (`LICENSE_EE.md`).

---

## What is and isn't allowed

In practice, all use is allowed unless you are selling a product, service, or
module in which the value derives entirely or substantially from Taifoon
functionality, OR you are bypassing the donut.

### NOT ALLOWED

- White-labeling Taifoon and offering it to your customers for money.
- Hosting Taifoon's solver core or adapter fleet and charging users to access
  it without preserving the on-chain donut.
- Forking the BuildersRegistry contract, removing the donut clause, and
  deploying it as a competing marketplace.
- Replacing `recordRevenueTouch()` with a no-op, or stripping the registry call
  before adapter execution.
- Using "Taifoon" or any confusable mark in the name of a hosted competing
  service.

### ALLOWED

- Using Taifoon to coordinate cross-chain data flows your own organization
  controls — for example, syncing protocol state into an internal data
  warehouse, or routing your own treasury rebalancing through the adapter
  fleet.
- Creating a Taifoon adapter for your protocol or any other integration
  between your protocol and Taifoon. (Donut applies to settled calls; that is
  the whole point.)
- Providing consulting services related to Taifoon — building adapters,
  reviewer agents, custom integrations, or operations support.
- Supporting Taifoon — running mirrors, mirror reviewers, or maintaining it on
  internal company infrastructure.
- Contributing back: every merge through `BuildersRegistry.finalizeMerge()`
  triggers donut routing, and your contribution earns its slice perpetually.

---

## Worked examples

### Example 1 — ALLOWED

Alice ships a Solana-Mayan adapter against bounty `b-mayan-sol-001` in
`taifoon-eco/contracts/adapters/`. Her adapter passes both reviewer-agent
verdicts on devnet. After the 24h challenge window, anyone calls
`finalizeMerge`. From that block, every Mayan fill routed through her adapter
splits a 49 bps donut: 70% to Alice, 20% to the reviewers, 10% to the
ecosystem. Alice may simultaneously offer paid consulting services to teams
who want to integrate her adapter — that is allowed.

### Example 2 — NOT ALLOWED

Bob forks `taifoon-solver/` and `taifoon-eco/contracts/`, removes the
`recordRevenueTouch()` call from the executor path, redeploys the contracts
under a different name, and offers "FastBridge by Bob" as a hosted SaaS that
charges users for cross-chain swaps. The value derives entirely from Taifoon's
adapter fleet, AND the donut is bypassed. Both rule 1 ("internal business
purposes only") and rule 4 ("preserve the on-chain donut") are violated.

### Example 3 — ALLOWED

A protocol team integrates Taifoon as the back-end of their internal treasury
rebalancer. Treasury credentials never leave the team. No external customers
access the integration. This is internal business use.

### Example 4 — NOT ALLOWED

The same protocol team turns the rebalancer into a public product, charging
end-users to rebalance their wallets via Taifoon's adapters, and arranges
billing such that fees never flow through `BuildersRegistry`. The fact that
the adapter calls still execute does not make this allowed — the donut must
be preserved.

---

## Why a license, and not Apache 2.0

Open-source licenses, by OSI's definition, cannot include limitations on use.
Taifoon needs two limitations that OSI cannot accommodate:

1. The on-chain donut is the funding mechanism for the agent fleet, the
   reviewer pool, and the ecosystem treasury. Without it, a single hosted-fork
   could capture all value while contributing none back.
2. The "internal business purposes" boundary, borrowed from n8n, prevents
   commercial-rehost capture without restricting the legitimate operational
   use that the vast majority of users will need.

We coined no new framework. TSUL is fair-code with one on-chain clause. If
you'd otherwise pick n8n's SUL for your project, TSUL behaves the same way for
99% of cases.

---

## Permissive enterprise licensing

If your use case isn't permitted by the four rules — for example, you want to
embed Taifoon in a commercial product whose value derives substantially from
the adapter fleet, and the donut model doesn't fit your billing — sign a
separate commercial agreement with us. Email **taifooon@proton.me**.

---

## Contributor License Agreement

Every contributor signs the [Contributor License Agreement](./CONTRIBUTOR_LICENSE_AGREEMENT.md)
on first PR. The CLA mirrors n8n's: you retain ownership of your contribution,
grant Taifoon the right to relicense, and are not liable for damages your
contribution causes downstream.

---

## Trademarks

"Taifoon", the orbital trace, the singularity glow, and the brand color
palette (Field Blue #3DA5FF, Electric Teal #00B5B8, Volt #B8F500 on
#000000-dominant surfaces) are trademarks of the Taifoon project. You may
reference them factually ("built on Taifoon", "uses Taifoon adapters") but
must not use them in product names, logos, or marketing for hosted
competing services.

---

## Reuse of TSUL

You may use TSUL for your own project. We'd love to hear about it — email
**taifooon@proton.me**. If your project also has on-chain revenue routing,
adapt the donut clause (rule #4) to reference your own registry contract.

---

## Authority

Last updated 2026-05-08. The canonical version of this license is the
`LICENSE.md` file at the root of `github.com/taifoon-io/taifoon-eco` and
`github.com/yawningmonsoon/taifoon-eco`. All other copies are mirrors.

For the operative on-chain implementation, see
`taifoon-eco/src/BuildersRegistry.sol`, function
`recordRevenueTouch()`.

Email **taifooon@proton.me** for any license question.
