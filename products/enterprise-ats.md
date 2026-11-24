# JobCloud Enterprise ATS (E-ATS)

> Source of truth for the Enterprise ATS product. Last sync: 24 Nov 2026.
> Sources: Confluence (LME space) page [JC ONE Enterprise ATS](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/86471311408/JC+ONE+Enterprise+ATS) and its 3 sub-pages; Gabriel's 5 consolidated "Enterprise ATS - ..." pages (LME space, 30 Oct 2026); PMH "Glossary & naming rules"; Jira (see §12); plus info from Lucille. Full page list in §13.
> Tags: **[Confluence]** = from the pages above, **[Jira]** = from Jira tickets, **[Lucille]** = stated by Lucille, **[Internal only]** = must not be shared with customers, **GAP** = not documented / open.
> When sources conflict, the most recent one wins and the conflict is noted.

---

## 1. Status and ownership

| Item | Value |
| --- | --- |
| Status | Live on production **[Lucille]**. Adapters deployed to prod (CDH-2004 closed 22 Oct 2026; CI-641 ats-adapter-candidly prod + CI-642 prod E2E done; epic CI-529 "ATSi Candidly integration" done) **[Jira]** |
| Operating mode | **Maintenance mode**: known limitations accepted, handled with workarounds/manual steps; new requests kept to a minimum, logged under MEPROJ-1464, not built by default **[Confluence]** |
| Signed customers | None yet (no contract signed) **[Lucille]** |
| Project lead (initial) | Simon Jansen (Head of Product); key decision maker on discovery idea DD-1096 "Candidly integration" (created 26 May 2026, initiative lead Lucille / Marko) **[Lucille] [Jira]** |
| Project lead (current) | Gabriel Stéphane Fabien Séjournant, LME team (PM; owner of epic MEPROJ-1464; consolidated documentation on 30 Oct 2026) **[Lucille] [Confluence]** |
| Product marketing / FAQ contact | Karima Selmi (sales material, FAQ, glossary; tag her in FAQ comments) **[Confluence]** |
| Vendor | WeAreCandidly ("Candidly", formerly Poplify), white-label ATS. Contacts: Aditya (tech lead), Aman (dev) **[Confluence]** |
| Engineering (ONE side) | Domain team (CDH tickets: Nikola Trajkovic, Milan Stojevski, William Lambert) for `marketplace-adapter-core-candidly`; Integration team (CI tickets: Edgars Zvirbulis, Claudiu Rotaru) for `ats-adapter-candidly` **[Jira]** |
| Other contacts | Benjamin Zutter (1Password, Microsoft security contact); Acquisition (Google verification); Inhouse Support / Cloud Engineering (environments, access) **[Confluence]** |
| Salesforce | Products added to the Salesforce catalogue (Sales doc page, 12 Nov). Note: on 30 Oct prices were "not yet in the official price list; Salesforce products WIP with Sales Ops" **[Confluence]** |

### Timeline

| Milestone | Status |
| --- | --- |
| Demo for Sales and CS | Suisse romande (WCH): done 26 Oct 2026. German-speaking CH (D-CH): planned **[Confluence]** |
| Demo for clients | Sales can already approach customers with existing content. No official demo account yet **[Confluence]** |
| Customer migration | TBD **[Confluence]** |
| Sales materials (30 Oct) | FR complete; DE and EN partly missing. DE factsheets and DE comparison uploaded 11 Nov; FR Product Guide 12 Nov **[Confluence]** |
| Third-party app verifications (30 Oct) | Microsoft and Zoom pending; Google and Slack in review (see §10) **[Confluence]** |
| Marketing materials ticket | LPMR-6 "Create Product Marketing Materials Enterprise ATS" done (17 Nov 2026) **[Jira]** |

---

## 2. What it is

- Applicant tracking system for **medium and large companies** (and staffing agencies, see factsheets). Recruiters and HR teams use it to collect applications, move candidates through hiring stages and track each candidate until hire. **[Confluence]**
- Part of **JobCloud ONE**. Accessed through a new left-menu item **"Enterprise ATS"**. **[Confluence]**
- Only customers already on JobCloud ONE are offered Enterprise ATS. **[Confluence]**
- Job ad **publication always happens in ONE**; Enterprise ATS handles candidate management and recruitment workflows after publication. **[Confluence]**
- White-label of **Candidly**; data hosted on **AWS, EU instance**. **[Confluence]**
- Hidden on mobile (CDH-2042) and hidden for Customer Service users (CDH-2021) in ONE. **[Jira]**

### Naming rules **[Confluence]** (PMH Glossary)

