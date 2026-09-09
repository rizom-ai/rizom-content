---
visibility: shared
---
# NLnet / NGI Zero — Application draft

*Target: NGI Zero Commons Fund / Open Internet Stack call, window 3 September – 3 November 2026. Non-dilutive, EUR 5k–50k, milestone-based. Applicant: Rizom Foundation (Stichting Rizom) per the founding plan; Rizom B.V. if the deed is not signed before filing. Reframed 2026-09-09 around situated agents; supersedes the portability-first draft of 2026-08-03.*

**Requested amount:** EUR 50,000

### Project name
Rizom Brains — accountable AI agents on memory the organisation owns

### Website / source
- rizom.ai — https://github.com/rizom-ai/brains — [docs link]
- Licence: AGPL-3.0 (runtime) + Apache-2.0 (SDK & protocol contracts)

### Abstract — what are you going to make?
Rizom Brains is open-source, self-hosted infrastructure for an organisation's working memory and the AI agents that work from it. The memory is plain markdown on infrastructure the organisation controls; the agents answer questions, draft decisions and increasingly act on that memory. It runs in production today, with pilots in an AI-ecosystem programme, cultural institutions and regenerative-farming cooperatives.

What this grant builds is the part no agent platform has: accountability. An agent's answer today does not say which records it was drawn from, what the agent was allowed to see, what it may assert on its own authority versus merely relay, who is answerable for it, or how a person contradicts it. The result is that partial, institutionally produced knowledge appears as impersonal intelligence, and organisations adopt it because it is fluent, not because it is trustworthy.

The project adds four things to the platform and publishes them as open contracts: (1) declared standing — an agent names its access scope, its bounded authority and its accountable principal; (2) provenance — every answer carries signed references to the records it drew on, scoped to what the reader may see; (3) contestability — a contradiction can be attached to any claim, so the memory holds the dispute rather than the last fluent summary; (4) refusal as a first-class result rather than a failure. Underneath, the memory itself is made verifiably owned: self-hosted in one command and exportable in full. Records carry AT Protocol identities and are described by open lexicons, so references verify across independently hosted brains without a central broker.

### Have you been involved in relevant projects before?
I am the maintainer of Rizom Brains (about 5,700 commits over fifteen months; my own website, newsletter and email workflows run on it, alongside the three pilot domains above). Before it: Offcourse, eleven years of open-source learning infrastructure; Lefthoek, where I built an AI "virtual team member" for organisational work; Public Badges, a digital trust framework deployed across Dutch media, cultural, education and healthcare institutions, through my work for PublicSpaces; and a decade teaching philosophy at the University of Amsterdam, where situated knowledge and institutional memory were my subject.

### What will the budget be used for? (milestones)
- M1 Owned substrate — one-command self-hosting (container + docs, no Rizom dependency) and a tested round-trip export/import of a whole brain with zero loss, including non-public entities. EUR 12,000
- M2 Declared standing — a standing record for every agent: access scope, bounded authority, accountable principal; enforced by the runtime and published on the agent card. EUR 9,000
- M3 Provenance — signed references from every agent answer to the records it drew on, scoped to what the reader may see; a verifier that checks a claim against the cited records. EUR 10,000
- M4 Contestability and refusal — a contradiction record attachable to any claim and surfaced beside it in retrieval; "not mine to answer" as a distinct result; tooling to file and review contestations. EUR 10,000
- M5 Publication, interop, security — the contracts published as versioned open lexicons with an Apache SDK; interop tests against an independent agent implementation; cross-agent trust levels; threat model and dependency review. EUR 9,000
- Total EUR 50,000

### Other funding sources
The platform has no external funding. Rizom B.V. runs a founder-funded, pre-revenue practice on top of it; early paid pilots part-fund that practice, not the open platform. [Foundation as applicant: the foundation holds the platform IP and marks; the B.V. holds a licence-back and does not receive this grant.] A separate application, "The Machine Did It" — a year of working with agents with every decision public — is pending at the Stimuleringsfonds Creatieve Industrie; it funds practice and publication, not this infrastructure. This grant funds the open, non-commercial platform work directly.

### Compare to existing / historical efforts
- Proprietary knowledge SaaS (Notion AI, Glean, Mem): fluent agents over your knowledge, but the knowledge and the agent are the vendor's, and nothing an agent says can be traced, bounded or contested.
- Agent frameworks and protocols (A2A, MCP, orchestration libraries): they describe what an agent can do and how context reaches it. None say what an agent speaks from, what it may assert, who answers for it, or how to contradict it. This project adds that layer on top of them.
- Self-hosted PKM (Obsidian, Logseq): ownership of your own files, but no shared organisational memory and no accountable agent layer.
- Content credentials (C2PA): provenance for media files. This is provenance for claims over organisational knowledge, resolving to records the reader is allowed to see.

What's new: standing, provenance, contestation and refusal as open contracts, on memory the organisation owns and can leave with.

### Significant technical challenges
- Visibility-scoped provenance: a citation must be verifiable by a reader without leaking records they may not see. Entity reads in the platform fail closed to public-only, and the export pipeline has already exhibited the failure mode this creates — non-public updates silently skipped, no error, clean git tree. Provenance has to be designed so that class of failure cannot hide.
- Signing across instances: references from one brain's agent to records held by another, key rotation, and verification without a central broker.
- Contestation semantics: who may contradict, how disputes rank in retrieval without becoming noise, and how an agent answers when a cited record is contested.
- Refusal distinguishable from failure and from evasion: a bounded-authority result that clients and other agents can act on.
- Keeping self-hosting one-command despite embedding and model dependencies.

### Ecosystem & engagement
Built in the open (AGPL/Apache, public repo, DCO), with the contracts served from a public registry with validation tools. Three live pilot domains feed real cases of agents answering on institutional knowledge. Interop is a deliverable, not a hope: M5 tests against an independent agent implementation so standing and provenance are usable by agents that do not run Rizom. A certified-partner network (open methodology, public registry) lets independent practitioners deploy and extend the platform without lock-in.

### Notes before submitting
- Confirm applicant: foundation requires the notarial deed signed before filing; otherwise file as Rizom B.V. and note the planned transfer.
- Fill the docs link; repo link is public.
- Window closes 3 November 2026.
