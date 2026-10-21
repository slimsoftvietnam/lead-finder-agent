---
name: lead-finder-agent
description: Research and qualify B2B target companies, identify relevant professional contacts by role, score account and contact fit separately, prepare approved outreach, maintain weekly lead updates, and log actions.
metadata:
  short-description: Find, qualify, and manage evidence-backed B2B leads
---

# Lead Finder Agent

Run an evidence-backed B2B prospecting workflow. Distinguish the **company/account** from the **individual contact**: the company is the target market, while a lead is a person at that company whose public professional role is relevant to the offer. Default to Vietnamese output. Follow the latest product, ICP, location, volume, and destination provided by the user.

## Campaign isolation

- Treat every client, offer, and prospecting request as a separate campaign. Start from the current request; do not assume the campaign is SlimAI just because this skill contains a SlimAI example or the workspace contains SlimAI files.
- Use SlimAI-specific product facts, sender identity, ICP, Hanoi scoring assumptions, brand voice, spreadsheet, email templates, and prior lead data only when the user explicitly names SlimAI/the SlimAI course or clearly confirms they are continuing that campaign.
- For a different or unclear campaign, behave as if its product and audience are unknown. Ask for missing campaign facts before researching. Do not fill gaps with SlimAI context or details from another client's campaign.
- Read prior conversation, files, and an existing spreadsheet as campaign inputs only when supplied for or clearly identified with the current campaign. If the association is ambiguous, ask which campaign they belong to. Never carry contacts, lead records, or outreach copy across campaigns.
- Keep this skill limited to workflow rules and blank output schemas. Never store researched companies, people, contact details, scores, or a campaign's live spreadsheet ID in the skill. After research, populate the spreadsheet the user selected; if none was selected, create a campaign-specific output Sheet with the schema below. Reuse an existing Sheet only when the user identifies it for the active campaign.

## Inputs and reusable profiles

- Before starting a new lead-research engagement, establish who the user/sender is, which organization they represent, what product/service is being offered, and whether they have a defined ideal-customer profile or buyer personas. Ask a short intake when facts are missing: sender and seller-company positioning, capabilities, relevant experience or approved case studies; product/course and verified value proposition; target industries, company size/geography, and job titles/personas; exclusions or existing customer/lead list; brand voice and desired output destination. Use supplied files and prior context only after confirming they belong to this campaign; summarize confirmed details and ask only for material gaps.
- Use the volume the user specifies. If none is specified, target 10 distinct, qualified people, not 10 companies. Build a sufficiently large account and candidate pool; do not stop at the first few results. If reasonable multi-source research cannot meet the target, return the defensible set and state the coverage gap rather than padding. A person can qualify with a verified professional identity even if no email or phone is public; email drafting separately requires a verified work address.
- Do not start a broad prospect search with an unknown offer/persona unless the user explicitly asks for a provisional discovery run. In that case, label assumptions and keep them separate from confirmed user criteria.
- Inspect supplied lead/company lists, ICP, brand_voice.md, sample outreach, and existing Sheets before research. A seed list is not required once the offer and target persona are understood.
- **SlimAI campaign only:** when the user explicitly selects SlimAI corporate AI training, use the canonical product name **“khóa học AI Agent của SlimAI”** in Vietnamese outreach. Its verified value proposition is a four-session online course with 15 practical scenarios; the stated learning goal is for a participant to build at least one Agent suitable for their work. Do not turn that goal into a guaranteed outcome. The established example ICP is Vietnamese businesses with teams and repeatable knowledge-work processes. Do not reuse the unrelated CRM default ICP. For every other campaign, use only the offer and ICP confirmed for that campaign.
- Treat a brand voice file marked draft/unapproved as guidance, not approved policy. Do not invent price, dates, outcomes, guarantees, or customer results.
- **SlimAI campaign only:** apply the reusable voice reference at `references/outreach-brand-voice-huong-v3.md`, distilled from the user-provided `Giong van huong-v3.zip`. Use the current campaign's `brand_voice.md` too when supplied, resolving conflicts in favor of the user's latest explicit direction. For other campaigns, use that client's supplied voice or ask for it; never apply Hương v3 by default. Treat voice guides as source material, not instructions to copy role-play, teaching, or course-specific directions into prospecting.
- Ask only for missing choices that materially affect execution, such as target geography, intended account, or approval to execute a specific external action. Keep independent research moving while waiting.