- EN: **Enterprise ATS**. FR: **« ATS d'entreprise »**. DE: to confirm (GAP).
- **Never say "Candidly"** to customers: internal name only.
- Use exact ONE permission names: **Applications Management** and **Job Ads Publication**.

### Positioning **[Confluence]**

- Promise: publish, track and hire from one platform (JobCloud ONE), no tool switching.
- Pillars: **Control** (stages, per-job rights), **Time saving** (automated messages, scheduling, stage triggers), **Collaboration** (evaluations, scorecards, sharing).
- Onboarding: self-service with the Product Guide; CS answers questions.

### Pricing **[Confluence]**

CHF, excl. VAT, **annual subscription, no setup fee**. One licence per legal entity.

| Segment | Per month | Per year |
| --- | --- | --- |
| ME (medium enterprise) | 200 | 2,400 |
| LE (large enterprise) | 500 | 6,000 |
| Staffing agency, up to 5 consultants (SA-5) | 200 | 2,400 |
| Staffing agency, 6 to 20 consultants | 350 | 4,200 |
| Staffing agency, 21+ consultants | 500 | 6,000 |

- Google Meet is extra: customer pays Cronofy directly (not invoiced by JobCloud).
- A DE pricing deck for staffing agencies exists as attachment (`Pricing_Staffing_Agencies_DE.pptx`, 2 Oct 2026), content not extracted.

### Basic ONE ATS vs Enterprise ATS **[Confluence]**

| Capability | Basic ONE | Enterprise ATS |
| --- | --- | --- |
| Pipeline | Fixed statuses | Customisable Kanban, default template per job ad |
| Access per job ad | No | Yes (Job Owner, Hiring Managers) |
| Scorecards / evaluations | No | Yes, 1 to 5 with sub-criteria |
| Templates and automation | Message templates (sent manually) **[Lucille]**; Confluence comparison said "Manual emails" | Customisable, stage triggers |
| Email (Gmail, Outlook) | No | Send and receive, history on profile |
| Calendar and self-scheduling | No | Yes (Cronofy) |
| Video | No | Zoom and Teams free; Google Meet paid via Cronofy |
| Offers and contracts | No | Yes |
| Reports | No | 5 reports, PDF/CSV |
| Comments, CV per candidate | Yes | Yes (comments cannot be edited) |
| Full candidate file download | Yes | **No** (decided, not built) |
| Screening questions | Yes | **No** |

### Sales claims: what can and cannot be said **[Confluence]**

| Claim | Status |
| --- | --- |
| One platform | True via sidebar SSO link; publication in ONE, candidates in Enterprise ATS |
| Per-job rights, self-service go-live | Confirmed |
| Kanban, scorecards, email, calendar, video, offers, reports | Native Candidly features |
| nLPD compliance, EU hosting | AWS EU confirmed; nLPD evidence still open |
| "Hosted in Switzerland" | **Do not use**: hosting is AWS EU |
| "Google Meet included" (EN factsheets) | **Wrong**: paid via Cronofy, to correct |
| "Onboarding session, live in 1 business day" | **Do not use**: onboarding is self-service |

### Target segments (from factsheets list) **[Confluence]**

- LE enterprises (large enterprises)
- ME enterprises (medium enterprises)
- Staffing agencies (SA): 5 consultants / 6 to 20 consultants / 21+ consultants

---

## 3. Account model: legal entity, workspaces, access

### Legal entity = one Enterprise ATS **[Confluence]**

- A company (**legal entity**) has **one single Enterprise ATS instance**. Enterprise ATS itself has no workspaces.
- Enabling Enterprise ATS on additional workspaces of the same legal entity does **not** create a new instance; it adds users to the same company.
- **Groups with several legal entities**: each legal entity needs its own Enterprise ATS and its own licence (e.g. 5 entities = 5 E-ATS = 5 licences). Recruiters working for several entities need access in each one.
- **[Internal only]** Licence is per legal entity because Candidly charges JobCloud per company.

### Workspaces in ONE **[Confluence]**

- ONE workspaces are still needed: they organise teams, manage user access and share/consume credits.
- Access to candidates is set **per job ad**, so a simple workspace structure is enough; no extra workspaces needed for complex customers.
- A workspace runs **either** the ONE basic ATS **or** Enterprise ATS, never both. Candidates live in only one ATS.
- Once a workspace has a job ad (draft or published), its ATS type **cannot be changed**.
- Existing ONE customers with job ads/candidates: set up a **new, empty** Enterprise ATS workspace next to the existing one.

### Sync of users from ONE **[Confluence]**

- Name, email and language come from ONE. Email cannot be changed in Enterprise ATS.
- User removed from their last E-ATS workspace -> removed from Enterprise ATS.
- Permission change in ONE -> role updated, or user added/removed in E-ATS accordingly.
- Last E-ATS workspace archived, or legal entity archived -> company closed in Enterprise ATS and all its users deleted.

