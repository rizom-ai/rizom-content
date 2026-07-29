# Certified Partner Model

Proposal 2026-07-29 (working session, Jan Hein). Shapes the Rizom Certified Partner program. Supersedes nothing; fills the partner-program gap identified in the SWOT ("No external specialists yet").

## The stack it stands on

**Code.** The runtime moves from Apache to **AGPL-3.0**, relicensed now while copyright is fully in-house. The plugin SDK, `@brains/atproto-contracts`, and theme interfaces stay **Apache** so partners can build (and even sell) plugins and themes freely. Add a DCO for future contributions. Rationale: AGPL closes the proprietary-capture door (no closed hosted forks) while keeping the commons promise; the Grafana pattern.

**Mark.** The **foundation registers the Rizom wordmark** (EU filing) and publishes a one-page trademark policy: descriptive use ("built on Rizom Brains") is free; the **"Rizom Certified"** marks are reserved for listed partners; forks must rename. Free code + guarded mark is the entire legal architecture — what Rizom sells is the practice, the name, and the network.

## How certification works

- **One track at launch: Certified Practitioner**, with capability tags (facilitation · domain · implementation) instead of sub-tiers. Operator/deployment skill is a tag, not a separate track. Builder certification (plugins/themes) is deferred until the platform exits alpha.
- **Entry by apprenticeship, not exam**: a candidate co-delivers one real, paid engagement with Rizom (the Datacampus shape). No curriculum required to launch; the candidate is billable on the engagement that certifies them. This honors the brand rule of continuous evaluation over point-in-time gatekeeping.
- **Standing is continuous**: a public registry modeled on the ATProto lexicon registry (status, steward, delivered engagements, compatibility), with `candidate → active → steward` states. Dormancy fades a listing; nothing "expires."

## Governance and economics

- **The foundation certifies**: it owns the registry, the mark, and listing/delisting decisions. The commercial practice (/work) co-delivers, vouches, and is itself the **first listed partner**, subject to the same rules and the same remit.
- **Economics reuse the published 60/25/15 split, allocated by role**: 60% to whoever delivers, 15% to whoever brought the client and carries risk, 25% to the commons (platform development + foundation stewardship). A partner who sources and delivers keeps 75% and remits 25%. Referrals are symmetric in both directions with no separate fee schedule. The 25% is the license fee.
- **Published price bands** per engagement type, binding for work delivered under the mark ("no hidden margins" holds at the network edge). Anchor: the Datacampus engagement (€3–5k/month retainer, €10–20k build budget); the workshop band still needs setting.

## Where it fits

- Certification anchors at the **Collective** tier of the Community/Collective/Core ladder. **Core ownership stays a separate, earned invitation** under its existing criteria — certification never automatically confers ownership.
- Naming: externally everything is **Rizom Brains**. `rover` survives as internal/technical vocabulary only; `relay` and `recall` are both deprecated. Retired brand vocabulary ("Cores", "facilitators") does not return.

## Interim holding (until the foundation exists)

Decided 2026-07-29, addendum: only the BV exists today; the stichting is not yet formalized. The license choice is independent of the holder, so nothing waits:

- **Copyright sits with the BV for now** — headers read "Copyright © 2026 Rizom B.V.", AGPL-3.0. When the stichting exists, the BV assigns copyright by written deed (Dutch law requires a written instrument for copyright transfer).
- **DCO worded for succession from day one.** DCO contributors keep their own copyright, so the BV → stichting transfer never needs contributor consent.
- **Transfer early, while the IP valuation is minimal** — moving assets out of a BV below market value is a taxable event; at alpha stage the defensible valuation is low. Confirm with tax advisor.
- **Trademark: the BV files the wordmark now** (priority date is what matters) and assigns the registration to the stichting later.
- **Brand book correction required:** the present-tense claims "the IP is held by a non-profit" / "stewarded by an independent foundation" violate the brand's own honesty rule while the stichting doesn't exist. Reword to intent ("will be transferred to the independent Rizom Foundation upon its establishment") until it is real.
- **Founding the stichting is an early action item, not a distant one** — a few hundred euros and about a week at a notary; the certifier/steward/license-exception roles all hang on it.

## To make it real

1. Relicense commit + DCO — before any external contribution lands.
2. EU wordmark filing + trademark policy page from the foundation.
3. Set the workshop price band.
4. Define the registry format — the agent entities' `discovered → approved` flow gives a machine-readable partner directory almost for free.
5. Check the referenced AI grant program for reusable eligibility criteria.
6. Found the stichting; then execute the copyright deed and trademark assignment from the BV.