# Vault Grant

**Version 1.0 — DRAFT FOR REVIEW BY COUNSEL (October 2026).** The one signature a tenant or a vault makes so that every key it
mints inherits the Taifoon Access Terms and TSUL rule 9. The same shape as a platform agreement a payment platform signs once for
its sub-accounts, and as a signed spending mandate for an agent: the grant lists the parties, the allowed scopes, the spending cap
per key and period, the cuts, the screening level and the upstream venue terms.

## 1. The grant
| field | what the grant says |
|---|---|
| grantor | the tenant (or its vault) that signs: its id and the wallet or device key that signs |
| party | enterprise · venue · reseller · onchain buyer · onchain seller · agent under a vault |
| documents | the documents it accepts for every key it mints: TSUL 1.1, TAT (and TEL where countersigned) |
| scopes | the most a minted key may hold (inference · hire · sell · vault); a minted key only narrows |
| spend cap | per key per period (a day, a month) in USDC; the layer enforces it on every child key |
| cuts | the legs the grantor takes or pays: reseller_markup, our_fee, venue_fee, provider, graders, ecosystem (the commerce catalogue) |
| screening | none · wallet screen · KYB, as the party requires |
| venue terms | the upstream venues whose terms flow down through this grant (Venice, the Taifoon GPU grid) |
| signs by | EIP-712 by the wallet, click-through under a key, or a countersigned contract |

## 2. How it is made and kept
1. A tenant signs once (`POST /v1/access/agreements {doc: "VAULT-GRANT", …}` with its key, or the EIP-712 message its wallet
   signs); the acceptance is a record envelope on the stream under the key's ref (never the key), order key
   `agreement:<ref>:VAULT-GRANT:<version>`.
2. Every key the tenant mints afterwards (its own keys, its children) carries `flowdown_from` = that record; a child's calls are
   under the grant without a second signature.
3. Revoking the grant revokes nothing by itself; it stops new mints. The keys already minted keep their caps and their record.

## 3. What the box enforces for a vault (when the tenant vault is live)
The vault's sign policy is the grant's spend cap and scopes in the box's own words: the Taifoon vault key signs only what the
policy allows, and the grant is the policy's signed authorization (wiki VAULT §4). Until the tenant vault is built, the grant
governs keys only.

Contact: builders@taifoon.io.