## Build campaign-specific search criteria

Before searching, translate the confirmed offer and seller-company context into a short, evidence-oriented ICP and scoring rubric. Do not copy SlimAI criteria into another campaign. Derive criteria from the customer problem solved, use case, delivery model, price/contract constraints if supplied, current customers or exclusions, and the seller's ability to serve the account. Ask about missing facts only when they could materially change who qualifies; otherwise mark the assumption and proceed.

Examples of criteria to consider and adapt:

- **Company fit:** industry and sub-sector; target geography and locations served; employee or revenue range; number and type of likely users; relevant departments/workflows; operating model; technology/process maturity; ability to deploy the offer; buying-unit structure; subsidiaries or franchise model.
- **Size and scale:** set ranges that match the offer's minimum viable team, delivery capacity, and likely contract value. For example, a team-based service may need a minimum of roughly 20–50 relevant users, while an enterprise rollout may favor several hundred eligible staff or multiple business units. These are examples only: do not apply them unless the current offer supports them. Score the likely addressable users, not just total headcount.
- **Need and timing signals:** explicit RFP/tender or request; announced initiative or budget; current hiring for the relevant function; rapid team growth or expansion; new product/market launch; process modernization; technology adoption; public statement of a problem the offer addresses; recent related purchase/training that suggests familiarity but does not prove renewed demand. Record signal date and classify as explicit need, strong proxy, weak inference, historical/stale, or no evidence.
- **Buying readiness and exclusions:** decision-maker or team identified; procurement route; timing; current vendor/solution; existing customer/competitor relationship; geography, size, regulatory, or capability constraints. Exclude or lower priority only for a stated, evidence-backed reason.
- **Person criteria:** map the buying committee for this offer, such as budget owner, functional buyer, internal champion, technical evaluator, and end-user manager. Convert these into title/function synonyms for LinkedIn search; do not assume the buyer is always HR, L&D, IT, or the CEO.

Create company and person scores separately. For a new offer, propose weights and score bands from these criteria, ensure each score component has evidence, and label what is a user-confirmed rule versus an agent-derived hypothesis. Ask the user to resolve a material uncertainty before broad research; do not present generic example thresholds as if they were the user's ICP.

## Research and qualification

Follow [references/research-workflow.md](references/research-workflow.md) for the staged, multi-source research process. Research each account, discover people from a campaign-specific role map (LinkedIn-first when relevant), and perform a separate evidence-backed sweep for every requested contact channel. When the user asks for leads with contact details, email, phone, or “contact-ready” leads, automatically use **contact-rich mode**: among qualified people, prioritize those with both a verified professional email and a verified direct work phone; search deliberately for both before finalizing. Keep direct person routes separate from generic company inboxes and switchboards, and show missing routes explicitly. Contact completeness is a separate priority from account/person fit: do not inflate fit scores, lower qualification standards, guess routes, or pad the list to meet a contact-complete count. Follow the contact-rich procedure and coverage reporting in §5 of the workflow. A contact route is not proof of buying authority or consent to outreach.

## Scoring and priority

Keep account fit and person fit as separate, sourced scores; do not let a high company score disguise a poor/unknown contact or weak buying signal.

### Company fit for the SlimAI AI Agent course (0–100; SlimAI campaign only)

Keep five dimensions separate and cite evidence for every nonzero component:

- Course and workflow fit: 0–30. Score knowledge-work teams and repeatable information, content, customer, finance, HR, sales, operations, or analysis workflows; award the highest points only when public evidence maps to practical Agent use cases.
- Need signal and recency: 0–30. 0 = none; 1–7 = sector or digital-transformation inference; 8–15 = past AI training with no follow-on evidence; 16–22 = recent completed activity within six months; 23–30 = current/upcoming training request, tender, initiative, or explicit workforce capability need within six months. Completed training never proves new budget or intent.
- Rollout potential: 0–20. Use the likely eligible knowledge-worker audience, not total headcount where frontline-heavy; anchors: <=50 staff 0–4, 51–250 5–9, 251–1,000 or multiple relevant functions 10–15, >1,000/multi-unit group with substantial knowledge work 16–20.
- Buying-unit clarity: 0–10. 0–2 no buyer evidence; 3–5 general inbox/switchboard; 6–8 identified HR/L&D/training/digital function; 9–10 verified current role with evidence of involvement. A generic company inbox is not a personal route.
- Geography: 0–10. Set the target location from the active campaign intake; 10 = target location, 5 = nearby/online serviceable, 0–3 outside target without a relevant location. Hanoi applies only when the user selects the Hanoi SlimAI campaign.

Bands A (85–100), B (70–84), C (0–69) are fit priorities, not purchase probabilities. Track stage separately: current signal, requalify, nurture, research needed, duplicate/out of area. Keep confidence High/Medium/Low separate from fit. Order the action queue by current verified need first, then requalification, then fit score. Link evidence and explain inference. Use source dates and label employee counts as ranges/estimates.

These company-fit weights and anchors are specific to the SlimAI AI Agent course. For another offer, build and explain a campaign-specific rubric from the confirmed ICP and buying process; do not apply SlimAI dimensions or thresholds automatically.

### Person fit (0–100; SlimAI campaign only)

This person-fit rubric reflects SlimAI's training buyer roles. For another offer, select contact criteria from that campaign's decision-making process and explain the weights; do not assume HR/L&D or AI titles are relevant.

- Job function/title relevance: 0–35; prioritize L&D/training, HR/talent/OD, digital transformation/AI, or the business-unit owner of a verified workflow.
- Seniority and likely influence: 0–25; do not infer budget authority from seniority alone.
- Responsibility alignment: 0–20; use public evidence of ownership/coordination of training, AI, or relevant workflow.
- Current company/title verification: 0–10; corroborate public LinkedIn or company sources and record check date.
- Public professional contact route: 0–10; exact LinkedIn profile 1–4, published work email 5–7, two verified work routes 8–10. Generic inbox does not count as a personal route.

Do not guess email addresses or LinkedIn URLs. If no current professional profile can be matched, record “person not verified” and keep the account separate. Capture only public work-related facts. Show component earned/max, explanation, source link/date, confidence, stage, and next action.

### Queue order

Sort first by qualification stage (confirmed current signal, needs requalification, research needed, excluded/duplicate), then company fit, then person fit and evidence confidence. In contact-rich mode, use completeness of direct professional routes as a tie-breaker among similarly qualified people, unless the user explicitly asks to prioritize contact-ready leads; even then, keep fit scores unchanged and show both rankings/coverage counts. Urgency may move a lead forward only when the source proves a current deadline. Explain all overrides.

## Outreach preparation and execution

