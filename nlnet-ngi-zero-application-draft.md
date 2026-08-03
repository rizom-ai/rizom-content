# NLnet / NGI Zero — Application draft

*Target: NGI Zero Commons Fund / Open Internet Stack call (reopens ~Sept 2026). Non-dilutive, EUR 5k–50k, milestone-based. Apply as an individual or as Rizom B.V. — no stichting required.*

**Requested amount:** EUR 50,000

### Project name
Rizom Brains — portable, self-hostable living memory for organisations, on the AT Protocol.

### Website / source
- rizom.ai — [repo link] — [docs link]
- Licence: AGPL-3.0 (runtime) + Apache-2.0 (SDK & protocol contracts)

### Abstract — what are you going to make?
Organisations lose their working memory constantly: the context behind decisions, the reasoning of a project, the expertise that walks out when a person leaves. The tools that promise to fix this are closed SaaS silos — your knowledge becomes someone else's asset, locked to their platform and their AI. **Rizom Brains** is open-source infrastructure for a "brain": a living, queryable memory an organisation fully owns. Data lives as **portable markdown** on infrastructure the organisation controls, identity and federation run on the **AT Protocol**, and the whole runtime is **AGPL** so no one can capture it into a proprietary fork. The grant hardens what makes ownership and portability real and verifiable: clean self-hosting, a documented data-portability guarantee, and AT Protocol-native federation between independent brains.

### Have you been involved in relevant projects before?
[Founder background — prior open-source / ecosystem / knowledge-infrastructure work. Rizom B.V. is building this in the open; the platform is AGPL, deliberately, to keep it a commons. Live pilots across an AI-ecosystem programme, cultural institutions, and regenerative-farming cooperatives validate the approach across domains.]

### What will the budget be used for? (milestones)
- M1 Self-host packaging — one-command self-hosting (container + docs), no Rizom dependency. EUR 10,000
- M2 Portability guarantee — tested export of the whole brain as portable markdown + a "deed of ownership"; import into a fresh instance with zero loss. EUR 10,000
- M3 AT Protocol federation — brains as first-class ATProto actors: identity, lexicon, selective sharing between self-hosted brains. EUR 14,000
- M4 Open lexicon + SDK — publish/document the ai.rizom.brain.* lexicon and the Apache SDK. EUR 10,000
- M5 Docs & security pass — contributor docs, threat model, dependency/security review. EUR 6,000
- Total EUR 50,000

### Other funding sources
Rizom B.V. is founder-funded and pre-revenue. Early paid pilots part-fund the commercial practice on top of the platform; the platform itself has no external funding. This grant funds the open, non-commercial infrastructure directly.

### Compare to existing / historical efforts
- Proprietary knowledge SaaS (Notion AI, Glean, Mem): closed, hosted, your data and the AI over it are the vendor's. Rizom inverts this — you own the data and can leave with all of it.
- Self-hosted wikis / PKM (Obsidian, Logseq): great local ownership, but no shared organisational memory, no federation, no AI-native retrieval. Rizom adds the living layer and open federation.
- Fediverse / ATProto ecosystem: mostly social. Rizom applies the same open-protocol, data-sovereignty principles to organisational knowledge.
What's new: verifiable data ownership (portable markdown + export deed), organisational living memory, and AT Protocol federation between self-hosted brains — combined and open.

### Significant technical challenges
Provable portability (round-trip export/import, zero semantic loss); mapping organisational-knowledge objects onto AT Protocol lexicons; selective consent-based federation without a central broker; keeping self-hosting one-command despite AI/embedding dependencies.

### Ecosystem & engagement
Built in the open (AGPL/Apache, public repo, DCO). Real-world pilots across three domains feed requirements and case studies back into the open platform. A forthcoming certified-partner network (open methodology, public registry) lets independent practitioners deploy and extend the open platform without lock-in — spreading the open protocol, not a proprietary product.

### Notes before submitting
- Fill the bracketed founder background + repo/docs links.
- The platform is already AGPL in the repo — lead with that; the open, self-hostable, capture-proof story is what NGI funds.