### Lifecycle effects ONE -> Enterprise ATS **[Confluence]**

| ONE event | Result in Enterprise ATS |
| --- | --- |
| First workspace set to Enterprise ATS | Company created |
| Extra workspace | Users added, roles recomputed |
| User removed from last E-ATS workspace | User closed; pending interviews go to account owner or job owner |
| Last workspace or legal entity archived | Company closed: users, job ads and candidates **permanently deleted** |
| Make a user account owner | Remove and re-add ADMIN in ONE (latest updated Admin = account owner) |
| Job ad stopped or deleted in ONE | **Stays open** in E-ATS; must be closed manually (no archive endpoint in API V2) |

---

## 4. Roles and permissions

Permissions are driven entirely by ONE; nothing is set in Enterprise ATS. **[Confluence]**

| Permissions in ONE | Sees in Enterprise ATS | Can do |
| --- | --- | --- |
| **Admin** (in at least one workspace) | All job ads and candidates in every workspace of the legal entity | Everything, incl. all recruitment settings and integrations |
| Limited access with **Job Ads Publication + Applications Management** (both) | Job ads and candidates of own workspace(s) | Publish in ONE, manage candidates, assign Hiring Managers, see reports |
| Limited access with **Applications Management only** | Only job ads they are assigned to | Evaluate candidates (e.g. scorecards). Cannot publish |
| Limited access without either | Nothing; menu item not shown | - |

Technical mapping to Candidly roles **[Confluence]**: Admin -> `admin` (latest updated Admin = `account_owner`); Applications Management + Job Ads Publication -> `user`; Applications Management only -> `reviewer`; neither -> not synced. One Candidly user per user and legal entity; highest role wins (owner 4, admin 3, user 2, reviewer 1).

- Permission needed to see candidates: Admin or Applications Management.
- Troubleshooting: if a user cannot see the "Enterprise ATS" menu item, **check their workspace role first**.
- Users do **not** see the "View Applications" button on the ONE job listing page; they always go to "Enterprise ATS" > "Candidates".

### Job Owner and Hiring Manager **[Confluence]**

These are **not roles**; they are set per job ad in Enterprise ATS.

- **Job Owner** = person who published the job ad in ONE (Admin or Job Ads Publication user). For **feed** job ads: the Admin whose profile was modified most recently.
- Other colleagues with Applications Management can also be assigned as Job Owner or Hiring Manager.
- Multiple Job Owners and multiple Hiring Managers per job ad are possible.
- Job Owner assigns Hiring Managers (any E-ATS user of the legal entity, any workspace). Job Owner decides who sees the applicants of a job ad.
- Job Owner deleted from ONE -> their job ads go to the Admin whose role was most recently assigned/updated. Hiring Managers unchanged.

---

## 5. Features

### Candidates and job ads **[Confluence]**

- **Kanban board** per job ad.
  - Sort: score, date added, name.
  - Filter: application status, tech test status, offer status, proximity, interview score, technical score.
  - Search: keywords (name, description) and tags (skills, attributes).
- Default Kanban: company-wide default, adjustable per job ad and during the process.
- **Default job template** (stages + automations) set by an Admin in Settings. **Not applied automatically**: first time a recruiter opens the candidates of a new job ad, they click "Apply the default job template" (once per job ad), then can adapt it for that job ad only. Tip: one default template covering most job ads.
- Job ads list: sorted by latest publication date (fixed), with search.
- Comments on candidates: cannot be edited.
- Share an application with a colleague: yes, if the colleague has access to an E-ATS workspace.
- Self-service setup of email templates, interview invitations, assessments, scorecards, recruitment funnels (optional).

### Reports **[Confluence]**

- Current pipeline
- Pipeline speed (time between stages)
- Pipeline conversion (top-to-bottom funnel ratio)
- Time to hire / time to fill
- GDPR report (candidates near or past retention deadline)
- Export as PDF or CSV, filter by period or job ad.

### Integrations **[Confluence]**

