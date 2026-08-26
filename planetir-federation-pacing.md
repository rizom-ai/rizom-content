---
visibility: restricted
---
# Planetir federation — pacing

Decision note · Rizom B.V. · 26 August 2026 · Companion to "Board memo — AT ONE Impact Week 2026" (the Impact Week memo is organisational; this note holds the technical question)

## What the federation is

The technical relationship is designed in the TrustFlow federation plan (`docs/plans/trustflow-federation-integration.md` in the brains repo): TrustFlow, the Planetir/Kaphera dataspace, is the governance and contract layer; a brain is the node runtime a member operates. Each side covers the other's largest gap — they have no runtime, agent, content store, or publishing surface; we have no agreement primitive and no way to share an entity under terms.

## Status

Proposed. No code on our side. Their prototype's API is fictional (simulated locally). The plan's one external dependency is a real catalogue endpoint from Kaphera; every phase is testable against a recorded fixture without it.

## The Impact Week pressure

The delegation's "experimental open data space" at IW26 (8–12 September) is almost certainly TrustFlow's public debut. Risk: the event creates pressure for something real by 8 September — the unpaid-rush-build failure mode. Opportunity: the debut generates real-world signals (who joins, what they share, what the governance actually needs) that the federation plan currently lacks.

## Position

The federation advances on the plan's own phasing, never on event pressure.

- Before the week: ask Daphne and Mehemed what the IW26 open data space will actually run on, and whether a real Kaphera catalogue endpoint exists yet.
- No integration code is rushed for the event. If a live demonstration is wanted, it is the recorded-fixture path the plan already defines, or their existing simulated prototype.
- Any build beyond the plan's phasing happens under written pilot terms (paid pilot or formal partnership with named scope).

## Decision deferred

Whether to prioritise the federation phases this quarter is decided after Impact Week, against the signals the debut produces — not before.
