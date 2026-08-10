## Context

In March 2026 six organisations — Frequency, Leading Edge, LightDAO, Earth One, Earthkind, and Omya — began forming **The Federation**: a coordinating layer that lets member networks collaborate while each keeps its own sovereignty. Their kickoff document (*The Federation — Kickoff Meeting Guide, Draft v1.0*) is mostly a data protocol rather than a manifesto.

It defines a shared taxonomy of six network roles (Founder, Funder, Network Steward, Influencer, Subject Matter Expert, Coherence Facilitator), each with typed fields and a steward-private 0–5 Network Trust Score. On top of that it specifies minimum-viable records for six shareable categories: Contacts, Initiatives, Deals, Events, Memberships, and Jobs. Governance is deliberately light — calls every six weeks through the 2026 pilot, async in between, consensus by default.

Implementation is planned in two phases: a shared Airtable base first, then a purpose-built platform capable of "sovereign contact management" — sharing role signals and running double opt-in introductions without ever releasing underlying contact data to a central database.

This note is an assessment of where Rizom fits that protocol.

## The core fit

The Federation's protocol is built around one requirement it states repeatedly: each steward keeps sovereignty over what they've built, while the network gets a shared view. That requirement is why the doc splits into two phases — a central base can hold events and job posts, but it can't hold steward-private trust scores, unreleased contacts, or deals shared under founder consent. Phase 2 isn't a feature upgrade; it's the point where the central model runs out.

A brain-per-steward architecture is that shape from the start. Each org's registry lives in their own brain — their own markdown, their own repo, their own control. The federation view is composed by those brains talking to each other over signed peer connections, with visibility set per record: `public`, `shared` (federation peers only), or `restricted` (never leaves the owning brain). So the same system carries a public membership directory, a federation-only deal record, and a trust score that no one else ever sees. The sensitivity gradient the doc walks through is handled by one property on each record instead of by deciding which platform to put it in. There's no migration between phases because there's no architectural break.

## How the protocol maps

Their minimum-viable records are already schemas. Founder, Funder, Network Steward, Influencer, SME, Coherence Facilitator — with their field lists — become typed entity types validated at write time, so a Deal record missing a close date or a founder-consent flag doesn't silently enter the registry.

The Contact Signals table is the clearest case. The doc specifies "no actual contact data — stewards signal that they have a contact fitting a specific role and need profile." In a brain that isn't a discipline the steward has to maintain; the signal is a `shared` record and the contact is a `restricted` one, and the boundary is enforced by the system. Nobody can paste an email into the wrong column. Same for trust scores: `restricted`, invisible to the network, still fully usable by that steward's own agent when it ranks who to surface.

Introductions get durable memory — who originated, who passed it on, whether it progressed — which is exactly the originator chain and carry-eligibility documentation the deals section says has to be reliable or the whole system poisons. And the public face isn't a second build: the membership directory, the events listing, and the jobs board publish straight from the records stewards already maintain.

## The part that actually decides whether this survives

The doc names its own failure mode: "busy people will not maintain a system that requires significant effort," and "stale registries erode trust." Every shared-registry attempt dies there. Forms don't fix it — a form is still a thing you have to remember to go and fill in, on top of the work.

A brain captures from where the steward already is. Chat, email, conversation. You mention a deal in the channel and the record exists. It can run the two-quarter staleness check itself and nudge the owner rather than waiting for someone to notice on a call. And because the base is meant to *be* the agenda, the quarterly prep becomes generated rather than assembled — each steward's ten minutes writes itself.

It's also MCP-native, so a steward's own assistant queries their registry directly. "Who in my network fits this raise" becomes a question you ask, not a view you build.

## What's real today vs. what gets built

Running now: typed entities, the three-tier visibility model, signed brain-to-brain connections with peer trust, peer discovery, capture via chat and email, site publishing from the same content graph, scheduled digests, MCP.

To be built for the full protocol: cross-network role-signal matching, and the double opt-in flow as a packaged workflow. Both are additive on the substrate above — new capability on the same records, not a replatform.