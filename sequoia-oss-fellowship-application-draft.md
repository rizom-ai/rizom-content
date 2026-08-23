---
visibility: shared
---
# Sequoia OSS Fellowship — Application draft

*Target: Sequoia Open Source Fellowship (sequoiacap.com/oss#apply, embedded Typeform P9damv8V). Equity-free, covers living expenses 6–12 months, 2–3 fellows/year, rolling review. No entity required. Drafted 2026-08-23.*

**1. Name**

Jan Hein Hoogstad

**2. LinkedIn Profile or Twitter**

https://www.linkedin.com/in/yeehaa/

**3. Link to project(s)?**

https://github.com/rizom-ai/brains

**4. Are you the primary maintainer?**

Yes

**5. Who else is on the core team behind your project?**

I'm the primary maintainer and write nearly all of the code. Around the project there is a small team that helps with adoption and support — onboarding new users, supporting deployments, and feeding real-world usage back into the roadmap — but the design and engineering of brains itself is my full-time work.

**6. How long have you been working on it?**

Full-time since May 2025. brains consolidates ideas I've been building toward for years across earlier systems (starting at Lefthoek), but the current codebase is a fresh, focused implementation.

**7. Are you already supported by any other organizations?**

No

**8. What would this funding enable you to accomplish?**

brains is a self-hosted AI knowledge agent built around files you own. Your notes, posts, and profile data live as plain markdown in a folder; the running brain can search and update that content, expose it to any MCP client (Claude, Cursor), and publish a static website from the same source. It's the open, self-hostable answer to a question a lot of people are asking right now: how do I get a personal AI assistant without handing my knowledge to a hosted platform?

The project works today. It's published on npm under @rizom, licensed AGPL/Apache, and runs in production beyond my own daily infrastructure — my website, newsletter, and email workflows all run on a brain, and live pilots are running across an AI-ecosystem programme, cultural institutions, and regenerative-farming cooperatives, with a small team helping new users deploy their own. But it's honestly pre-1.0: APIs still shift, and self-hosting it still assumes more patience than it should.

Twelve months of focused time would let me close that gap:

- **Ship a stable 1.0** — freeze the core APIs and entity model, with documented stability guarantees, so others can build on brains without chasing breaking changes.
- **Open the plugin surface** — brains is plugin-based internally (site publishing, email, newsletters, sync); 1.0 means third parties can write and share plugins against a stable contract.
- **Make self-hosting boring** — one-command install and upgrade paths, so adoption can grow beyond early adopters comfortable reading source.

The commercial-free structure of the fellowship fits deliberately: the core is and stays open source, no company formation or fundraising required, and the funding converts directly into maintainer time on the parts of the project that benefit everyone who runs it.

---

*Status: draft, not yet submitted. Q8 angle (ship 1.0 + adoption) confirmed 2026-08-23. Consistent with NLnet draft's "other funding" answer: founder-funded, pre-revenue, no committed external support.*

Related: nlnet-ngi-zero-application-draft