- Email: Gmail (send-only permission), Microsoft (Mail.Send; Microsoft auto-adds Mail.ReadWrite, Candidly states it does not read the inbox). Candidate replies tracked via a platform address in copy.
- Calendars (Google, Microsoft) via **Cronofy**; tokens stored encrypted.
- Video tools: connected per user. **Google Meet** requires a Cronofy subscription the customer buys and pays directly (USD, per active seat, https://www.cronofy.com/pricing-direct). JobCloud does not set or invoice this price.
- Inbound **XML feeds** supported for Candidly workspaces; all applications delivered to Candidly. Compatible with customer job feeds / website integration (no impact).

### Data retention and GDPR (Candidly baseline) **[Confluence]**

- Admin sets retention period (e.g. 6, 12, 18 or 24 months).
- Candidates emailed 15 days before deletion to keep or delete; no answer = permanent deletion.
- Admins receive a CSV report of upcoming deletions.
- Deleted data may remain in backups up to 1 month.
- 8 default rejection reasons (editable in Settings > Recruitment > Unsuccessful Reasons): Wrong Skill Set, Not the Right Cultural Fit, Lacking Relevant Experience, Salary/Benefits, Communication Skills, More Qualified Candidates, Hired Elsewhere, Other.

---

## 6. Known limitations (do not promise)

| Limitation | Detail |
| --- | --- |
| Screening questions | Not available in Enterprise ATS; answers not visible. Hidden in vacancy creation for Candidly workspaces (CDH-2009). Engineering epic CI-1084 "Candidly Screening Questions support" is To Do **[Confluence] [Jira]** |
| Bulk candidate export | No bulk export of profiles, CVs or attachments; attachments downloadable one candidate at a time. Report exports may contain candidate names per job ad but are not a database export. **[Internal only]** FAQ (29 Oct): quote requested from Candidly. Risks page (30 Oct, more recent): "Not available. Not planned" (Caduff) **[Confluence]** |
| Full candidate file download | Not available (exists in ONE basic ATS). **[Internal only]** Candidly quoted ~CHF 1,800 (to be confirmed); Caduff decided not to invest for now **[Confluence]** |
| Job fields not synced | Salary, workload, languages and screening questions are not passed to E-ATS (API V2 supports some, not built) **[Confluence]** |
| Stopped / deleted job ads | Stay open in E-ATS; customer closes them manually **[Confluence]** |
| User email | Can only be changed in ONE **[Confluence]** |
| Session | Candidly session lasts 14 days, independent of ONE session; logout from ONE does not log out of Candidly (CDH-2017 backlog) **[Confluence] [Jira]** |
| Cosmetic | Candidly re-cases job titles and geocodes addresses **[Confluence]** |
| Rejection reason at pre-screening | Cannot be set at pre-screening stage (DD-1194) **[Jira]** |
| Rejected candidates | No dedicated column; disappear from Kanban, need filter (DD-1196) **[Jira]** |
| Candidate history | Cannot see if a candidate applied to several job ads (DD-1220) **[Jira]** |
| Candidate sharing | One application at a time, only to users who already have access (DD-1221) **[Jira]** |
| Default template | Must be applied manually per job ad **[Confluence]** |
| Edit comments | Not possible **[Confluence]** |
| Switch back to basic ATS | Not possible once a workspace has a job ad **[Confluence]** |
| Back office access | Exists but reveals all candidate PII; masking could be requested from Candidly **[Confluence]** |

---

## 7. Onboarding

### Principle **[Confluence]**

- **Customer Service** enables E-ATS access in ONE by setting the workspace type to "JobCloud Enterprise ATS" (like for External ATS).
  - Preconditions: workspace **empty** (no job ads) and at least **one Administrator**.
- **Customers set up E-ATS themselves** (self-service) using the Product Guide. CS does not run the setup but answers questions.
- Rollout: no technical limit on parallel onboardings; rollout planned **gradually** to collect feedback.
- Sales message: "You get a guide to follow, and Customer Service is there if you get stuck."

### Customer journey **[Confluence]**

1. Customer decides to take E-ATS; Sales or CS sends the Product Guide.
2. Customer logs in to ONE, clicks "Enterprise ATS".
3. Customer follows the Product Guide section by section.
4. Questions -> Customer Service.
5. All guide steps done = onboarding complete.

### The 4 setup steps (from onboarding email) **[Confluence]**

Before starting: colleagues have access in ONE; logo and an example hiring process at hand.

| Step | Content | Done by |
| --- | --- | --- |
| 1. Global settings | Logo and brand colour for emails, candidate data retention, rejection reasons | Admin |
| 2. Templates | Emails, interview invitations, assessments, scorecards | Admin |
| 3. Tools | Email signature, availability, connect email and video tools | Each team member |
| 4. Hiring process | Stages (e.g. first interview, team interview, case study) | Admin |

Then job ads are published in ONE as usual and applications managed in E-ATS.

### CS playbook when a customer contacts them **[Confluence]**

1. Ask which Product Guide step the customer is on.
2. Look in the Product Guide, then the FAQ.
3. Answer in the customer's language, point to the exact guide section.
4. Menu item missing -> check workspace role in ONE.
5. Guide never received -> send it.
6. No answer found -> escalate to Product Support Team.

---

## 8. Support, SLAs and operations

### Support levels **[Confluence]**

- L1 = Customer Service. L2 = Product Support. Only L2 submits tickets to Candidly (confirmed on Risks page, 30 Oct), linked in Jira. Core / Dev Maintenance fixes ONE-side bugs; Candidly fixes ATS-side bugs.

### RACI **[Confluence]**

| Activity | R | A | C | I |
| --- | --- | --- | --- | --- |
| Receive customer issue | CS (L1) | CS | L2 | PM |
| Qualify and reproduce | Product Support (L2) | L2 | PM, CS, Core | |
| Fix ONE-side bug | Core / Dev Maintenance | PM | | L2 |
| Fix ATS-side bug | Candidly | PM | | L2 |
| Decide on evolution requests | PM | PM | L2, Core, Candidly | CS |
| Communicate to customer | CS | L2 | PM | |

### Escalation flow **[Confluence]**

1. CS checks Product Guide and FAQ, answers or escalates to L2.
2. L2 reproduces on staging and classifies (ONE-side, ATS-side, request).
3. ONE-side bug: Jira ticket for Core / Dev Maintenance.
4. ATS-side bug: L2 submits ticket to Candidly, linked in Jira.
5. Evolution request: Jira ticket under MEPROJ-1464; not built by default (maintenance mode).

Templates: **Bug** = customer, legal entity ID, workspace ID, environment, roles in ONE and E-ATS, steps, expected vs actual, screenshots, severity, customers affected, workaround; **no candidate personal data** (nFADP). **Evolution request** = problem, customers asking, revenue at stake, workaround, vendor or JobCloud change; built only if PM approves.

### Troubleshooting by symptom **[Confluence]**

| Symptom | Likely cause | Action |
| --- | --- | --- |
| User does not see "Enterprise ATS" | Workspace type or ONE permission | Check workspace type and role |
| Job ad cannot be published | No eligible owner, empty location, company not synced, or Daxtra pool empty | Check owner and address; L2 to Candidly for `daxtra_db_missing` |
| Old or stopped job still open | No archive in API V2 | Close manually in E-ATS |
| Users or jobs missing after a deploy | No backfill (offset latest) | Re-save in ONE; escalate to Core |
| Role or profile out of sync | Partial sync failure | Re-save user in ONE; escalate to Core with IDs |
| Title casing or address differs | Candidly re-casing / geocoder | Cosmetic, no action |
| Applications missing | Delivery error (422 missing phone, 404 job not synced) | Core first |
| Gmail, Outlook, Zoom, Slack connection fails | App verification pending | Check status (§10) |
| Kanban, templates, reports, emails, scheduling | Candidly product | L2 ticket to Candidly |

### SLAs (JobCloud-specific, response by impact) **[Confluence]**

| Impact | Example | SLA |
| --- | --- | --- |
| Critical | Platform down, data leak | 2 hours |
| High | Core flow blocked for many users | 4 hours |
| Medium | Feature broken, workaround exists | 24 hours |
| Low / enquiries | Cosmetic, question | 48 hours |

### Candidly platform baseline **[Confluence]**

JobCloud-specific answers override these defaults.

| Topic | Default |
| --- | --- |
| Uptime | 99.9% per month |
| Planned maintenance | 21:00-05:00 CH time, announced at least 48 h before |
| Backups / recovery | Max data loss ~5 min; restore within 1-3 h; backups kept up to 1 month |
| Data breach notification | Within 48 h of Candidly becoming aware |
| Closing a company | Deletes users, job ads, candidates. Deleted user's pending interviews move to account owner or job owner |
| Hosting | AWS, EU instance |

### Sub-processors **[Internal only]** **[Confluence]**

Legal review pending; do not share with customers.

| Sub-processor | Purpose | Region |
| --- | --- | --- |
| Mandrill | Email | US |
| Dropbox Sign | E-signatures | US |
| OpenAI | Job descriptions | US |
| Daxtra | CV parsing | EU |
| myInterview | Video interviews | EU |
| Cronofy | Calendar | Partner-chosen region |

---

## 9. Sales and CS material **[Confluence]**

All on [Sales documentation JobCloud Enterprise ATS](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/86901653549/Sales+documentation+JobCloud+Enterprise+ATS) (last modified 12 Nov 2026). 47 attachments (PDF/PPTX); content not extracted here (GAP). Latest version per item:

| Material | FR | DE | EN |
| --- | --- | --- | --- |
| Capabilities comparison Basic vs Enterprise ATS | `Enterprise_ATS_Comparaison_des_capacites_FR.pdf` (26 Oct) | `Enterprise_ATS_Funktionsvergleich_DE.pdf` (11 Nov) | `EN_Capabilities comparison ... (1).pdf` (2 Oct) |
| Factsheets LE / ME / SA-5 / SA-6-20 / SA-21+ | `Enterprise_ATS_Factsheet_FR_*.pdf` (26 Oct) | `Enterprise_ATS_Factsheet_DE_*.pdf` (11 Nov) | `*-Enterprise ATS Factsheet_EN.pdf` (24 Sep; says "Google Meet included": wrong) |
| Sales deck (External Presentation) | `..._FR_v3_28.10.2026.pptx` (29 Oct) | `..._DE.pptx` (2 Oct, being reviewed) | `..._EN.pptx` (5 Oct) |
| Onboarding Product Guide | `jobcloud_ats-d-entreprise-guide-de-demarrage_fr_light.pdf` / `_fr_visuels.pdf` (12 Nov) | WIP | `Product_Guide_Enterprise_ATS_V1.pptx` (5 Oct) |
| Pricing staffing agencies | - | `Pricing_Staffing_Agencies_DE.pptx` (2 Oct) | - |
| Onboarding email template | GAP | GAP | Yes (WIP) |

- Product Guide FR targets "companies with one or several workspaces": publish first job ad in ONE right away; admin sets company settings once; each team member completes own profile.

- Not final: videos (to be created by Marketing once the official demo account exists). **[Confluence]**
- Open FAQ questions remain; check before promising anything to customers. **[Confluence]**

---

## 10. Technical reference **[Confluence]**

### End-to-end flow

1. CS sets a workspace to type JobCloud Enterprise ATS (empty, at least 1 Admin; irreversible once a job ad exists).
2. ONE Core emits change events (Kafka).
3. Adapter creates/updates company, users and job ads in Candidly (**one-way sync**).
4. Adapter writes sync confirmation back to ONE (`atsSettings.config`), which unlocks publication. Credit redemption blocked until the vacancy has a Candidly jobId (CDH-2026) **[Jira]**.
5. User clicks "Enterprise ATS" in ONE sidebar: signed SSO login (JWE token to `/welcome`).
6. Candidates apply on jobs.ch / jobup.ch: `ats-adapter-candidly` pushes the application (`POST /jobs/{id}/apply`).

### Adapter (`marketplace-adapter-core-candidly`)

- PHP 8.5 CLI daemon on AWS ECS; Kafka on Aiven (Avro, Schema Registry); PostgreSQL; secrets in AWS Parameter Store; CI on CircleCI. Grafana dashboard + consumer lag alerts (CDH-2003).
- Topics: `...account-membership-change` (v1), `...vacancy-change` (v2). Consumer group `marketplace_core_candidly_adapter`, offset latest (**no backfill**).
- Syncs only if ATS = CANDIDLY and account and legal entity are ACTIVE.
- Identity: company_id/domain = LegalEntity UUID; member_id = userId:legalEntityId; Candidly job id = ONE vacancy UUID.
- Auth to Candidly: JWE (RSA-OAEP + A256GCM) in `X-Secret-Key`, valid 5 min. Auth to ONE: Auth0 client credentials.
- Job fields sent: id, title, location, description, job_owner_emails. Updates fire only on title, description or address change.
- Not done: job archive, two-way sync, salary/workload/languages/screening questions, publication lifecycle, rollback on partial failure.

### SSO and application delivery (API V2)

- SSO payload: company_id, member_id, unique_session_id (single use). Session 14 days; latest login wins across companies. Sign-out `DELETE /api/v1/sign_out`.
- Application required fields: first_name, last_name, email, contact_no. Resume PDF/DOCX up to 25 MB, up to 5 other documents.
- Errors: 422 invalid data, 404 job not synced, 409 candidate already exists, 410 job archived.
- Rate limit: 300 requests / 5 min / user in prod (100 non-prod); Share CV 20 (10 non-prod).
- Full endpoint contract: [Candidly API Spec V2](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87018471425/Enterprise+ATS+-+Candidly+API+Spec+V2+Auth+Users+Jobs+Applications) (engineers).

### Third-party apps (status 26 Oct 2026)

| App | Use | Status |
| --- | --- | --- |
| Microsoft (Outlook, Teams) | Email, video | Partner verification pending; partner ID cannot be applied yet |
| Google (gmail.send, Maps, Places) | Email, geocoding | OAuth verification via Acquisition. Google **rejected** due to privacy policy wording; Legal asked for Limited Use text (LGLS-793, Pending Feedback) **[Jira]** |
| Zoom | Video | Marketplace review pending |
| Slack | Notifications | In review |
| Cronofy | Calendar, Google Meet (paid) | Managed by Candidly |

Credentials in 1Password (via Benjamin Zutter).

### Environments

- Production: https://enterprise-ats.jobcloud.ch. Staging: https://enterprise-ats.staging.jobcloud.ch.
- Access: ONE user from Inhouse Support / Cloud Engineering; CS sets a test workspace to E-ATS type; use Admin and a Limited role to reproduce.
- Vendor back office (Candidly) shows all candidate PII.

---

## 11. Decisions, accepted risks, open questions **[Confluence]**

### Decisions taken

| Topic | Decision | By |
| --- | --- | --- |
| Full candidate file download | Not built (quote ~CHF 1,800, to confirm) | Caduff |
| Bulk candidate export | Not available, not planned | Caduff |
| Google Meet | Paid via customer's own Cronofy subscription; Zoom and Teams free | 29 Oct 2026 |
| Hosting | AWS EU (overrides sales claim "Switzerland and EU") | FAQ |
| Vendor tickets | CS = L1, Product Support = L2; only L2 submits to Candidly | Confirmed |
| Response SLAs | 2h / 4h / 24h / 48h | FAQ |
| Prices | Annual subscription, no setup fee | Sales |
| Evolutions | Kept to a minimum, logged under MEPROJ-1464, not built by default | PM |

### Accepted risks

| Risk | Impact | Handling (no new build) |
| --- | --- | --- |
| Job ad stopped/deleted in ONE stays open in Candidly | High | Customer closes manually; L2 cleans orphans on request |
| Closing a company permanently deletes users, job ads, candidates | High | CS checks with customer before archiving last E-ATS workspace |
| Partial sync failure (no rollback) | Medium | Re-save user/role in ONE; escalate to Core |
| No event backfill after deployment | Medium | Re-save affected users/job ads in ONE |
| Daxtra pool empty -> onboarding fails (`daxtra_db_missing`) | Medium | L2 asks Candidly to refill |
| Account owner cannot be deactivated before a new owner is set | Medium | Give ADMIN to another user first |
| Candidly session 14 days vs ONE session | Medium | Accepted |
| Title re-casing, address geocoding | Low | Accepted |
| Job fields not synced (salary, workload, languages, screening questions) | Low | Accepted |
| Dev SSH key committed in repo (docker/dev) | Low | Core to confirm dev-only and rotate |

### Open questions (as of 30 Oct 2026; due dates passed, current status unknown: GAP)

| Question | Owner | Due |
| --- | --- | --- |
| Which team owns SSO and application delivery (`ats-adapter-candidly`)? | Core | 4 Nov 2026 |
| Which auth flow is live: V1.0 (JWT) or V2.0 (JWE)? (code uses JWE) | Core / Candidly | 5 Nov 2026 |
| nFADP evidence: sub-processor locations, transfer basis (art. 16), Google Limited Use wording | Legal / Candidly | 6 Nov 2026 |
| Exact amount of the full-download quote | Gabriel | 5 Nov 2026 |
| Correct EN factsheets "Google Meet included" | Marketing | 6 Nov 2026 |
| Microsoft partner verification and Zoom review | Gabriel / Benjamin | ongoing |
| API spec typos and Share CV scope | Candidly | low |

---

## 12. Evolution requests and related Jira **[Jira]**

Epic [MEPROJ-1464](https://jobcloud.atlassian.net/browse/MEPROJ-1464) "Enterprise ATS evolution requests" (Gabriel, In Progress). Ideas in project DD (Ideas hub):

| Key | Idea | Reporter | Created |
| --- | --- | --- | --- |
| DD-1194 | Rejection reason can't be set at pre-screening (Swiss customers reject for legal reasons, e.g. no work permit) | Karima Selmi | 28 Oct |
| DD-1196 | Rejected candidates are hard to find (no dedicated column) | Karima Selmi | 29 Oct |
| DD-1197 | Paying customers lose screening questions that free users keep (adoption/renewal risk; most target customers use them in legacy jobup ATS) | Karima Selmi | 29 Oct |
| DD-1208 | Advanced stats (no custom report builder, no API to stats) | Gabriel | 16 Nov |
| DD-1217 | Workspace-level tag "Enterprise ATS" in Back Office (like "External ATS") | Laura Couve | 20 Nov |
| DD-1218 | Bulk view/download of attachments | Gabriel | 20 Nov |
| DD-1220 | Candidate previous applications (nLPD question) | Gabriel | 20 Nov |
| DD-1221 | Simplify candidate sharing (multiple / flexible) | Gabriel | 20 Nov |

Other open tickets:

| Key | Topic | Status |
| --- | --- | --- |
| DD-1096 | "Candidly integration" discovery idea (lead Lucille / Marko, decision Simon), created 26 May 2026 | Evaluate / Measure |
| CI-1084 | Candidly Screening Questions support (epic) | To Do |
| LGLS-793 | Privacy policy text for Google OAuth verification | Pending Feedback (Legal) |
| LGLS-805 | ATS and seeker data deletion: may we return seeker data stored in ONE ATS? (raised by Lucille) | Pending Feedback (Legal) |
| AR-108 | Candidly AI features (AI Review Board) | Pending Feedback |
| CDH-2017 | Logout from Candidly when user logs out of ONE | Backlog |
| CDH-2011 | Changing role causes 404 on Candidly side | Backlog (bug) |
| CDH-2146 / CDH-2147 | Adapter maintenance (DBAL, composer audit) | Backlog / Ready for Review |
| CI-1247 | Graceful shutdown for `ats-adapter-candidly` | To Do |
| LMEE-48 | mkp-client: analytics feature flag and sidenav item | In Review |

---

## 13. Confluence page map

| Page | ID | Last modified |
| --- | --- | --- |
| [JC ONE Enterprise ATS](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/86471311408/JC+ONE+Enterprise+ATS) (parent, Sales/CS entry point) | 86471311408 | 30 Oct 2026 |
| [Sales documentation JobCloud Enterprise ATS](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/86901653549/Sales+documentation+JobCloud+Enterprise+ATS) | 86901653549 | 12 Nov 2026 |
| [Consolidated FAQ: Enterprise ATS](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/86907158546/Consolidated+FAQ+Enterprise+ATS) | 86907158546 | 29 Oct 2026 |
| [Onboarding new Enterprise ATS customers](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/86932979713/Onboarding+new+Enterprise+ATS+customers) | 86932979713 | 2 Oct 2026 |
| [Enterprise ATS - High-level Overview](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87015129148/Enterprise+ATS+-+High-level+Overview) (Gabriel) | 87015129148 | 30 Oct 2026 |
| [Enterprise ATS - Product, Features and Commercial](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87021486103/Enterprise+ATS+-+Product+Features+and+Commercial) | 87021486103 | 30 Oct 2026 |
| [Enterprise ATS - Technical Reference](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87021748225/Enterprise+ATS+-+Technical+Reference) | 87021748225 | 30 Oct 2026 |
| [Enterprise ATS - Support and Operations](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87021387789/Enterprise+ATS+-+Support+and+Operations) | 87021387789 | 30 Oct 2026 |
| [Enterprise ATS - Risks, Open Questions and Decisions](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87021191176/Enterprise+ATS+-+Risks+Open+Questions+and+Decisions) | 87021191176 | 30 Oct 2026 |
| [Enterprise ATS - Candidly API Spec V2](https://jobcloud.atlassian.net/wiki/spaces/lme/pages/87018471425/Enterprise+ATS+-+Candidly+API+Spec+V2+Auth+Users+Jobs+Applications) (not summarised) | 87018471425 | 29 Oct 2026 |
| [Glossary & naming rules](https://jobcloud.atlassian.net/wiki/spaces/PMH/pages/87078043679/Glossary+naming+rules) (PMH) | 87078043679 | 19 Nov 2026 |
| Simon's personal "FAQ Enterprise ATS" (86753214504): redirect to Consolidated FAQ only | 86753214504 | 28 Oct 2026 |

CORE-space engineering pages (not summarised): Candidly job ATS mapping (86511583314), Candidly ATS API tests (86512238656), Candidly ATS adapter tests (86944645222), Vacancy -> Job sync (86961782834), AccountMembership -> User, Company (86966108177).

---

## 14. Gaps / open points

- **GAP** Content of the 47 sales attachments (factsheets, comparison, decks, Product Guide, SA pricing deck) not extracted; only file names and dates.
- **GAP** Status of the open questions in §11 (all due dates passed early Nov).
- **GAP** DE naming of the product (glossary: "to confirm").
- **GAP** Official demo account not yet available; marketing videos pending.
- **GAP** D-CH Sales/CS demo date.
- **GAP** Customer migration plan (TBD), e.g. legacy jobup ATS customers.
- **GAP** Legal review of sub-processors / nFADP evidence (pending).
- **GAP** Onboarding email in FR and DE (page mentions FR/DE/EN; only EN present).
- **GAP** Handover date Simon -> Gabriel.
- **GAP** Pipeline: prospects in discussion, target number of customers, revenue goals.

---

## Changelog

- 24 Nov 2026: created from Confluence parent page + 3 sub-pages; status and ownership from Lucille.
- 24 Nov 2026 (later): added Gabriel's 5 consolidated pages (pricing, positioning, comparison, sales claims, technical, support ops, risks/decisions), PMH naming rules, attachment inventory, Jira tickets.
