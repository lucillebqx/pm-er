# ATS rethinking

Status: DRAFT fact base, compiled 17 Nov 2026 from the Miro board (uXjVH_Z5UCY=), the Figma file "Domain" (page "ATS bluesky") and Lucille's input in chat.
Legend: [Miro] = stated on the board. [Figma] = seen in the mockups. [Lucille] = stated by Lucille. [Inferred] = my reading, to confirm. [GAP] = not found, needs your input.

## 1. Why we worked on it in Term 2

Stated on the board
- [Miro] Entry point was data. A "Data, Data, Data" frame lists the inputs: GA / Adobe, Clarity (session recordings), Modjo (call recordings), survey feedback (CSAT), usability tests, interviews with Sales, Customer Service and Support, and a competitor review. A note proposes an "aggregator (UI-based) of all answers".
- [Miro] Pain points seen in the data (quick-win frames):
  - Notification overload in multi-person workspaces (volume and relevance); multiple clients reported it.
  - Users can't find their new candidates. Multiple CSAT complaints, and Clarity shows users going in circles between dashboard and job ad list.
  - "Where's the ATS actually?": overall confusion about where the ATS lives.
  - Little reading space, lots of scrolling to reach the CV and screening answers.
  - No way to see who answered YES to all screening questions.
  - Pipeline drop-off: users hire someone but never move the candidate to "Hired"; later stages happen outside the ATS.
  - Single-file, clunky document upload; empty lanes give no guidance; new and infrequent users get no explanation after publishing.
- [Miro] Usage data point: the "Download all" button is used by 16% of customers.
- [Miro] Recruiter think-aloud sessions (2026-09-03 and a second one) showed low trust in the fit score, confusing labels (Recommended / Shortlist / Suitable) and banner blindness on recommended candidates (details in section 3).
- [Miro] Pace: planning 20 Jul, recruiter interviews and research week of 27 Jul, workshop in Zurich 3 Aug (more Zurich workshop sessions in the weeks of 24 Aug and later).

Product goal (the business reason)
- [Lucille] By rethinking the ATS UI, the product goal is to create promotional placements directly in the ATS for the RPP features we will implement in the future.
- [Lucille] The rethinking also fixes known usability problems (the pain points above), so the ATS can carry those placements credibly.
- [Lucille] This supports the RPP strategy, i.e. the overall new strategy of the company, not a specific OKR set.
- [Lucille] Segments: all of them. With the RPP strategy, the focus of ONE, historically set on SE, is enlarged to all company sizes.
- [Inferred] The ATS is where every customer lands after publishing a job ad, so it is the natural surface to sell RPP features at the right moment.
- Figures (baselines, counts) are deliberately left out of this document.

## 2. Product vision

Stated on the board
- [Miro] Direction: "THE BIG ATS UI RETHINKING", a rethink of how information is delivered (entry points, candidate list, candidate page, dashboard widgets, emails).
- [Miro] Product philosophy: "simplicity-first" for the non-expert hirer (majority) versus power users (high-paying minority). The ATS should "surface what's important" instead of being passive.
- [Miro] Positioning of the ATS: not "just a CV distributor"; recommendation is to favor document upload over CV download so evaluation happens in the ATS.
- [Miro] Target flow, per hiring stage (lanes), with "Phase I / II / IIb / IIc" scoping of the information shown:
  1. Discover / New: first actions are shortlist, comment, contact, decline.
  2. Screen / Suitable
  3. Meet / In conversation (multiple "Meet" loops possible; collaboration and AI interview features are positioned here)
  4. Hired (close the ad, start date)
  5. Unsuitable
  6. Declined
  - Archived and "All candidates" are out of scope for now.
- [Miro] Idea: differentiate WHY a candidate is suitable (fit the job / the company / the culture) and compare shortlisted candidates (what they have in common, what sets them apart).
- [Miro] "Close future": vector-based search (matched languages, years of experience, industry experience, relevant / matched / unmet skills, academics).
- [Miro] "RPP stuff" (later): AI interview analysis, interview scheduling, feedback space, video interview, cultural fit.
- [Miro] Figma mockups ("ATS bluesky"), see section 5: a requirements review step ("Review your requirements", must-haves, nice-to-haves, languages extracted from the job ad) then a candidate list per stage (table with CV Insights score), and a candidate side panel (details, activity, comments, documents, screening answers, CV Insights).