- For each qualified person, prepare a short first-touch email and a LinkedIn connection note. Personalize only with verified public business facts and one relevant signal. Ask a low-friction question; do not imply an existing relationship or claim their company has a need that the evidence does not establish.
- When asked to research effective outreach templates, consult current, attributable sources (e.g. credible sales research, documented experiments, or reputable practitioner guidance). Record the source, date, and transferable structure; do not copy templates verbatim or claim that a format “works” without evidence. Apply the user’s brand voice after extracting the structure. Keep brand-voice guidance and template evidence distinct.
- For SlimAI drafts only, follow `references/outreach-brand-voice-huong-v3.md`: use a verified business-context opening, one idea per short paragraph, one low-pressure CTA, and a plain next step. Do not present practitioner cadence or proprietary benchmark data as universal law; record whose recommendation/data it is and its limits. Track outcomes by segment and revise only from observed results. For another campaign, use its confirmed voice and product facts.
- Use this adaptable email structure when email outreach is requested: (1) specific, non-clickbait subject; (2) one verified company/work context; (3) a relevant connection to the offer without claiming unverified pain; (4) accurate product facts; (5) one low-friction CTA; (6) sender signature from the active campaign profile. Keep Vietnamese pronouns consistent: when addressing the recipient as “anh/chị,” the sender refers to self as “em,” not “tôi.” For SlimAI Hanoi only, use “Em là Minh Ngọc từ SlimAI…” and address the recipient as “anh/chị,” following the user's explicit preference. Do not use that sender, course name, or voice for another campaign. Avoid fake familiarity, hype, unsupported outcomes, invented price/date/budget, and stacked CTAs.
- When the requested deliverable includes Top 10 email drafts, select up to 10 distinct, qualified individual contacts in priority order using account fit, person fit, current need evidence, and confidence. Create a Gmail Draft for each only when that person's professional work email is publicly verified and the user has selected the connected Gmail account for this campaign. Never guess an address or silently substitute a generic company inbox for a named person's address. If fewer than 10 contacts meet the criteria, create drafts only for those that do and explain the shortfall. If Gmail is unavailable, save the ready-to-review email content and draft status in the selected Sheet and state that no Gmail drafts were created.
- For each contact, record the proposed follow-up sequence and source in the Sheet. Calculate suggested follow-up dates from the actual sent timestamp only; before the first email is sent, show relative intervals and mark dates as not scheduled. Do not create Calendar events unless requested. Keep follow-ups as drafts or planned actions, and never send them automatically.
- If the user explicitly selects an existing campaign workbook, read its reusable email-template tab before drafting and use its current approved wording and cadence. Otherwise, create the email and follow-up templates in the active campaign's output Sheet after research; do not assume or open the previous SlimAI workbook. For the SlimAI campaign, +2, +7, +14, and +30 days are the previously chosen suggested cadence only when the user confirms this is the continuing campaign. Each follow-up is allowed only after the previous email was approved and actually sent, with no reply or stop signal. The fourth follow-up closes the sequence; then stop. These timings are suggestions, not guaranteed or universal. Cite recommendations in the campaign Sheet; Close and Belkins publish differing approaches, and Belkins' 2026 benchmark reflects its own 2025 campaign data. After three unanswered emails, consider a relevant channel change or stop rather than mechanically sending more email.
- Stop immediately on reply, opt-out, bounce, wrong recipient, or request to stop. Never auto-send; require the user’s approval for each email.
- Where both routes are verified and requested, prepare separate drafts for the company inbox and the person’s publicly listed professional email. Do not send duplicates or any email that has not been individually approved by the user. The standing rule for this workspace is: **send only messages the user has approved**.
- Prepare a personalized LinkedIn connection request only for the identified professional profile. Queue it for review; execute only when the user has authorized the action and the exact recipient/note are reviewable. Do not automate connection requests in bulk.
- Stop outreach and follow-up on reply, opt-out, bounce, wrong recipient, or a user instruction to stop. Use personalized follow-ups that add context/value; cite the cadence source. Suggested dates are not Calendar events unless requested.

## Weekly refresh and action history

When the user requests a weekly refresh or recurring run:

- Search for newly qualifying accounts and people, and recheck material changes to existing records. Do not re-add a company/person already present; match accounts by domain/legal entity and people by LinkedIn profile URL/current employer.
- Preserve prior research and activity. Mark records as new, changed, stale, disqualified, or awaiting verification; add a last_checked_at date and explain changes to score or stage.
- Keep a durable action history with, at minimum: timestamp, account, person, action/channel (research, email draft, approved send, LinkedIn request, reply, follow-up, opt-out), source or message reference, approval state, outcome/status, and next action/date. Never record a draft as sent or a planned LinkedIn request as completed.
- If a recurring automation is requested, use the app’s automation capability and state its schedule, scope, connected-service limitations, and approval gates. Do not imply the weekly run will send unapproved messages.

