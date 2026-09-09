# The Brain | User-Facing Capability Menu

**Purpose:** a menu of things the Brain lets people *do*. Pick items, combine them into a solution for a specific customer situation. Every item is tagged by how mature it is and backed by a real technical feature with a source document.

---

## How to read this

- **Part A: The menu.** Every user-facing capability, one row each, grouped by theme.
- **Part B: Solutions.** Pre-combined "meals": which menu items solve which customer situation, and whether we can deliver it *today*.
- **Part C: Planned.** Things that are not in the product yet. Never demo these as
  working. Useful for "where this is going" only.

### Maturity tags

| Tag | Meaning | How to talk about it |
| --- | --- | --- |
| **Production** | Proven in real, continuous production use, and on the default path. | Demo freely, safe to promise. |
| **Shipped** | In the released product and working, but with one or more of: landed recently, off by default, needs an outside account, or known rough edges. | Demo freely, promise the capability, be measured about scale and edges. |
| **Pilot** | Runs, but we are still validating it with real users — a POC or prototype internally. | Demo with a caveat, do not promise outcomes. |
| **Planned** | Not in the product. Roadmap only. | Do not demo or promise outcomes now. |

**Production vs Shipped:** Production means we run it ourselves, daily, on live brains, and a new customer can lean on it. Shipped means it is in the box and works, but plan to validate it for the specific customer: it may be newer, optional, or dependent on an
outside service.

---

## Part A: The menu

### 1. Capture and retain what people know

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A1 | Knowledge kept as plain files they own | Keep what the organisation knows in portable text files, not locked inside a tool they might lose access to | Schema-validated markdown entities stored in `brain-data/` | `docs/entity-types-reference.md`, `docs/content-management.md` | Production |
| A2 | Edit anywhere, full history | Write in any editor (e.g. VS Code, Obsidian, plain text), with every change versioned and recoverable | `directory-sync` with git history and remote sync (optional Obsidian template helper) | `docs/directory-sync-git.md`, `docs/content-management.md` | Production |
| A3 | Capture from a conversation | Sit with someone, talk through what they know, and have the brain turn that conversation into saved, searchable notes | Chat interfaces + `system_create` (text / URL / upload / prior response) | `docs/feature-overview.md`, `docs/content-management.md` | Production (one person capturing) · Pilot (several people, with a who-added-what record) |
| A4 | Capture links and documents | Save an article, PDF or file and have it summarised and indexed | `link` capture + `document` / `image` entities with generation jobs | `docs/entity-types-reference.md`, `docs/content-management.md` | Production |
| A5 | Automatic topic clustering | See what subjects the knowledge covers without anyone tagging anything | Derived `topic` projections over the content graph | `docs/architecture-overview.md` (projection graph), `docs/entity-types-reference.md` | Shipped (still being refined) |
| A6 | Strengths-and-gaps summary (SWOT analysis) | Turn what the brain knows about a person or team into a structured strengths-and-gaps summary | `@brains/assessment` `swot` entity | `docs/feature-overview.md` ("optional product capabilities") | Shipped (opt-in) |
| A7 | A visual map of what the brain knows | See at a glance which subjects the brain has depth in, and where it is thin | `@brains/topics` knowledge-map, rendered on the site and dashboard | `docs/roadmap.md`, `.changeset/knowledge-map-legibility.md` | Shipped (still being polished) |
| A8 | Edit content in a browser | Add and change notes, pages, posts and profile details through web forms (no files, no markdown) | `cms` plugin (web bundle) — browser authoring for configured entity types | `docs/content-management.md` ("CMS"), `plugins/cms/` | Shipped (actively evolving) |
| A9 | See what the brain holds at a glance | Open a dashboard with entity counts and plugin summary widgets | `dashboard` plugin (web bundle) | `docs/feature-overview.md` ("Dashboard operator views"), `plugins/dashboard/` | Shipped (widget set still growing) |