Vision (Lucille's words, structured)
- [Lucille] An ATS that provides insights about candidates: a tool that processes the information sent by seekers and translates it into actionable insights.
- [Lucille] Leverage the vector-based technology developed with Invite to apply, so that every customer using the internal ATS gets insights on the applications received.
- [Lucille] Place selling points at the right moment for clients.
- [Lucille] The ATS becomes the perfect hiring companion for recruiters. AI is used to better connect the humans behind the process.
- [Lucille] Definition of "insights": information about the applicant, processed to highlight education, experience, knowledge, set of skills, languages, number of years of experience, and the answers to the screening questions compared to the expected answers.
- [Lucille] Segments: all (SE, LME and larger), in line with the RPP strategy.
- [Figma] The mockups already express this: "Recruiter assistant" (chat, "Ask Clippy anything about your candidates", e.g. "Recommend me new applicants a great fit"), AI insights with green / yellow points per candidate, an AI candidate profile summary, and fit labels (Great fit).

Draft one-liner (to validate): "The ATS that turns what seekers send into actionable insights, and is the hiring companion recruiters want to open every day."

To confirm
- [GAP] What success looks like in 12 months (qualitative is enough).
- [GAP] Final naming: "Recruiter assistant" / "Clippy" in the mockups.
- Link to existing context: CV Insights (setup/company/matching.md), Invite to apply (setup/company/invite-to-apply.md), RPP and ONE monetization (setup/company/strategy-jobcloud.md).

## 3. What we looked at (research)

Scope of the Term 2 research (Lucille)
- [Lucille] Lots of research took the market into account: worldwide first, then EU-based.
- [Lucille] Listening to customer calls (Modjo) and known customer feedback (CSAT, surveys, Clarity).
- [Lucille] Usability tests still have to take place this term, in more detail.
- [Lucille] Principle for testing: tests run on a bunch of colleagues; we do not show the work to customers, to avoid creating expectations. Order: finalize the vision, estimate it, then get business confirmation.

Competitor benchmark (Miro, Yassine and Lucille, feature grid)
- ATS analysed: Zoho Recruit, Greenhouse, Workable, VIVAHR, Better team, Totaljobs, Recruit CRM, Recooty, Pinpoint, JazzHR, Teamtailor, Recruitee, Trakstar Hire, BambooHR, Manatal. A later list also names Pracuj.pl, Join.com, Homerun, Hirefly (Wellfound), Workable, Greenhouse, Ashby, no fluff jobs.
- Grid dimensions: assignee, target customer (SE / LME), collaboration (multi-users, comments with mentions, activity log, scorecards), productivity (templates, bulk actions, task automation), communication (2-way email, history), calendar integration, managing applications (kanban vs list, customization, multiple flows, tags, scoring, questionnaires, comments, filter / sort), interview features, AI (information extraction, scores, MCP), others (integrations, talent pool), UI of candidate page and dashboard, pricing model (pay as you go, product related).
- Observations noted: scoring per skill felt messy (Manatal); star-rating plus comment; permission-style roles; reading-space ideas; quick evaluations / evaluation forms; step-by-step hiring guidance; notification center; "Pay per Invite???" as a pricing idea.

Internal and customer data (Miro)
- GA / Adobe, Clarity recordings, Modjo calls, CSAT survey feedback ("CSAT explorer" to dig into comments), usability tests (before / after), interviews with Sales, Customer Service and Support, "Questions based on feedback" and "preliminary data exploration".
- Interviewing recruiters and research, week of 27 Jul 2026.

Think-aloud sessions (Miro, 2026-09-03, 27 min, plus a second session)
- Trust in the fit score is low: 94% match plus 2 lines isn't enough; wants to see which criteria drove it.
- "Recommended for you", "Shortlist" and "Suitable" overlap and confuse; the Shortlist button purpose is unclear.
- Work authorization checkbox is distrusted (self-reported); location is a stronger signal.
- Wants 3 to 5 killer criteria set once at job ad creation and auto-checked per candidate.
- Still leaves the system to check LinkedIn for authenticity (AI-tailored or fake CVs).
- Languages need a proficiency level; a missing skill tag does not mean the skill is absent.
- Needs fast filter / sort at 60 to 100+ candidates.
- A wish to filter by nationality came up. [Lucille] We do not take that into account; the focus is the right to work in CH (confirmed, see section 4, risks).
- Session 2: horizontal scroll in the table not discovered, banner blindness on recommended candidates, card doesn't look clickable, numbers in the filter modal not understood.

Quick wins and decisions log (Miro, "Frame 8")
- DONE: CV Insights unavailability explanation; rename the comments copy.
- IN PROGRESS: collapsible ribbon / reading space; display screening answers and sort; "John is hired, decline all others" (both inside the big UI rethinking).
- SOLUTION DESIGN NEEDED: notification settings, empty-lane follow-up, welcome to the ATS, "where are my candidates", "where's the ATS", applications with comments, strategic CV placement.
- NO GO: "Download all" promotion (customer frustration), upload docs improvement, notify applicant after lane moves, screening-question automation from job ad creation.

Open questions in the board
- Entry points into the ATS (dashboard, vacancy page, job ad publication page, emails); screen as you go vs all at once; one job ad vs multiple live; kanban vs list; how many tabs by default and whether users can create their own.
- Information to define with the Apply team: post code, notice period, where do you want to work, salary expectations, work authorization.

To confirm
- [GAP] The think-aloud sessions on the board (3 Sep 2026): colleagues or customers?
- [GAP] Usability test plan for this term (goals, tasks, prototype to use).
- Research counts are intentionally not reported (decision: no figures).
- Some Miro frames were not extracted (e.g. "Questions based on feedback", "to be set", frames 1 / 9 to 13, embedded docs).

## 4. Strategy

Stated on the board
- [Miro] Two tracks: (a) quick wins shipped independently (numbered 1 to 14, with "effort wins" and "strategic decisions"), and (b) THE BIG ATS UI RETHINKING, in phases (Phase I, II, IIa to IIc, "Phase 2" frame).
- [Miro] Scope set via an exploration frame: CSAT, competitors, delivery of information, candidate profile page, dashboard, entering the ATS, kanban vs list, sort / filter, sub-sections, priority of information, internal data (Apply team, Profile team, vector-based search).
- [Miro] Information is split into Mandatory (applications received, name, date, email, phone, CV, CV Insights score and summary, screening answers, messages, cover letter, comments, bulk actions, decline, move stage, search, mark as read, invite to apply / sourcing), Desired (add application or document, product type), Future (shortlist via tags, vote up / down) and To define with Apply Team.
- [Miro] Principle: "Do we give customers what they're asking for, or what we believe they need?" Simplicity-first for the non-expert majority.
- [Miro] Design process: Zurich workshops (calendar frames from 3 Aug), then Figma "ATS bluesky".

Sequence of work (Lucille)
- [Lucille] 1. Finalize the vision. 2. Estimate it. 3. Get business confirmation. 4. Only then show anything to customers (colleague-only tests until then, to avoid creating expectations).

Monetization model (Lucille)
- [Lucille] The features presented will be monetized: calendar invite, CV Insights score, Schedule an interview, Prepare for an interview, Vote for a candidate, and others.
- [Lucille] Assumption: they will be part of a billing plan, not sold individually. Promotional placements therefore promote a plan, not a single feature.
- [Figma] Placement example: in the candidate panel, the "Interviews" tab shows "It's time to talk face-to-face. Unlock your hiring potential with JobCloud ONE's interview module..." with the CTA "First interview for free" and a dismiss link. The tabs "Assessments" and "Background check" also appear in the panel. A black diamond button sits next to the job ad title in every view (probably the premium entry point).
- [Inferred] "First interview for free" suggests a free-trial pattern; this needs alignment with a plan-based billing model.
- [Lucille] Model: very likely freemium. Paid features are grouped the way LinkedIn groups them.

Freemium grouping, LinkedIn-style (proposal, to validate)
- [Inferred] What LinkedIn does (linkedin.com/talent-solutions): it groups its paid offer by hiring frequency and persona, not feature by feature. A free job post sits at the base. "Hiring Pro" targets occasional hirers who aren't recruiters (from job post to interview, qualified shortlist of best-fit candidates). "Recruiter + Hiring Assistant" targets consistent hiring (advanced sourcing, smarter automation, integrations, agentic AI).
- [Inferred] Applied to JobCloud ATS (all segments), 3 groups:

| Group | For | Features (from your list and the mockups) |
|---|---|---|
| Free (included with the job ad) | Everyone | Applications in lanes, requirements review, screening answers display, basic extracted profile (education, experience, languages, skills), comments, decline / move stage, messages |
| Plus (occasional hirer) | Non-expert hirers of any size | CV Insights score and deep criteria evaluation, screening answers compared to expected answers, calendar invite, schedule an interview, prepare for an interview, vote for a candidate |
| Pro / Team (consistent hirer) | Recurring hirers, larger teams, agencies | Recruiter assistant (AI chat), AI profile summary, compare candidates, collaboration (scorecards, mentions), bulk actions, invite to apply / sourcing |
| Partner offers (outside the plans) | Anyone | Assessments, background checks (via a trusted partner) |

- [Figma] Designer note: "sort applications by fit will be a paid feature".
- [Lucille] Decision: fit sorting stays in Plus; the free tier shows the top 3 applicants at the top of the list as the teaser.
- [Lucille] Decision: Assessments and Background checks are partner offers, not part of the plans (confirmed).
- [GAP] Is Invite to apply part of the ATS groups or kept as its own product (see setup/company/invite-to-apply.md)? Does the first teaser stay free ("First interview for free")?
- [GAP] Plan names and prices (PRO team owns billing, see setup/company/job-ad-monetizations.md).

Placement suggestions (to react to)
Principle: promote at the moment of value, never block the free flow, and keep the non-expert hirer's path simple.
1. Contextual teaser in the candidate panel, tied to the stage. The Interviews tab promo already in Figma ("It's time to talk face-to-face...") fits when a candidate is moved to Shortlist / In conversation. Same pattern for Assessments and Background check, framed as partner offers rather than plan upgrades.
2. Locked insight preview. In the table and panel, the free profile shows extracted facts; the CV Insights score and deep criteria evaluation show a blurred or teaser state with "See why this candidate fits". The value is visible before paying.
3. Action-triggered upsell. Clicking "Setup interview", "Prepare Interview" or the vote button on a free plan opens a short plan comparison, instead of a banner.
4. Empty-lane and first-visit moments. The empty "In conversation" lane or the first visit after publishing can explain what comes next and what the paid plan adds (this also fixes the "empty lanes give no guidance" pain point).
5. Recruiter assistant entry. A free sample question (e.g. "Recommend me new applicants a great fit") then the plan prompt once the list is longer than what a person can scan.
6. Persistent premium entry point. The black diamond next to the job ad title opens the plan overview; always the same place, never animated.
7. Guardrails: one promo at a time, dismissible with memory, max once per candidate stage, no promo on the first screen of a first-time user, none in notification emails at launch (lesson from "notification overload").

Risks
- [Lucille] Nationality filtering is not taken into account. The focus is the right to work in CH (confirmed). The mockups use "Can work in CH" / "Work in CH: Yes" columns, "Country (can work in CH)" in the data spec, and permit / citizenship values (Swiss citizen, EU citizen, L permit, C permit).
- [Miro] Work authorization is self-reported and distrusted by recruiters.
- [Miro] Billing logic is owned by the PRO team; Domain displays status in the ATS.
- [Miro] Simplicity-first for the non-expert majority vs promotional pressure.
- [Miro] Trust in AI scores is low; the mockups already include disclaimers and "Learn more about scoring".
- [Miro] "Download all" promotion was a NO GO because of customer frustration; promotions must not take away existing free value.

To confirm
- [GAP] Strategic positioning (why a JobCloud ATS: differentiation vs competitors and vs external ATS integrations).
- [GAP] Success metrics, roadmap and timing (Term 3), team and dependencies (Domain, Apply, Profile, PRO, Delivery).

## 5. Mockups (Figma)

- File: "Domain", page "ATS bluesky" (node 20964:111914). Frames include 11+ "ATS view" variants, about 35 "application" frames, many "Right colomn" and "Helper" states, a "Tables" section and several widgets.
- [Figma] Job ad header: status, product (e.g. jobs.ch Ultimate Plus), dates, toggle "Job ad / Applicants", black diamond premium button.
- [Figma] Review your requirements (before looking at candidates): must haves and nice to haves extracted from the job ad, languages (e.g. German, English native / proficient), Skip or Apply requirements. Can be redone anytime.
- [Figma] Stage tabs with counters and a progress bar: New, Shortlist, In conversation, Hired, Declined (the Miro lanes Discover / Screen / Meet / Hired).
- [Figma] Filter chips (Live in Switzerland, Available immediately, Applied last 2 days, Best fit), list / table toggle, search, AI-assisted filters.
- [Figma] Table per stage (progressive information): New shows applied date, screening yes / no, availability, languages; Shortlist shows last activity, skills (+N), diploma, experience, languages, with comment and vote counts. Fit indicator next to each avatar (Great fit badge). Row actions: comment, email, move to next stage (Shortlist, Interview), decline.
- [Figma] Candidate panel (side drawer): fit badge, applied date, tags, next / previous candidate, shortlist, decline, thumbs-up vote; tabs Activity, CV Insights ("Deep criteria evaluation"), Documents, Comments, Messages sent; variant with left nav (Candidate profile, CV and Documents, Activity, CV Insights, Messages, Comments, Interviews, Assessments, Background check).
- [Figma] AI blocks: Insights (green strengths, yellow warnings), AI candidate profile summary ("4 strengths, 2 warnings"), most recent duties, always labelled "AI insights, review information on your own", plus legal disclaimer and "Learn more about scoring".
- [Figma] "In conversation" cards: next interview planned (e.g. Today 16:30), "Prepare Interview", "Setup interview", "Your next interviews".
- [Figma] "Recruiter assistant" chat with an applicant list on the right.
- [Figma] Personal message widget, documents widget, comment entry, "Tables" section with lane-move logic and an open question: "Still makes sense to give full autonomy on which lanes candidates are going?".
- [Inferred] These are explorations ("bluesky"), not final designs. Per Lucille, they are shown to colleagues only, not to customers.

Designer notes found in the file (text layers; the strongest source of intent)
- [Figma] Frame 21973 (principles for the whole exploration):
  - Candidate list: filter, compare, shortlist, adjust job-related criteria; show close matches and flag requirements that may be too restrictive.
  - Candidate sheet: bring together profile, documents, JobFit, screening answers, comments, messages, interviews and activity; let recruiters question or correct the evaluation.
  - Stage workflows: New = initial fit; Suitable = deeper review and interview preparation; In conversation = interviews and evaluation; Hired still needs definition.
  - AI's role: connect evidence, highlight unknowns, suggest actions; keep facts, opinions and AI guesses separate; the recruiter stays in control.
  - Design work: explore the structure, prototype a full candidate journey, cover failures, permissions and paid access.
- [Figma] Frame 21725:49907 (monetization hint): "Display the 3 best applicants at the top of the list. View more suitable applicants / sort applications by fit will be a paid feature, use this as an immediate fix, future = ??". Pending question: Legal, "best fit" or "recommended"? Two ways to review the list: TUNING (refine requirements from the job ad, e.g. "this requirement is actually less important") and EXPLORATION (look for a requirement that isn't in the job ad, e.g. "show me the candidate who can speak Italian").
- [Figma] Frame 22020:45790: "Your requirements are not the full picture of what you actually want. New criteria might pop up when you are reviewing the applicants."
- [Figma] Frame 21907:48251-48255 (side panel content spec): CV Insights = strengths + watch-outs, score breakdown, list of information found in the CV (click a certification to learn what it is). Interview = schedule, list upcoming, cancel, change. Messages = send, schedule. Activity = date, message sent, lane moves, comments / notes, decline with message, interview set up, document added; sortable by date or type.
- [Figma] Frame 21952:40405: activity grouped by dates (open question: do we need time?).
- [Figma] Frame 21876:17608: badges next to tab names always active, for discoverability. Frame 21876:17887: rename "Comments" to "Notes", private by default?
- [Figma] Frame 22597:46564 (candidate data spec): first / last name, email, phone, country (can work in CH), languages, competencies.
- [Figma] Frame 21864:12778: conditional filter functions (e.g. Experience AND Eligible AND Available).
- [Figma] Frame 22602:51881: "We have extracted the information from the CV to display your experience. Please verify this information independently."

Promotional placements found (Frame 22601, candidate panel with left nav)
- [Figma] Interviews: "Bring your interview to the next level" / "Unlock your hiring potential with JobCloud ONE's interview module. Experience seamless scheduling and real-time feedback to make informed hiring decisions."
- [Figma] Assessments: "Send tailored assessments to candidates and effortlessly evaluate their performance on customized tests."
- [Figma] Background checks: "Easily initiate background checks through our trusted partner to uncover any criminal history and ensure a safe hiring process." (a partner offer)
- [Figma] Sorting / viewing more suitable applicants by fit is noted as a paid feature (frame 21725:49907).

Frame catalogue (from the file structure and text layers)

| Group | Frames (node id) | What it shows |
|---|---|---|
| Early explorations (Section 1) | 8 "ATS view" frames, e.g. 20964:111949, 20964:112381, 20964:114398, 20964:114688, 20964:115000 | Butchery use case (Robert Thompson, Henry Marco...). Table with Name, Fit, Can work in CH, Questions (x of 4), Applied, Stage. Variants show "missing: French / unknown: city" evidence, a "Needs attention" group ("Interview not prepared", "Decline message not sent", "Evaluation required"), and Messages / Comments / Interview / Days in stage columns |
| Tables section | 20970:116551, 20973:117134, 20973:117530 | "NEW" table with Name, Skills, Languages, Availability, permit / citizenship (Swiss citizen, EU citizen, L permit, C permit), location, diploma, Questions; third variant adds Score and "Ask Clippy anything about your candidates"; sticky note on lane autonomy (20973:118278) |
| Requirements review | 21571:7268, 21571:7587, 21571:7760 | "Review your requirements": Must haves (requirements set on the job ad), Nice to have (what candidates bring), Languages, "Where should the candidate be located?", "Let's review your requirements before looking at your candidates" |
| Developer use case, list variants | 21571:6764, 21588:16185 (view-1), 21589:18363 (view-2), 21589:22156 (view-3), 21595:13509 (view-5), 21595:15392 (view-6), 21595:17899 (view-7), 21595:20636 (view-8), 21596:22619 (view-9), 21601:58976 (view-10), 21726:50002 (view-11) | Progressive columns per stage: Applied, Screening, Available, Languages (New); Last activity, Skills, Diploma, Experience, Languages (Shortlist); Fit, Eligibility, Skills with Great / Good / Partial / No fit (view-11); expanded rows with Recent duties, Work in CH, Availability |
| Application cards | 21595:8723 to 21595:12528, 21616:62342, 21595:13052, 21595:13329, 21595:11707 | Row states: collapsed, expanded, with "Next Interview planned", "Prepare Interview", "Review interviews" |
| Lanes | 21583:9525 "Meet", 21583:9965 "In Conversation" | Setup interview, Next Interview, Your next interviews |
| Candidate panel ("Right colomn") | about 25 variants, e.g. 21868:16401, 21907:49290, 22032:47116, 22583:170362, 22586:13028, 22591:35658 | Application date, fit badge (Great fit), Jobfit Full Report, AI insights disclaimer, General competency / Experience / Language, Personal message, Candidate details, Screening questions, Documents (5), Comments, 1 of 12 pagination; several variants are skeletons with only pagination |
| "Does Emilia meet your requirements?" | 22032:48507 | In-panel question to the AI |
| Recruiter assistant | 22098:50881, 22098:52075 | "Hi I'm your recruitment assistant, how can I help you today?" and "You have 4 applicants that are a great fit + 1 outlier! What would you like to know about them?" with an applicant list |
| Promotion and add-ons | 22601:49918 and neighbours (22597 / 22598 / 22602) | Interviews, Assessments, Background checks tabs with teasers; CV summary frame |

Note: the "Right colomn" frame 21898:45921 only contains pagination ("1 of 12"), so it is a skeleton, not a good reference.

Reference frames for the story (my selection, no reference was provided; to validate)

| Story step | Frame (node id) |
|---|---|
| 1. Review your requirements | 21571:7295, 21571:7787 |
| 2. Stage list per lane, progressive info | 21588:16185 (view-1), 21589:22156 (view-3), 21726:50002 (view-11), Tables section 20970:116956 |
| 3. Candidate insights panel | 22032:47116 or 22583:170362 (full content with screening questions) |
| 4. Meet / In conversation (schedule, prepare) | 21583:9525, 21595:11707, 21595:13329 |
| 5. Promotional placement | 22601:49918 (Interviews, Assessments, Background checks) |
| 6. Recruiter assistant | 22098:52075, 22032:48507, 20973:117530 |

Narrative: from "I received applications" to "I know who to talk to" to "I act on it (and discover what the paid plan adds at that moment)".

## 6. What I need to present this project (checklist)

| Need | Status |
|---|---|
| Problem statement and business case | Done: supports the company RPP strategy; promotional placements for RPP features |
| Research summary | Done qualitatively (no figures by decision) |
| Vision in one sentence | Draft proposed, to validate |
| Target segments | Done: all sizes (ONE enlarged from SE) |
| Strategy, phasing and scope | Partial (phases, info scope, sequence of work) |
| Monetization model | Freemium, LinkedIn-style grouping (Free / Plus / Pro), fit sorting in Plus with top 3 free, assessments and background checks as partner offers; plan names and prices [GAP] |
| Placement suggestions | Proposed, to react to |
| Usability test plan (this term, colleagues only) | [GAP] |
| Success metrics | [GAP] (not tied to an OKR set) |
| Risks | Done (see section 4) |
| Mockups with a narrative | Reference frames proposed, narrative drafted |
| Timeline, owners, dependencies | [GAP] |

## 7. Questions to refine (for Lucille)

1. Is the draft vision one-liner right?
2. Is the 3-group freemium split (Free / Plus / Pro) the right reading of the LinkedIn grouping? Open: CV Insights score (free teaser or paid) and Invite to apply (inside the plans or its own product). Settled: fit sorting in Plus with top 3 free; assessments and background checks are partner offers.
3. Which of the 7 placement suggestions do you want to keep, drop or change?
4. Were the 3 Sep think-aloud sessions colleagues or customers? Usability test plan for this term (tasks, prototype)?
5. Do the reference frames in section 5 match your story?
6. Anything on timing (Term 3), owners and dependencies, and what success looks like in 12 months?
7. Hire stage (section 8): the main CTA is defined (close the ad). Which information matters at that stage?

## 8. Stage model: information, CTAs and the deck (provided by Lucille, 18 Nov 2026)

### Principle
- [Lucille] Information and CTAs are aligned to the stage an application is in: Discover, Screen, Meet, Hire.
- [Figma] In the mockups (nodes 20964:111954, 20964:114693, 20964:115005), the stages appear as table tabs: New (Discover), Suitable (Screen), In conversation (Meet), Hired (Hire). The tab bar also shows All candidates, Unsuitable and Declined. [Inferred] This mapping is my reading of the screenshots, to confirm.
- [Lucille] All these tools will be sold in bundles of features (which features sit in which bundle is not detailed in the deck, see section 4).

### Per stage

| Stage | Information prioritized | CTAs |
|---|---|---|
| Discover | General fit indicator (CV Insights score); authorization to work in Switzerland; screening questions answered; application date | Update stage (the main CTA) |
| Screen | Next-level fit assessment (a deeper dig into the CV Insights score); comments left by recruiters in the previous or the current stage; number of days since the application entered the stage | Contact the applicant and decline are the encouraged CTAs |
| Meet | Interview advancement (is one scheduled, how many took place, when is the next one); messages exchanged with the candidate; comments left by me or my team | Prepare the interview or schedule it; evaluate the candidate |
| Hire | [GAP] Not defined yet | Close the ad (the main CTA): sends a declination email to all other applicants and deletes their data in our ATS |

### New items to mention
- All applications lane: a new lane in the ATS listing every application received. It is intended to be created upon request of the customers.
- Search: a new feature aligned with LinkedIn Hiring Assistant. It will be a dedicated initiative, separate from this project.

### Candidate profile page (still being worked on)
- [Figma] Mockups: nodes 20964:114262 (Details folder) and 20964:113329 (Activity folder). The profile opens as a panel with the candidate header, a Message button, a Not a fit button, and tabs Details, Activity, CV Insights and Documents. Details shows the fit summary ("Great match", categories met), the screening questions and answers. Activity shows moves between stages, comments and contacts, filterable by All, Messages, Comments.
- [Lucille] Information stays organized in folders (the tabs).
- [Lucille] The CV is accessible at all times (customer feedback).
- [Lucille] CTAs include: vote for the candidate (thumb up or down), leave a comment, learn about the profile via the CV Insights report, update the stage, contact the applicant, and more.
- [Figma] Hybrid UI option (node 21864:13654): candidate list on the left, profile on the right, instead of a full redesign.
- [Lucille] Layouts under review: full width versus panel (side view). Kept in mind: recruiters need to (1) collaborate and (2) compare applicants; we want to make both easier.
- [Lucille] Idea: help recruiters understand the files seekers provide directly, with reading helpers (e.g. the recruiter highlights a text and an AI explains it: this company is active in that industry, this diploma covers that field).

### Alignment with RPP
- [Lucille] We have been working with the Ecom team and will continue, to assess who the features are for and how they are bundled and priced.
- [Lucille] We keep working on promotional placements within the ATS, covering the full journey, avoiding a Christmas tree experience (everything popping out).
- [Lucille] Contextual upselling means offers targeted to the customer's needs. Example: we see you have many job ads live, so you might like to upgrade to Premium and benefit from features such as scheduling interviews, the AI interviewer and more.
- Reporting was removed from the slide (18 Nov).

### What we are still working on
- Finalization of the table view.
- Finalization of the profile view.
- UI options: maybe a hybrid version rather than a full redesign.
- Digging into features requested by customers, and how they fit in the current and next UI of the ATS.
- Testing and collecting feedback.
- Yassine demos the prototype just before this point in the presentation.

### Deck "ats-2.0 (v2)" (Miro board uXjVH_Z5UCY=, 14 slides)
1. Cover.
2. Product vision (raw data to insights; "working towards the ATS monetization, aligned with the RPP strategy").
3. How we got there (market and competitors, customers, data analytics, internal teams, PM-UX workshops).
4. What we found (space, technology, information, actions).
5. Product requirement 1: UX (screenshot).
6. Product requirement 2: Technology for all.
7. Product requirement 3: Layered information. Discover / Screen / Meet columns with the prioritized information and a screenshot crop per stage.
8. Product requirement 4: CTAs follow the stage. Four columns (Discover, Screen, Meet, Hire) with the CTAs and the "sold in bundles of features" note. Hire: close the ad.
9. What it means: each step of the hiring process gets its own information and its own actions.
10. How we see this: the four stages in one line each, the All applications lane and the Search initiative.
11. Candidate profile page: folders, CV always accessible, CTAs at hand; right side: layouts under review (collaborate, compare) and easier reading of seekers' files. No screenshots (too crowded).
12. Alignment with RPP: bundling and pricing with the Ecom team, promotional placements, contextual upselling (with example).
13. Prototype demo: Yassine.
14. What we are still working on: five items, with the hybrid UI screenshot.
- Rules kept: high level, no monetization detail on which features are paid, no figures.
- Old deck "ats-2.0" is kept untouched on the board.

### Open points
- [GAP] Hire stage: the information to prioritize is still to define (the main CTA, close the ad, is set). Slide 7 therefore has no Hire column.
- [GAP] Timing and scope of the All applications lane and the Search initiative.
