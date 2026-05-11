# Taifoon licenses

> *One license. One file. One answer.*

This repo holds the canonical text of every license used across the Taifoon project. It is the **single source of truth**. Every other Taifoon repo, every page on taifoon.io, every contract that references "TSUL" points here.

| File | Applies to |
|------|-----------|
| [`LICENSE.md`](./LICENSE.md) | The Taifoon Sustainable Use License (TSUL) v1.0 — fair-code, on-chain donut routing. Used by `taifoon-eco`, `taifoon-mamba`, `open-mamba`, `taifoon-next` (the platform / contract / agent code). |
| [`APACHE-2.0.md`](./APACHE-2.0.md) | Apache License 2.0 — used by `taifoon-solver`, `taifoon-sdk`, and contributor templates (the public-goods code). |
| [`CONTRIBUTOR_LICENSE_AGREEMENT.md`](./CONTRIBUTOR_LICENSE_AGREEMENT.md) | The CLA every contributor accepts on first PR or first on-chain `submitAdapter()`. |

Public FAQ (worked examples, plain-English explanations): https://taifoon.io/legal/tsul

License questions: **taifooon@proton.me**

---

## License posture across the org

```
taifoon-io/
├── license/                  PUBLIC      ← you are here. Canonical text. CC0 on metadata,
│                                          operative licenses inside are TSUL + Apache 2.0 + MIT.
├── taifoon-solver/           PUBLIC      Apache 2.0  ← solver core, Frontier submission
├── taifoon-sdk/              PUBLIC      Apache 2.0  ← public SDK (npm: @taifoon/sdk)
├── open-mamba/               PUBLIC      MIT         ← the free task-bus engine (Rust)
├── taifoon-mamba/            PUBLIC      TSUL        ← Pro tier on top of open-mamba (dispatcher,
│                                                       bounty scoper, cost-optimizer)
├── taifoon-design-system/    PUBLIC      CC-BY-4.0   ← design tokens, fonts, UI kit
├── .github/                  PUBLIC      CC0         ← org meta (this README displays at taifoon-io)
│
├── taifoon-eco/              PRIVATE     TSUL        ← BuildersRegistry, adapters, donut routing
└── taifoon-next/             PRIVATE     TSUL        ← taifoon.io website source
```

The split is deliberate. **Four rules of thumb:**

1. **MIT** is for the engine layer that needs to be unrestricted-foundation infrastructure. `open-mamba` is the Rust task-bus engine — anyone can self-host, embed, or fork without any clause to read. The `taifoon-mamba` Pro tier runs on top and carries the commercial features.
2. **Apache 2.0** is for the layers that need maximum reach with patent grants. `taifoon-solver` and `taifoon-sdk` are public, OSI-compliant, and eligible for procurement processes that ban any "commercial-restriction" clause. Anyone can fork, embed, integrate.
3. **TSUL · public** is for the layers that earn credibility by being readable: `taifoon-mamba` (the Pro dispatcher built on open-mamba). The license enforces the on-chain donut without restricting visibility — the source is the proof of how the OS works.
4. **TSUL · private** is for the layers where source visibility would erode the sovereignty: `taifoon-eco` (the contracts and donut-routing logic) and `taifoon-next` (the brand surface). TSUL still applies to the source — copyright + the donut-preservation clause survive — but the code itself is owner-only. The deployed contracts on devnet 36927 are auditable on-chain; the brand surface is the live taifoon.io site.

**CC-BY-4.0** on the design system lets anyone use Taifoon's visual language (with attribution) — important for partner integrations.

## Why this repo exists separately

Mirrors n8n's pattern: the operative `LICENSE.md` is pinned at one canonical location, every other repo references it. When the license version bumps, one place updates and every repo's link still works. No drift.

## Reuse

Want to use TSUL for your own project (especially if you have on-chain revenue routing)? Email **taifooon@proton.me** — we'd love to know about it. Adapt rule #4 to reference your own registry contract.