### 2. Find answers and ask questions

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A10 | Natural-language search | Ask a question in plain words and get an answer drawn from everything captured | SQLite index + embeddings + semantic search (`system_search`) | `docs/feature-overview.md`, `docs/architecture-overview.md` | Production |
| A11 | Use it from an existing AI assistant | Connect the knowledge base to any AI assistant that supports MCP (the open standard for this, e.g. Claude Desktop, Cursor, Copilot), and ask it questions from the tool they already use | MCP server over stdio and HTTP | `README.md`, `docs/interface-setup.md`, `docs/agent-discovery.md` | Production |
| A12 | Ask it in the browser | Ask the brain questions from a web page and get answers that cite their sources | Bundled web chat (`/chat`) with sessions, uploads, confirmations, progress | `docs/feature-overview.md`, `interfaces/web-chat/` | Production |
| A13 | Ask it in Slack or Discord | Query and capture knowledge inside the chat tool they already use (Slack or Discord) | `chat` bundle — Discord + Slack via one Chat SDK | `docs/feature-overview.md`, `docs/interface-setup.md` | Production (Slack is one workspace per brain) |

### 3. Onboarding and process continuity

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A14 | Guided procedures | Write a repeatable procedure down once (say, how you onboard a new hire) and have the brain walk anyone through it step by step | `@brains/playbooks` (chat-native playbook runs) | `docs/feature-overview.md` (automation bundle), `plugins/playbooks/` | Shipped (engine works; only onboarding walkthroughs ship built-in; custom procedures are an advanced path) |
| A15 | Guided first-run setup | Be guided through initial configuration on first run | `@brains/onboarding` activation plugin | `docs/feature-overview.md` | Shipped (part of the automation add-on, not in every default setup) |
| A16 | A single "needs your attention" list | Get one screen for everything that needs a human decision, instead of hunting across the system | `@brains/unified-inbox` aggregating source-owned items, with `shell/recurring-checks` for scheduled alerts. Covers flagged incoming mail, newly discovered peer brains, and system-health warnings, plus a daily email digest | `plugins/unified-inbox/README.md`, `docs/roadmap.md` | Shipped (landed recently) |
| A17 | Inbound email triage | Have incoming email sorted into categories (opportunity, recruiting, work, admin, personal) and surfaced as items to deal with (the mailbox itself is left untouched) | `interfaces/email` (IMAP intake) + `@brains/email-workflows` derived triage | `docs/feature-overview.md`, `plugins/email-workflows/README.md`, `docs/roadmap.md` | Shipped (opt-in) |

### 4. Publishing and external presence

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A18 | Website from the same content | Publish an internal handbook or a public site straight from the knowledge base, so the two never drift apart | `site` bundle — static site builder + reusable themes | `docs/feature-overview.md`, `docs/content-management.md` | Production |
| A19 | Draft posts, decks, portfolio | Turn rough notes into a written post, a slide deck, or a case study | `publishing` bundle — `blog`, `decks`, `portfolio`, `series` | `docs/entity-types-reference.md`, `docs/content-management.md` | Production |
| A20 | On-brand voice and visuals | Make everything generated sound and look consistent with their brand | `style-guide` entity (voice + visual direction) applied during generation | `docs/entity-types-reference.md` | Production (needs a well-written style guide) |
| A21 | Images, covers, PDFs, carousels | Produce cover images, share images, printable PDFs and PDF carousels on demand | `media` bundle + shared media renderer | `docs/feature-overview.md`, `docs/roadmap.md` | Production |
| A22 | Newsletter and subscribers | Draft, schedule and send a newsletter | `@brains/newsletter` (+ Buttondown) | `docs/entity-types-reference.md` | Shipped (needs a Buttondown account) |
| A23 | Social drafts | Generate social posts from existing material | `@brains/social-media` | `docs/entity-types-reference.md` | Shipped (publishing to each network needs a connected account) |
| A24 | Publishing pipeline | Queue, schedule and retry publication | `@brains/content-pipeline` | `docs/architecture-overview.md` | Shipped (scheduling and retries less exercised than direct publishing) |

