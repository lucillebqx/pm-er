# Invite to Apply

> Sources: Lucille Bouquiaux (history, MVP scope, Miro deck, open points; 17-18 Nov 2026) and meeting with Sally (PM, Profile team) for the seeker rules and flows.
> Status: MVP validated 11 Nov 2026. Staffing agencies affected.

## Summary

Base CV (legacy) -> idea of a new revenue stream -> invite to apply on ONE -> fake door test (prepared, never run) -> real version approved -> MVP in T2 (no monetization).

## 1. How we got here

### 1.1 Origin: Base CV

- Base CV was a system in legacy jobup. Recruiters could search profiles and invite them to disclose their identity.
- It worked quite well, but the company stopped it.

### 1.2 The idea: a new revenue stream

- Brainstorm to create another revenue stream, building on Base CV.
- The idea was developed into **invite to apply**, linked to a job ad published on ONE.
- It soon became clear this would be an expensive project.
- Decision: test the recruiters' appetite with a **fake door test** before investing.

### 1.3 The fake door test (prepared, never run)

**How it was designed**
- The Matching team created fake candidate profiles matching the job ad.
- After publishing a job ad on ONE, recruiters were to be shown the list of profiles, without knowing they were fake.

**Why**
- Measure the real appetite for the feature without spending much.
- Avoid "Monopoly money": if customers knew it was fake, the recorded behaviour would be worth nothing, because behaviour changes when it is your own money.

**Status**
- Almost ready to launch after a few rounds with Legal.
- Blocker: an A/B testing tool was needed to restrict traffic and limit noise from frustrated customers.
- The team started looking into a new tool (to be implemented in T3).
- Then we learned that business had prioritised the real version of invite to apply. The fake door test was never run.

### 1.4 The real deal: MVP in T2

- The real version was approved as part of the new strategy.
- Prices and costs of the project still matter, so in T2 we investigated an MVP with:
  1. No monetization.
  2. Actual candidates who opted in.
  3. Emails sent out and applications recorded.
  4. Free invites capped at 5.

## 2. MVP

### 2.1 Scope (from the Miro board)

- Online job ads only, no differentiation by product.
- Matches above a 40% CV Insights score, shown highest first.
- Invitation by email.
- ATS permission required for recruiters.
- Seeker side: invitation email with a main CTA to the application form and a consent page to opt out.

### 2.2 MVP decision (overrides meeting notes)

- Seekers **cannot choose which CV is visible** in this MVP.
- Impact on the flows below: no CV selection list in the opt-in popup, no "confirm CV visibility" popup for already opted-in seekers, no per-CV visibility management on the profile page.
- Open: which CV is shared by default (e.g. most recent CV, max 6 months old)? To be confirmed.

### 2.3 Customer journey

1. Seekers are invited by email; the template is not editable and is in the job ad language.
2. They reply via the quick apply form.
3. Applicants are identified in the ATS.
4. Online job ads only, no differentiation by product.
5. Feedback via surveys at every stage.

## 3. Seeker rules

- Logged-in seekers only.
- At least one CV is required (minimum = 1).
- Oldest CV allowed = 6 months old.
- Opt-in is valid until the seeker opts out.

## 4. Opt-in collection points

- Paramount point: the new unified opt-in the Seekers team is working on is the building block of the project. Without matches in our pool, we can't sell.
- This term we work with the Seekers team to finalize the process: opt-in on application, profile page and onboarding; opt-out on the profile page. Flows are in Frame 44 on the Miro board.

Can the opt-in be collected at each of these points, and remain valid in all cases until the seeker opts out?

| # | Entry point | Condition | Notes |
|---|-------------|-----------|-------|
| 1 | Application level | Once the application is sent, logged-in users | |
| 2 | Profile level | Seeker on Profile page | |
| 3 | Onboarding | Upon CV upload | |
| 4 | CV upload test page | Edge case | To be detailed later |

## 5. Flows by source of opt-in

### 5.1 Application

| Seeker state | Flow |
|--------------|------|
| Not opted in yet | Seeker sends an application, then an **opt-in popup** collects the general consent. ~~List of CVs to make visible (max 6 months)~~ (out of MVP) |
| Already opted in | Seeker sends an application. ~~Popup to confirm CV visibility~~ (out of MVP) |

