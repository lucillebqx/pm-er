# CV Insights score - Term III 2026

Initiative: display the CV Insights score on every application in the JobCloud ONE ATS and let recruiters sort applications by score, delivered in Term III 2026.

Status: READY FOR DELIVERY 
Sources: fact base, compiled 24 Nov 2026 from Lucille's input in chat and existing workspace files ([matching.md](../setup/company/matching.md), [ats-rethinking.md](../setup/company/ats-rethinking.md), [invite-to-apply.md](../setup/company/invite-to-apply.md), [job-ad-monetizations.md](../setup/company/products/job-ad-monetizations.md)).
Legend: [Lucille] = stated by Lucille. [Workspace] = taken from another workspace file. [Miro] / [Figma] = from the board or mockups, via ats-rethinking.md. [GAP] = not found, needs input.

## 1. Scope for Term III 2026

- [Lucille] The CV Insights score is implemented in the JobCloud ONE ATS this term (Term III 2026).
- [Lucille] The score is displayed on all applications. 
- [Lucille] Recruiters can sort applications by score, so they review the most relevant applications first.
- [Lucille] Mockups: [Figma, file "Domain", node 23038:16720](https://www.figma.com/design/E0KNkqNGoDtoJ0hatLjZKi/Domain?node-id=23038-16720).
- [GAP] Mockup content (score display, sort control, states) not extracted yet.

## 2. Background: CV Insights (live)

- [Workspace] CV Insights (internal alias: Jobfit) is owned by the Domain Team.
- [Workspace] It analyzes CVs against job ads and gives recruiters concise feedback on how well a candidate matches a role, highlighting key skills and experience relevant to the job ad.
- [Workspace] Why it matters: cuts the time recruiters spend manually reviewing each CV in the initial screening phase; faster, fact-driven decisions; less time on unsuitable applications without compromising quality.
- [Workspace] Availability in the JobCloud ONE ATS: all job ads, live or offline, free or paid, published after 9 Oct 2025.
- [Workspace] Output:
  - Presentation of the candidate: a concise professional persona, focused on recent experience and structured progression.
  - Suitability highlights: key strengths, skills and experience that make the candidate a good fit.
  - Unmet requirements: areas where the candidate may not fully meet the job's expectations.

## 3. The CV Insights score

- [Workspace] Status before this term: not live, ongoing with the delivery team.
- [Workspace] Goal: help recruiters quickly prioritize the candidates who best match their requirements, so they focus on the most qualified applicants first.
- [Workspace] Output: a visual indicator of the application's fit to a job ad.

## 4. Where the score is used across initiatives 

- [Workspace] Invite to apply (MVP): only matches above a 40% CV Insights score are shown, highest first.
- [Workspace] Job ad monetization Value-based-pricing (VBP): only "suitable" applications are billed; suitability is based on a minimum CV Insights score.
- [Miro] (future) ATS rethinking: the score and summary are in the "Mandatory" information set of the ATS.


## 5. Research signals (ATS rethinking, think-aloud sessions Sep 2026)

- [Miro] Trust in the fit score is low: "94% match plus 2 lines" isn't enough; recruiters want to see which criteria drove it.
- [Miro] Labels "Recommended for you", "Shortlist" and "Suitable" overlap and confuse.
- [Miro] Banner blindness on recommended candidates.
- [Miro] Recruiters need fast filter / sort at 60 to 100+ candidates.
- [Miro] Quick win already done: CV Insights unavailability explanation.

## 6. Monetization context (ATS rethinking, not decided for this initiative)

- [Lucille] The CV Insights score is listed among the features that could be monetized in the future - provided that we can trust the score. 
- [Lucille] (future) Decision in the ATS rethinking: fit sorting stays in the Plus tier; the free tier shows the top 3 applicants at the top of the list as a teaser.


## 7. Open questions [GAP]
[Lucille]  Chris Otto should provide documentation on how the score is calculated (inputs, criteria, weighting)?  (Lucille's input)
[Lucille] we chose not to display actual percentages of fit but divided the scores in four categories of fit and will display the fit in a gsm-bar way. 
[Lucille] Applications without a score are displayed as such https://www.figma.com/design/E0KNkqNGoDtoJ0hatLjZKi/Domain?node-id=18809-100666&t=4P5IyicN0dPYEIoF-0
[Lucille] Applications wihtout a score are displayed at the bottom of the list sorted by CV insights score. 
[Lucille] Default sort remains "application date" with the latest applciations received first. 
[Lucille] Domain Team is the delivery team.
Open - Release date within Term III 2026, and success metrics.


## 8. Work in progress 
Reporting and success/performance measurement needs to be done by PM

Question	Metric
Is the score accurate?	Suitable rate per fit level (expected: it rises with the level)
Is the score accurate?	Unsuitable rate in the top fit level
Is the sort useful?	Share of recruiters who use the sort, and whether they keep it on
Is the sort useful?	Time to first stage move: sort vs date
Do recruiters trust it?	Switch-back rate to date sort