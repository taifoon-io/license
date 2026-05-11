# Taifoon Contributor License Agreement (CLA)

Thank you for contributing to Taifoon. This agreement clarifies the terms under
which contributions are made and protects both contributors and the project.

The CLA mirrors n8n's contributor agreement and adopts the same plain-English
shape. By submitting a contribution (a pull request, an adapter submission via
`BuildersRegistry`, a reviewer-agent submission, a documentation patch, or any
other authored material) you agree to the following:

---

## 1. You own what you contribute

You confirm that the contribution is your original work, OR that you have the
right to submit it under the terms below. You are responsible for the
contribution. If your employer holds rights to work you produce, you confirm
you have permission to submit it.

## 2. Grant of license

You grant the Taifoon project (the maintainers operating under
`taifooon@proton.me`) a perpetual, worldwide, non-exclusive, royalty-free,
irrevocable license to use, reproduce, modify, distribute, sublicense, and
relicense the contribution, including under licenses other than the Taifoon
Sustainable Use License if the project's license terms change in the future.

This relicensing right exists for one operational reason: as the project
matures, license terms may need to adapt (to align with regulatory
requirements, to add or remove enterprise tiers, to refine the on-chain donut
clause). Without the relicensing right, every license update would require
re-collecting consent from every past contributor, which is impractical at
scale.

You retain all other rights to your contribution and may use it however you
wish in your own work.

## 3. Patents

If your contribution incorporates inventions you have rights to, you grant the
Taifoon project a perpetual, worldwide, non-exclusive, royalty-free patent
license to make, use, sell, offer for sale, and import implementations of
those inventions as part of the project.

## 4. No liability

You are not liable for damages arising from the use of your contribution by
others. The contribution is provided "as is", without warranty.

## 5. Donut routing acknowledgment

You acknowledge that contributions which merge through
`BuildersRegistry.finalizeMerge()` enter the donut routing system as defined
in rule #4 of the Taifoon Sustainable Use License. Your wallet address as
recorded at submission becomes the perpetual recipient of the creator slice
(70% of the 49 bps donut on every settled call routed through your
contribution) for as long as the contribution stays merged. This is not a
warranty of revenue; it is a description of how the routing works.

## 6. GitHub terms

If you submit via GitHub, GitHub's
[Terms of Service](https://docs.github.com/en/site-policy/github-terms/github-terms-of-service#d-user-generated-content)
also apply to your contribution.

---

## How to sign

The first time you submit a pull request to a Taifoon repository, the CLA bot
will comment with a link asking you to confirm acceptance. Accept once and
your acceptance covers all future contributions to the same repository
identity.

For wallet-based submissions through `BuildersRegistry.submitAdapter()`, the
on-chain transaction signature itself constitutes acceptance of this CLA at
the version current as of the submission block. The current CLA version is
hashed into the contract's `CLA_VERSION_HASH` constant; updates require a new
hash and explicit re-acceptance from contributors who submit after the
update block.

For license questions or to request bespoke contribution terms, email
**taifooon@proton.me**.

---

**Last updated:** 2026-05-08
**Version:** 1.0