### 5.2 Profile page

| Seeker state | Flow |
|--------------|------|
| Not opted in yet | Seeker goes to Profile page, then an **opt-in popup** collects the general consent. ~~List of CVs to make visible (max 6 months)~~ (out of MVP) |
| Already opted in | Seeker sees the CV shared. ~~Manage visibility (up to 6 months old)~~ (out of MVP) |

### 5.3 Onboarding

| Seeker state | Flow |
|--------------|------|
| Not opted in yet | Seeker follows onboarding. Once the CV is uploaded, the opt-in is collected. Then the normal process continues (profile or apply). |

### 5.4 Opt-out

- Seeker opts out of the invite-to-apply service on their profile page.

## 6. Legal questions (still under legal review)

- [ ] Default opt-in or default opt-out?
- [ ] Once the seeker opts in, are we allowed to:
  - create matches based on the shared CV?
  - suggest the relevant matches to recruiters?
- [ ] Edge case: can we create our own "match profile" per opt-in, and update seeker information as they apply to job ads (and send updated CVs)?
- [ ] Cross-platform opt-in (jobs.ch / jobup.ch): what is allowed?

## 7. Profile relevancy

- CVs cannot be kept forever, as they are not relevant after a couple of years.
- Do not present CVs older than 6 months.

## 8. Matches: jobs.ch vs jobup.ch

### Principle

- Recruiters do not care about the source platform.
- As long as a match fits the criteria, a jobs.ch match can be presented for a jobup.ch job ad (and vice versa).
- Do not present jobs and jobup matches separately.

### Duplicates (edge case)

- Share of seekers with profiles on both platforms: ~10% (exact number TBC).
- The system must handle this case and never present the same person twice.
- Proposed method: email address verification.

### Match without a profile on the other platform

- Some job ads have no login wall: the seeker can apply directly.
- Other job ads have a login wall: the seeker must log in or register.
- Open: exact behaviour to define per case.

### Legal

- [ ] Cross-platform opt-in (see section 6).

## 9. Open points (T3)

1. Monetization and invoicing: Ecom team and Integrations team in T3. Credit card payment is not part of phase one.
2. Pricing of the matches: following the VBP pricing tables will be studied. Does it make sense, and how to make it work given that VBP does not cover all job ads?
3. Contextual upselling: where and how to promote? Examples: an automatic trigger of invite-to-apply for recruiters whose job ad has not attracted enough qualitative profiles; on job ad creation, if the seeker market for the ad is too small, tell the recruiter to use invite-to-apply and save time.
4. Apply journey: thinking about a "one-click apply" to bypass any barrier in the application journey. The more accepted invites, the more money.
5. Surveys: collect feedback from customers correctly at every stage and make sure the data is read correctly afterwards.
6. Reporting: last point but crucial to understand customers' appetite for the feature. Look at how recruiters interact with the product and who is interested (industry, company size, region, product chosen, job ad, etc.).

## 10. Open questions / next steps

- [ ] Which CV is shared by default, given no seeker choice (MVP)?
- [ ] Legal answers: default opt-in/out, matching permission, match profile, cross-platform opt-in.
- [ ] Exact share of seekers on both platforms.
- [ ] Behaviour for matches with no profile on the other platform (login wall vs direct apply).
- [ ] Detail the CV upload test page flow.

## 11. Miro deck

Deck "Pay per Invite - MVP (new)" (17 Nov 2026, below the previous deck; the previous deck and its copy are kept):
1. Title: invite-to-apply.
2. The vision: publish, discover, invite, respond, pay.
3. Why we are doing this: time-based sales today, recruiters want the right people, a new monetisation model.
4. How we got here: From Base CV to the fake door (origin, idea, catch, fake door, goal).
5. How we got here: From the fake door to the real deal (almost ready, blocker, shift, MVP in T2, scope).
6. Solution design behind the MVP (copied as the team left it: check marks, hourglass on "Manage the consents").
7. MVP customer journey (section 2.3).
8. UX: special cases and the survey (examples for the surveys).
9. Live demo by Luciana.
10. Opt-in and out - still under legal review (new slide, 18 Nov 2026; sections 4 and 6).
11. Open points (T3), reworked 18 Nov 2026 (section 9).
