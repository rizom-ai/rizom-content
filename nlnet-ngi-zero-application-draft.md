---
visibility: shared
---
# NLnet / Restack — Application draft

*Target: NLnet Restack (Open Internet Stack), the successor to the NGI Zero Commons Fund, which closed 1 June 2026. Call open since 3 September 2026; deadline 3 November 2026, 12:00 CET (noon). EUR 5k–50k, milestone-based, non-dilutive. Assessment is a batch after the deadline; the last complete version submitted before it is the one assessed. Restack excludes AI-related projects, so the proposal is framed as trust infrastructure for records — automated assistants are a consumer of that layer, not its subject. Applicant: Rizom Foundation (Stichting Rizom) per the founding plan; Rizom B.V. if the deed is not signed before filing. Retargeted 2026-09-09; supersedes the NGI Zero drafts.*

**Requested amount:** EUR 50,000

### Project name
Rizom Brains — owned, portable organisational memory with verifiable provenance

### Website / source
- rizom.ai — https://github.com/rizom-ai/brains — [docs link]
- Licence: AGPL-3.0 (runtime) + Apache-2.0 (SDK & protocol contracts)

### Abstract — what are you going to make?
Organisations keep their working memory — the context behind decisions, the reasoning of a project, the expertise that leaves with people — in closed, hosted services where the knowledge becomes the vendor's asset. Rizom Brains is the open alternative: self-hosted infrastructure for an organisation's memory, stored as plain markdown on infrastructure the organisation controls, AGPL so it cannot be captured into a proprietary fork. It runs in production today, with pilots in an AI-ecosystem programme, cultural institutions and regenerative-farming cooperatives.

This grant makes the ownership verifiable and adds the trust layer such a memory needs once anything derives from it — a digest, a summary, an answer, a published page. First the substrate: self-hosting in one command with no dependency on Rizom, and a tested round-trip export/import of a whole brain with zero loss. Then four record-level mechanisms, published as open contracts: (1) provenance — every derived record carries signed references to the source records it drew on, scoped to what the reader may see; (2) declared standing — any actor that publishes claims into the memory, whether a person, a service or an automated assistant, declares its access scope, its bounded authority and its accountable principal; (3) contestability — a contradiction can be attached to any claim, so the memory holds the dispute rather than the last fluent summary; (4) refusal as a first-class result: "not mine to answer" distinct from failure. Records carry AT Protocol identities and are described by open lexicons, so references verify across independently hosted instances without a central broker.

### Have you been involved in relevant projects before?
I am the maintainer of Rizom Brains (about 5,700 commits over fifteen months; my own website, newsletter and email workflows run on it, alongside the three pilot domains above). Before it: Offcourse, eleven years of open-source learning infrastructure; Lefthoek, where I built an AI "virtual team member" for organisational work; Public Badges, a digital trust framework deployed across Dutch media, cultural, education and healthcare institutions, through my work for PublicSpaces; and a decade teaching philosophy at the University of Amsterdam, where situated knowledge and institutional memory were my subject.

### What will the budget be used for? (milestones)
- M1 Owned substrate — one-command self-hosting (container + docs, no Rizom dependency) and a tested round-trip export/import of a whole brain with zero loss, including non-public entities. EUR 12,000
- M2 Provenance — signed, visibility-scoped references from every derived record to the source records it drew on; a verifier that checks a claim against the cited records. EUR 10,000
- M3 Declared standing — a standing record for every publishing actor: access scope, bounded authority, accountable principal; enforced at write time and published on the actor's card. EUR 9,000
- M4 Contestability and refusal — a contradiction record attachable to any claim and surfaced beside it in retrieval; "not mine to answer" as a distinct result; tooling to file and review contestations. EUR 10,000
- M5 Publication, interop, security — the contracts published as versioned open lexicons with an Apache SDK; interop tests against an independent implementation; cross-instance trust levels; threat model and dependency review. EUR 9,000
- Total EUR 50,000

### Other funding sources
The platform has no external funding. Rizom B.V. runs a founder-funded, pre-revenue practice on top of it; early paid pilots part-fund that practice, not the open platform. [Foundation as applicant: the foundation holds the platform IP and marks; the B.V. holds a licence-back and does not receive this grant.] A separate application, "The Machine Did It" — a year of working with agents with every decision public — is pending at the Stimuleringsfonds Creatieve Industrie; it funds practice and publication, not this infrastructure. This grant funds the open, non-commercial platform work directly.

### Compare to existing / historical efforts
- Proprietary knowledge SaaS (Notion AI, Glean, Mem): the knowledge and everything derived from it are the vendor's; nothing can be traced, bounded or contested, and you cannot leave with it.
- Self-hosted PKM (Obsidian, Logseq): ownership of your own files, but no shared organisational memory and no provenance or contestation on what is derived from them.
- Content credentials (C2PA): provenance for media files. This is provenance for claims over organisational knowledge, resolving to records the reader is allowed to see.
- Automation and agent protocols (MCP, A2A): transport for context and capabilities; nothing about what an actor speaks from, what it may assert, who answers for it, or how to contradict it. This project supplies that layer beneath them.

What's new: provenance, standing, contestation and refusal as open contracts, on memory the organisation owns and can leave with it.

### Significant technical challenges
- Visibility-scoped provenance: a citation must be verifiable by a reader without leaking records they may not see. Entity reads in the platform fail closed to public-only, and the export pipeline has already exhibited the failure mode this creates — non-public updates silently skipped, no error, clean git tree. Provenance has to be designed so that class of failure cannot hide.
- Signing across instances: references from one instance to records held by another, key rotation, and verification without a central broker.
- Contestation semantics: who may contradict, how disputes rank in retrieval without becoming noise, and how a derived record behaves when a cited source is contested.
- Refusal distinguishable from failure and from evasion: a bounded-authority result that clients and other instances can act on.
- Keeping self-hosting one-command despite embedding and model dependencies.

### Ecosystem & engagement
Built in the open (AGPL/Apache, public repo, DCO), with the contracts served from a public registry with validation tools. Three live pilot domains feed real cases of organisations deriving from and publishing out of their own memory. Interop is a deliverable, not a hope: M5 tests against an independent implementation so provenance and standing are usable by software that does not run Rizom. A certified-partner network (open methodology, public registry) lets independent practitioners deploy and extend the platform without lock-in.

### Notes before submitting
- Scope check first: ask at the NLnet office hour whether a provenance/contestation layer for organisational records is in Restack scope when automated assistants are one consumer of it.
- Confirm applicant: foundation requires the notarial deed signed before filing; otherwise file as Rizom B.V. and note the planned transfer.
- Fill the docs link; repo link is public.
- File a complete version early as a floor; the last complete version before 3 November 12:00 CET is the one assessed.