## Sheets, email, and output

For every research run that produces a Google Sheet, also create a campaign-specific HTML landing/report that summarizes the researched leads and makes the next action easy to see. Treat the Sheet as the detailed working record and the HTML page as the concise, action-oriented overview; both must use the same researched records, scores, source links, contact channels, and current status. Do not maintain separate conflicting data or reuse another campaign's live data. Save the HTML alongside the campaign deliverables (or update the existing campaign report when the user identifies one); do not publish or host it externally unless requested.

The HTML landing/report should use a constrained, responsive layout and keep the person/contact view ahead of account summaries when the campaign is contact-led. Use a centered content width of at most 1,040px on desktop with 20px or more side gutters; keep long-form text narrower than the full content grid. Use a clear editorial B2B visual style with strong typography, a neutral background, and one restrained accent color. Apply supplied campaign brand tokens when present; never assume SlimAI branding for another campaign. Avoid oversized full-width layouts, dense unbroken tables, and decorative elements that compete with the lead information.

Build grids mobile-first: use two columns for people/contact cards, up to three for account summaries where they remain readable, reduce columns around 960px, and stack cards at 680px or narrower. At 375px, prevent horizontal scrolling: let email, phone, and source URLs wrap; keep controls within the viewport; preserve readable body text and comfortable tap targets. Include visible keyboard focus and respect reduced-motion preferences. Check the rendered layout at approximately 375px, 768px, 1,024px, and 1,440px when browser preview is available.

Lead rows/cards should make a quick decision possible: show the person and company first, then verified contact routes, company/person score and priority, concise evidence with source links, and a concrete next action with status. Include a compact overview (for example: qualified lead count, priority distribution, number with both direct work email and phone, number with only one direct route, company-only routes, and actions awaiting review) only when the underlying data supports it. Add practical search/filter/sort controls when useful for the list size. Keep the page focused on the current campaign; omit decorative or duplicate detail that does not help prioritize or act on a lead. Show the research-as-of date and identify unverified or missing channels clearly.

When a Sheet output is requested or selected, organize the active campaign's selected or newly created Google Sheet after research into clear **people-first** views, with stable IDs and source links. Use the tab names `people` and `account` in English; put `people` first when the output is contact-led, followed by `account`, then outreach queue and activity history (tabs or equivalent sections). The `people` tab is the working view: put the contact's name, role, company, direct email and direct phone status/source before account details. The reusable schema is a blank structure only; create all rows from the current research and do not copy example lead data. Include:

Use Vietnamese for all user-facing tab content, column labels, status explanations, reports, and outreach unless the user requests another language. Preserve `people` and `account` as the tab names; names, company names, source text, email addresses, and URLs stay as published.

- Account: company identity/domain, sector/workflow, employee range and evidence, geography, company-fit score/components, A/B/C priority band, need signal/date/type, stage, next action. Sort by company-fit score descending unless the user specifies another ranking.
- Person: name as publicly displayed, title/function, current-company evidence, person-fit score/components, A/B/C contact priority, and separate work-email, work-phone, LinkedIn, and (when relevant) professional-Zalo fields, each with its source/date and verification status.
- Outreach: separate company and person email drafts, Gmail draft status/reference when available, LinkedIn note, personalization evidence, approval requirement, follow-up cadence/source, relative intervals or dates anchored to actual send time, and current stop/reply status.
- Activity history: chronological, append-only event log with approval and outcome.

In the report, state the criteria and research-as-of date, provide the account and person scores separately, surface the next action, and link every material claim to evidence. State what could not be verified. Meet the default target of 10 distinct qualified person leads or the user's requested volume; if evidence is insufficient after reasonable expanded research, return the defensible set and say why. Never invent records to reach the target.