### 5. Multiple people on one brain

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A25 | A separate identity per person | Give each person their own login, role and personal settings | `shell/auth-service` runtime auth database, multi-user boundaries, invitations | `shell/auth-service/README.md`, `docs/roadmap.md` | Shipped (multi-user landed recently, less mileage than the single-user path) |
| A26 | Passwordless login + admin console | Sign in with a passkey or OAuth, and manage people, invitations, peers and an audit trail from one console | `web` bundle — `auth-service`, `admin`, `account` | `docs/feature-overview.md`, `plugins/admin/` | Shipped (passkey login is proven; the people and invitations console is newer) |
| A27 | Access control per item and per action | Decide what is public, what is for trusted collaborators, and what is admin-only (separately for reading, creating, updating, deleting and publishing) | Visibility model (`public` / `shared` / `restricted`) + caller levels (Public / Trusted / Admin / Anchor) | `docs/feature-overview.md` ("Security and control") | Production |

### 6. Shared team memory

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A28 | Turn discussion into a record | Have a team conversation automatically distilled into a short summary, a list of decisions, and a list of action items the team can retrieve later | `conversation-memory` entities (`summary`, `decision`, `action-item`) with retrieval and dashboard widgets | `docs/entity-types-reference.md`, `docs/roadmap.md` | Shipped (the mechanism; sharing it across a team is A29–A31) |
| A29 | Make that memory shared | Switch that memory from private-to-each-person to shared-across-the-team | `team` bundle policy over `conversation-memory` | `docs/feature-overview.md` ("Team policy"), `docs/brain-model.md` | Pilot |
| A30 | Let teammates contribute, safely | Allow trusted colleagues to add notes, links, decisions and action items, with deleting and publishing still admin-only | `team` bundle trusted-collaborator entity permissions | `docs/brain-model.md`, `packages/brain-cli` bundle policy | Pilot |
| A31 | Keep who-said-what | Keep a record of which person contributed each item | Speaker-attribution first pass (actor / source metadata on messages) | `docs/roadmap.md` | Pilot (first pass: records who spoke; does not yet link one person across different channels) |
| A32 | Shared team documentation | Keep a section of team reference pages | `@brains/doc` (`docs`, added by the team recipe) | `docs/entity-types-reference.md` | Shipped (the team setup it is usually part of is still a pilot) |

### 7. Connecting brains to each other

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A33 | Query another organisation's brain | Query another organisation's Brain once both sides have approved the connection | A2A protocol + `discovered → approved → callable` lifecycle | `docs/agent-discovery.md` | Shipped (the brain-to-brain network is young; few real links yet) |
| A34 | Directory of connected brains | Keep a list of trusted outside brains and what each one is good at | `agent` + `skill` entities, reviewable second-order discovery | `docs/agent-discovery.md`, `docs/feature-overview.md` | Shipped (few real peer brains exist yet) |
| A35 | Identity-checked requests between brains | Have every request between brains cryptographically identity-checked and scoped to a permission level | RFC 9421 request signing, peer-trust grants, task-caller binding | `docs/roadmap.md`, `docs/agent-discovery.md` | Shipped (landed recently; lightly exercised in the field) |
| A36 | Be discoverable to other organisations | Make the brain findable on an open directory, so potential collaborators can discover what they know | `federation` bundle — `atproto`, `atproto-registry` | `docs/feature-overview.md`, `docs/agent-discovery.md`, `docs/plans/atproto-integration.md` | Pilot (the brain can publish itself; finding other brains is still a manual list) |
| A37 | A map of connected brains | See which other organisations' brains are closest to yours in subject matter | `@brains/agent-discovery` proximity-map widget (dashboard + site section) | `entities/agent-discovery/`, `.changeset/proximity-map-full-width.md` | Shipped (new visualisation, still being refined) |

### 8. Ownership and control

| # | Capability | So the customer can… | Technical feature behind it | Source | Maturity |
| --- | --- | --- | --- | --- | --- |
| A38 | Self-hosted on their own infrastructure | Run the knowledge base and the application on infrastructure they control, on a small low-cost server | Single Bun process, container + Kamal deployment | `docs/public-release/README.md`, `packages/brain-cli/docs/deployment-guide.md` | Production |
| A39 | Choose the text-AI provider | Run the brain's writing and answers on OpenAI, Anthropic or Google models, chosen in config with no code change | Model-name-based provider selection in `shell/ai-service`; one shared `AI_API_KEY`; search indexing always uses OpenAI | `README.md`, `shell/ai-service/` | Shipped (OpenAI is the exercised path; an OpenAI key is required either way) |
| A40 | Tune behaviour without code | Change how the brain writes and answers by editing a text file | `prompt` entities overriding generation templates | `docs/content-management.md` | Production |

