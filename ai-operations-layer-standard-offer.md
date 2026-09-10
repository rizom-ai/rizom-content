---
title: AI operations layer — standard offer
visibility: shared
---
# AI operations layer — standard offer

What we sell to a small company that wants its recurring operations watched and its routine client communication drafted by AI, without hiring an operations manager and a relationship manager first. Delivered as an instance of our platform with the company's own rules and integration on top, then either hosted by us or handed over.

Set 2026-09-11 from the first proposal of this shape. Prices below are list; see the launch-client policy at the end.

## What it is

A separate system next to the client's platform, connected through a small contract: events and statuses go in, escalations and overviews come out. Three reasons for this being the shape:

- The client's developer keeps their platform and their pace; none of our code lives inside theirs.
- The layer is built and tested against test data before the client's platform is finished, so delivery does not wait on them.
- Acceptance criteria attach to the contract and are testable — a rule fires or it does not — rather than to how something feels.

Three roles, delivered in this order:

1. **Operations watcher.** Continuous checks on clients and projects — deadlines, open actions, incidents, SLA drift, payment status. Deterministic rules decide what is wrong; the model explains and prioritises. A daily overview to the owner, escalations to named people according to a decision table, and a log of everything the layer saw and did.
2. **Relationship manager in drafting mode.** Intake of client questions, status requests and change requests by e-mail, with full client context. Every reply is prepared as a draft for a human operator, and the layer measures per message type how often the operator changes it. Complaints, price, scope and other predefined situations escalate to the operator on rules, never on the model's own judgment.
3. **Technical assistant and autonomy gates.** Log analysis, incident classification and documentation for the client's developer, who stays technically accountable. Plus the mechanism by which the relationship manager may send a message type unaided once its measured correction rate is under an agreed threshold — and drops back to drafting automatically if the threshold is exceeded.

## Milestones and list prices

| | Duration | List price |
|---|---|---|
| 1. Architecture and acceptance criteria | 2 weeks | €5.000 |
| 2. Operations watcher | 3 weeks | €15.500 |
| 3. Relationship manager, drafting mode, with measurement | 3 weeks | €13.500 |
| 4. Technical assistant and autonomy gates | 2 weeks | €8.000 |
| **Total** | **~10 weeks** | **€42.000** |

Each milestone is funded into escrow before work starts and released on acceptance. Milestones stand alone: the client can stop or pause after any of them, and what exists at that point works and is theirs.

**Milestone 1 is accepted when** the platform contract is written as a schema, the escalation rules as a decision table, and the acceptance criteria for milestones 2–4 as concrete pass/fail conditions, and the client signs off. It produces the acceptance criteria for everything after it.

**Milestones 2–4 are accepted when** their rules demonstrably fire on a test set, escalations arrive within the agreed time, the overview or drafts appear on schedule, and the measurement is visible. No milestone is accepted on a qualitative judgment of output.

## Assumptions the prices rest on

- The client's platform exposes events and statuses through an API, not exports.
- E-mail is the first client channel; other channels are a separate milestone.
- At most 25 active clients at go-live.
- The client's developer delivers their side of the contract per milestone on an agreed date.
- Language models via API; running models locally is a separate decision with its own cost.

A broken assumption re-prices only the affected milestone, before it is funded.

## After delivery

Two options. We host and operate the layer at **€950 per month**, model usage passed through at cost. Or we hand it over to the client's developer to run themselves; the code they receive is open source, so there is no lock-in, and support is then hourly.

Model usage at 25 clients: roughly €150–400 per month depending on message volume, made concrete in milestone 1.

## Launch-client policy

The first client for this offer pays a launch-client price of 15–20 % below list, in exchange for serving as a reference after milestone 2 goes live and allowing the engagement to be written up as a case without confidential detail. The concession is a fixed policy for whoever is first; it is not negotiated per client and it does not move the list price.

## What this offer does not do

It does not quote a build price before milestone 1 exists. It does not accept "feels natural and human" or any other untestable criterion. It does not put our code inside the client's platform. It does not name a fixed price for a scope that has not been written down.