---

## Part B: Solutions (menu items combined)

### Who we sell to

We target teams and organisations going through a **people change**, and we insert ourselves to solve the **knowledge loss and living-memory problems** that the change creates.

| Trigger | Code |
| --- | --- |
| **A key person is leaving**: resignation, retirement, promotion out of the role, a long sabbatical | **T1** |
| **A merger, acquisition or internal reorg**: knowledge boundaries move and context gets stranded | **T2** |
| **Rebuilding after layoffs**: rehiring into roles that were cut | **T3** |
| **Rapid hiring / scaling headcount** | **T4** |
| **Coverage gaps from leave**: parental, sick or sabbatical clusters | **T5** |
| **A function changes hands**: outsourcing, offshoring, or insourcing back from a vendor | **T6** |

Most of the knowledge at risk is scattered across tools like Confluence, Notion, Google Docs, SharePoint, wikis, chat history, and people's heads. The Brain's job is to become the one place it is captured, searchable and owned.

### Trigger coverage at a glance

| Solution | T1 leaving | T2 merger / reorg | T3 post-layoff | T4 fast hiring | T5 leave gaps | T6 function moves |
| --- | :---: | :---: | :---: | :---: | :---: | :---: |
| **S1** Departing-expert debrief | ✓ | | ✓ | | ✓ | |
| **S2** Living team memory | | ✓ | | ✓ | | ✓ |
| **S3** Onboarding accelerator | | | ✓ | ✓ | | ✓ |
| **S4** Coverage during leave | | | | | ✓ | |
| **S5** Merger knowledge consolidation | | ✓ | | | | ✓ |
| **S6** External-facing continuity | ✓ | | | | | |
| **S7** Org-wide self-service Q&A | | | ✓ | ✓ | | |

### Detail

Menu items are listed in setup-to-use order: what you put in first, then what people do
with it, then how it is controlled. For example, S1 starts with A1–A4 and A8 (the files,
the capture and the editing that fill the brain), moves through A5 and A7 (organising that
happens automatically), then A10–A12 (the ways people ask it things), and ends with A27
(who is allowed to see what).

| Solution | Knowledge-loss pain it solves | Menu items it combines | Can we deliver it today? |
| --- | --- | --- | --- |
| **S1: Departing-expert debrief** | Undocumented context walks out the door; "only they knew how to do this" | A1, A2, A3, A4, A8, A5, A7, A10, A11, A12, A27 | **Yes** as one brain the team then queries. If several named people must each contribute under their own login, with a record of who added what, that part is **Pilot** (A25, A29–A31). |
| **S2: Living team memory** | Months later the team argues the same decision again, because no one recorded why it was made | A25, A13, A28, A29, A31, A32, A30, A10, A12 | **Yes, with a pilot caveat.** The shared, attributed memory (A29–A31) is still being validated. Demo it; frame outcomes as "what teams are starting to see," not a guarantee. |
| **S3: Onboarding accelerator** | New hires ramp slowly; senior staff are constantly interrupted with the same questions | A8, A32, A18, A14, A7, A10, A11, A12, A13 | **Yes.** Guided procedures (A14) are Shipped and still improving: present them as a strengthening capability. |
| **S4: Coverage during leave** | Person-dependent processes; nobody else knows the steps | A3, A8, A14, A32, A16, A10, A12, A13 | **Yes.** |
| **S5: Merger knowledge consolidation** | Two organisations, two knowledge bases, no shared search or memory | A1, A2, A8, A25, A5, A7, A10, A12, A13, A18, A27, plus A33 / A34 if the two sides keep separate brains | **Partly.** Clean if both sides' content can be brought in as text. Direct import from other tools is **Planned** (C10). |
| **S6: External-facing continuity** | A public-facing expert leaves; clients and prospects lose the resource | A1, A3, A20, A19, A21, A18, A12, A11, A40 | **Yes.** This is the most mature area (personal / professional publishing, live in production). |
| **S7: Org-wide self-service Q&A** | The same questions asked over and over across a growing org | A25, A5, A10, A11, A12, A13, A27 | **Partly.** Asking in chat works now. The purpose-built "ask the team" experience is **Planned** (C1). |

---

## Part C: Planned

None of this is in the product today. The Status column says how far along each item is.
Do not demo or promise; "on our roadmap" only.

### Status

| Status | Meaning |
| --- | --- |
| **Planned** | On the roadmap with a written plan. Intended to be built. |
| **Parked** | A plan exists, but it is deliberately on hold until a customer needs it. |
| **Partly there** | Part of it already ships; the rest is planned. |
| **Shelved** | Built or prototyped once, then deliberately set aside. Could return with demand. |

| # | Capability | What it would unlock | Source | Status |
| --- | --- | --- | --- | --- |
| C1 | "Ask the team": purpose-built Q&A | A polished self-service answer experience for a whole org | `docs/plans/team-posture-capabilities.md` | Parked |
| C2 | Meeting notes from transcripts | Structured notes and action items straight from a recording | `docs/plans/team-posture-capabilities.md` | Parked |
| C3 | Structured decision records | A deliberate decision register (context, options weighed, decision, consequences) that people author and curate. Different from A28, where the brain only auto-notices decisions mentioned in chat | `docs/plans/team-posture-capabilities.md` | Parked |
| C4 | Weekly team digest | A narrative of what the team produced and decided over the week. Different from A16's daily list of what is currently open | `docs/plans/team-posture-capabilities.md` | Parked |
| C5 | Opportunity / lead prioritisation | Capture and rank sales opportunities into a focus list | `docs/roadmap.md`, `docs/plans/bd-priority-engine.md` | Planned (in development) |
| C6 | Inbound lead qualification from email | Turn qualifying emails into ranked leads that consolidate a whole thread | `docs/plans/lead-management.md` | Planned |
| C7 | Reply to email from the brain | The brain drafts and sends email replies | `plugins/email-workflows/README.md`, `docs/roadmap.md` | Shelved |
| C8 | Live web search | The brain searches the live web when its own knowledge falls short | `docs/plans/web-search-tool.md` | Planned |
| C9 | Interactive knowledge graph | A richer map of how individual pieces of knowledge connect. A topic-level visual map already exists (A7) | `docs/plans/team-posture-capabilities.md`, `docs/plans/topic-extraction-and-reconciliation.md` | Partly there |
| C10 | Direct import from other knowledge tools | Pull existing knowledge in from Notion, HackMD and similar without export steps. Notion and HackMD had early prototypes; other tools would be new work | `docs/plans/team-posture-capabilities.md` | Shelved |
| C11 | Live collaborative editing | Several people editing the same page at once | `docs/plans/team-posture-capabilities.md` | Parked |
| C12 | Installable console app (PWA) | The admin console as an installable desktop / mobile app | `docs/plans/operator-console-pwa.md` | Parked |
| C13 | Automatic discovery of peer brains | The brain finds relevant peer brains on its own, instead of being pointed at them | `docs/plans/atproto-integration.md`, `docs/agent-discovery.md` | Partly there |
| C14 | Run all AI on your own hardware | Fully offline / air-gapped operation (today search indexing always calls OpenAI) | `docs/plans/embedding-service.md` | Parked |

---

## Extra notes

- **Lead with the proven core:** capture (A1–A4), search and ask (A10–A13), publish from the same content (A18–A21), self-hosted (A38). All Production.
- **The team story is real but young.** Multiple people on one brain (A25–A27) is Shipped. Turning conversation into records (A28) is Shipped as a mechanism. Making it a *shared, attributed team memory* (A29–A32) is a Pilot.
- **"Bring your own AI provider" has limits.** True for the text AI (OpenAI, Anthropic, Google). But search indexing always calls OpenAI today, and there is no fully-offline mode. Do not promise air-gapped.
- **One product, not a range.** The Brain is not sold as Basic / Pro / Enterprise editions with different code. It is one system; capabilities are switched on per customer. Going from "just me" to "the whole team" is a configuration change: not a new licence, a rebuild, or a data migration.
