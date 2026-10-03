# Travel Buddy — Submission Paper
**Module:** User Experience Design – Principles & Methods | **Assignment:** Alternative C (MUXDCI)

> Expanded draft, written toward the full ~20-page scope. Two things remain genuinely open and are stated plainly throughout rather than smoothed over: the card sort (Section 5.1) is designed but not yet run, so the information architecture in Section 5.2 is a hypothesis; and the moderated usability round (Section 7.1) was an AI-simulated pilot pending real participants, so the findings in Section 7.2 are hypotheses for a real test, not validated findings.

---

## Introduction

Travel Buddy is a mobile experience platform designed to help people discover places, connect with locals, and plan and share travel experiences. Unlike existing platforms that serve one part of the travel journey, Travel Buddy integrates three pillars — Discover, Connect, and Plan & Share — into a single, coherent experience.

Travelers today rely on multiple disconnected apps, distrust commercially biased review platforms, and lack a free, authentic way to connect with local people at their destination. Existing solutions each serve one pillar well but leave the others unaddressed — a gap confirmed through competitive analysis and grounded in ten research hypotheses developed prior to primary data collection.

This submission documents the end-to-end UX strategy for Travel Buddy, following the Double Diamond process model. It moves from research and stakeholder analysis (Sections 1–3), through feature definition and information architecture (Sections 4–5), into prototyping and usability testing (Sections 6–7), and concludes with a strategic reflection on the full UX value logic (Section 8).

The project applies two primary research methods — a quantitative user survey and semi-structured qualitative interviews — alongside competitive SWOT analysis of five established travel platforms. Design decisions throughout are grounded in research findings rather than assumption, and where evidence is thin (a single completed interview, an under-sized survey), that limitation is named rather than papered over.

---

## 1. Process Framing & Planning

Travel Buddy follows the **Double Diamond** process model — discover, define, develop, deliver (Dippner, 2022, Ch. 4.2) — rather than a purely agile sprint model, because the project sits at the intersection of two conditions that a sprint-first approach handles poorly: it is greenfield (no existing user base, no legacy product to iterate from) and it is multi-pillar (Discover, Connect, and Plan & Share are three distinct value propositions, each already owned by a different competitor — TripAdvisor/Google Maps for discovery, Polarsteps for journaling, Airbnb Experiences for connection; Section 3.3). A sprint model optimizes for building fast once scope is known; it does not answer the prior question of *what* to build, or in what proportion, across three pillars that no single competitor combines. That question could only be answered by a genuine divergent research phase before convergence on a build.

Lean UX principles govern the pace inside that frame: rather than one long discovery phase followed by a single define phase, research ran as a rolling build-measure-learn cycle anchored to ten pre-registered hypotheses (H1–H10, `01_Research_Hypotheses.md`) spanning all three pillars — review distrust and app fragmentation (H1–H3), non-transactional connection and trust barriers (H4–H6), low-effort journaling and flexible planning (H7–H9), and switching cost (H10). Each hypothesis was written before data collection specifically so that disconfirming evidence could reshape scope rather than be absorbed into it.

That reshaping happened visibly. Before primary research, the four traveler archetypes (Explorer, Cultural Connector, Documenter, Pragmatic Planner) were treated as roughly co-equal, and journaling — read as the most emotionally resonant pillar — was assumed to be the leading feature. Two convergence events changed this. First, when the P1 interview participant named fragmentation across 8–10 apps per trip as "the single most important problem," and reported manually retyping information from TikTok into Google Maps into a Google Sheet into ChatGPT and back, trip planning was promoted from a supporting feature to the primary one — confirmed when the expanded survey (n=13) subsequently ranked Trip Planning first in feature importance (4.38/5), up from last place (3.00/5) in the earlier n=8 pull. Second, the Pragmatic Planner archetype was folded into the Explorer persona (now Aisha) rather than kept separate, because the data showed the same person exhibits both behaviors — careful upfront research and constant on-the-ground flexibility (H9) — rather than these being two distinct user types. Third, AI tools (ChatGPT, Gemini), initially treated as outside the competitive frame, were reclassified as both a contributor to fragmentation and a design opportunity once P1 confirmed active use of them mid-planning. This is the diverge/converge movement the Double Diamond is meant to make visible: scope narrowed and reordered *because* of evidence, not despite it.

**Table 1. Strategic objectives.**

| # | Objective | Evidence basis |
|---|---|---|
| SO1 | Reduce trip-planning fragmentation by unifying discovery, connection, and journaling in one platform | H3: travelers use 3+ apps/trip; P1 confirmed 8–10 tools/trip with manual transfer between each. No competitor spans all three pillars — TripAdvisor/Google Maps own discovery, Polarsteps owns journaling, Airbnb Experiences owns connection (comparative matrix, Section 3.3) |
| SO2 | Replace commercial bias with peer-sourced trust as the primary discovery signal | H1: local tips trusted 4.46/5 vs. 3.38/5 for platform star ratings, 3.31/5 for stranger reviews (n=13); 10/13 respondents disappointed by a highly-reviewed place; TripAdvisor's fake-review weakness (The Strategy Story, 2024) |
| SO3 | Enable authentic local connection without a transactional paywall | H4/H5: 12/13 open to local connection; verified identity (11/13), no monetary exchange (9/13), and shared interests on profile (8/13) are near-required comfort factors; Airbnb Experiences' structural gap — every local contact requires a paid booking (Streetwise Journal, 2024) |

## 2. Stakeholder Ecosystem

### 2.1 The Three-Ring Model

Stakeholders are "all people who have a specific knowledge that the design team needs to build, use, or operate a successful system that fits the business goals" (Dippner, 2022, p. 33, based on Spies, 2014) — deliberately not the end users of the product, but the people around it whose knowledge, decisions, and constraints shape what gets built. Travel Buddy's stakeholder map places each individual by influence and proximity to the product core (Spies, 2014), across three rings.

**Core** — daily decision-making power. The **Product Owner/Founder** holds the business model, funding constraints, and competitive positioning, and makes final calls on roadmap; their long-term view is a globally recognized social travel companion monetized through premium subscriptions and B2B partnerships. The **UX Lead** holds user behavior and interaction knowledge and translates research and business goals into the actual product experience, aiming to make Travel Buddy a design-quality benchmark in the category. The **Tech Lead/CTO** holds infrastructure, API, security, and performance-tradeoff knowledge, and is accountable for a stable, modular system that can add features without full rebuilds — including offline functionality, a stated technical priority.

**Direct** — domain expertise that shapes delivery without owning the decision. The **Marketing Lead** holds audience segmentation and channel data and wants launch positioning that clearly differentiates from TripAdvisor and Airbnb, building an organic community rather than a paid-acquisition funnel. The **Business Development Lead** holds partner-expectation and revenue-structure knowledge, targeting 20+ local business partnerships before public launch and a self-sustaining partner ecosystem long-term. The **Investor Representative** holds funding benchmarks and comparable-startup valuations, and is oriented around measurable growth metrics (DAU, retention, conversion) and a clear monetization path within 18 months toward Series A readiness.

**Indirect** — constrain the project from outside without direct involvement in daily decisions. The **Legal & Compliance Officer** holds data-residency, consent, and liability knowledge, wanting zero compliance violations at launch and a legal framework that scales across the EU, Southeast Asia, and the US. **App Store representatives** (Apple/Google) hold platform-specific guidelines (HIG/Material Design) and review policy, and gatekeep distribution on the basis of policy compliance and accessibility. **Tourism Boards & Industry Partners** hold destination statistics and seasonal demand data, and want their destinations represented authentically to attract "quality" travelers rather than volume.

### 2.2 Stakeholder Tensions Relevant to Design

Four tensions surface repeatedly and each maps to a concrete design constraint rather than an abstract disagreement:

- **Speed vs. quality** (Product Owner vs. UX Lead): the founder's pressure to reach market and demonstrate traction pulls toward shipping more surface area faster; the UX Lead's mandate is a coherent cross-pillar experience. Resolved by keeping MVP scope deliberately narrow (Onboarding + Dashboard + three core features) rather than letting roadmap pressure expand it.
- **Monetization vs. user trust** (Investor Representative vs. UX Lead): the investor's 18-month monetization clock creates pressure toward premium gates or engagement-maximizing patterns; the research base (H1, H4) shows the product's entire value proposition rests on being perceived as non-commercial and non-manipulative. Resolved by ruling out dark patterns and requiring that any premium tier add genuine value rather than withhold baseline functionality.
- **Content authenticity vs. business partnerships** (Marketing Lead vs. Business Development Lead): BD's incentive to secure 20+ local business partnerships creates pressure to surface sponsored or partner content prominently; Marketing's positioning promise is "anti-algorithm" and human-first. Resolved by ensuring local guide and peer-sourced content is never displaced or diluted by commercial listings in the discovery feed.
- **Technical feasibility vs. design ambition** (Tech Lead vs. UX Lead): offline mode and real-time local matching are both technically demanding — offline requires local data caching and conflict resolution; real-time matching requires location infrastructure and safety verification at speed. Resolved by treating both as items needing early feasibility spikes before being locked into the MVP feature set, rather than assumed as given.

### 2.3 User Personas

Three personas were developed — one per pillar — because the survey data (n=13) confirmed the pillars represent genuinely different needs rather than variations on one user type (`06_User_Personas.md`). Each persona is grounded in survey clustering plus the P1 interview, not invented detail.

**Aisha, 26 — The Explorer / Pragmatic Planner (Trip Planner).** Content coordinator, Kuala Lumpur; 1–3 trips/year, mixed regional and international, comfort-oriented travel focused on food, culture, and sightseeing. *"I look things up before I go, build a whole planner, and still end up winging 30% of it once I'm there. The problem isn't finding information — it's that I have to collect it from everywhere myself."* Aisha builds a Google Sheets planner before every trip — budget, restaurant shortlist, rough itinerary — sourced across Google, TikTok, ChatGPT, YouTube, Facebook travel groups, and Google Maps, sometimes all in one sitting: she finds a restaurant on TikTok, drops the pin on Maps, confirms it in a Facebook group, then retypes it into her spreadsheet. The plan that results is solid but built through raw manual effort rather than good tooling, and once she lands she still improvises 30–40% of her best moments. Goals: find places worth going to rather than merely highly reviewed; assemble a plan without stitching together six apps; come home with memories she can actually retrieve. Frustrations: moving information between apps is the single most time-consuming part of planning, and nothing fixes it; AI drafting tools generate good itinerary ideas that then have "nowhere to go"; she cannot reliably tell a local's tip from a one-time tourist's. She represents the persona reframe that followed the P1 interview — originally treated as a separate "Pragmatic Planner" archetype, folded into Aisha once the data showed the same traveler exhibits both behaviors. Primary feature: Trip Planner. Hypothesis links: H1, H2, H3, H9. Key data: local-tip trust 4.46 vs. 3.38 platform rating (n=13); 9/13 cite "hard to find authentic experiences"; Trip Planning rated the #1 feature (4.38/5); P1 confirmed 8–10 apps per trip with fragmentation named as the single most important thing to fix.

**Marco, 29 — The Connector (Local Match).** Freelance UX designer, Barcelona; 1–3 trips/year across Europe and Southeast Asia, usually solo or with a partner. *"I've had conversations with locals that changed how I thought about a place. But I've never found a reliable way to make that happen. It has always been luck."* Marco has had meaningful local interactions that reshaped how he experienced a destination, but only by chance, and he would not pay for one — the moment money enters, he feels the authenticity drains out. He represents travelers who are open to connection but have never had a tool that made it feel both safe and genuine simultaneously. Goals: at least one meaningful local conversation per trip; discoveries that weren't part of any plan; feeling like a person in a place rather than a tourist moving between checkboxes. Frustrations: platforms like Airbnb Experiences make connection feel like a purchased product; there is no safe, low-friction way to meet locals organically; group tours feel staged and solo outreach feels awkward with no shared context. He is reciprocal by instinct — happy to show visitors around Barcelona in return — and distrustful of anything commercial or algorithmic; he needs a verified, free way to confirm the other person is who they say they are, with no pressure attached. Primary feature: Local Match. Hypothesis links: H4, H5. Key data: 12/13 open to local connection (n=13); verified identity (11/13), no monetary exchange (9/13), and shared interests on profile (8/13) all function as near-required comfort factors — though whether "no cost" is a hard dealbreaker or a strong preference still needs qualitative confirmation.

**Ji-yeon, 27 — The Documenter (Travel Journal).** Product manager, Seoul; 2–4 trips/year, usually with friends or a partner. *"I always think I'll organize my photos when I get home. I never do. Then two years later I'm looking at 800 pictures and I can't remember half of what I was doing."* Ji-yeon takes hundreds of photos per trip fully intending to organize them afterward, and never does — not from laziness, but because every journaling tool she has tried demands more attention than the trip is worth giving up for it. She isn't a creator or public poster; she wants memories for herself and the people who were there, and she represents the strongest single product signal in the survey: auto-capture as the most wanted feature, including among people who currently document nothing at all. Goals: keep a record of trips without it becoming a second job; share memories with the people she traveled with, not the internet; look back in two years and remember context, not just an image. Frustrations: her camera roll has no notes on where, who, or why; journaling apps lose her attention past day two; Instagram feels performative and WhatsApp threads get buried immediately. She wants documentation that happens automatically in the background, produces a beautiful shareable output she didn't have to build, and defaults to private with an easy option to open up later. Primary feature: Travel Journal. Hypothesis links: H7, H8. Key data: auto-capture and beautiful auto-generated layout tied as top journal features (8/13 each); journaling ranked #3 in feature importance (3.62/5); P1 partially resolved the aspiration–execution gap by confirming she, too, loses trip details from past travel and responded positively to the auto-capture concept, though whether non-documenters actually engage once built still needs a diary study.

## 3. Research & SWOT

### 3.1 Research Design

Travel Buddy's discovery phase deliberately combined two methods rather than relying on one. A quantitative survey answers "how many" and "how much" — it establishes breadth and lets hypotheses be tested against a numeric signal across a reasonably diverse sample (Dippner, 2022, Ch. 5.3.2). A qualitative semi-structured interview answers "why" and "how" — it surfaces the reasoning, workarounds, and emotional texture behind a behavior that a multiple-choice question cannot capture (Dippner, 2022, Ch. 5.3.3; Portigal, 2013). Used together, the two methods triangulate: where they agree, confidence in a hypothesis rises; where they diverge, the disagreement itself becomes a design question rather than a dead end. This pattern emerged repeatedly in this project — most visibly with H3 (fragmentation), where the interview surfaced a pain the survey's answer options had structurally underweighted (see 3.2).

**Instrument 1 — User survey (quantitative).** The instrument (`04_User_Survey.md`) is built as six sections, twenty questions: Section A (identity, motivation, expectation — A1–A7), Section B (current tools and fragmentation — B1–B3), Section C (discovery and trust — C1–C3), Section D (local connection — D1–D3), Section E (planning, documentation, sharing — E1–E5), and Section F (concept reaction and adoption — F1–F4). Each section maps to one or more of the ten hypotheses, and priority hypotheses (H1, H3, H4, H7, H10) were flagged before distribution as "must validate" — if any failed, the product concept itself would need revisiting. The survey closed at **13 valid responses** (17 submitted, 4 blank rows excluded) against a target of 30+. This is a real limitation, not a footnote: the sample is geographically skewed (7 Asia, 6 Europe) and skews young (8 of 13 respondents 18–24). Every percentage in this section should be read as **directional signal, not statistical proof** — a pattern worth designing around, not a number to defend in a viva.

**Instrument 2 — Semi-structured interview (qualitative).** The interview guide (`05_User_Interview_Guide.md`) runs a five-phase structure per session (45–60 minutes): warm-up (5 min), recent-trip walkthrough (15 min), pain and challenge deep-dive (15 min), opportunity exploration with concept reactions (10 min), and wrap-up (5 min). Four participant archetypes were defined against the hypotheses — the Independent Explorer (H1, H2, H3), the Social Planner (H4, H6, H8, H10), the Memory Keeper (H7, H8, H9), and the Pragmatic Planner, added after the first session specifically because it validated H3 with unexpected intensity. Of the planned 3–5 sessions, **one is complete** (P1, Ho Chi Minh City, remote worker, Pragmatic Planner archetype); recruitment for the remaining sessions is ongoing. One completed interview is a genuine constraint on how much interpretive weight the qualitative findings can carry (Martin & Hanington, 2012) — it is treated here as a rich single case that generates hypotheses about depth, not as a validated pattern across users. Nielsen's (2000) argument that a handful of participants surfaces the majority of usability-relevant issues supports proceeding with early synthesis, but it does not substitute for the additional 2–4 sessions still needed before the Local Match and journaling features are finalized.

**Table 2. Hypothesis validation summary.**

| # | Hypothesis (short) | Survey signal (n=13) | Interview signal (P1) | Status |
|---|---|---|---|---|
| H1 | Distrust of commercial reviews | Local residents 4.46/5 vs. platform stars 3.38/5; 10/13 disappointed by highly-reviewed places | Cross-references across 4+ sources before trusting a place; single-source ratings explicitly distrusted | Converging |
| H2 | Off-the-beaten-path demand | "Hard to find authentic local experiences" is the #1 frustration (9/13) | Explicitly wants "where locals actually go," not tourist spots; over-recommended places become tourist traps | Converging |
| H3 | Multi-app fragmentation | 5/13 use exactly 3 apps, 2/13 use 4+; "many apps, nothing does everything" now 3rd-ranked frustration (5/13, up from 2/8) | Uses 8–10 tools per trip; named fragmentation as the single most important thing to fix | Strengthening qualitatively; survey format likely underweights it |
| H4 | Non-transactional connection | "No money involved" selected by 9/13 as a comfort factor | Open to messaging a local for a free recommendation, provided safety signals are present | Converging |
| H5 | Trust as the barrier to connecting | Verified identity (11/13) and no-money framing (9/13) are the top two comfort factors | Needs a genuinely local, voluntary participant with a visible profile and social proof | Converging |
| H6 | Locals willing to guide travelers | Not tested — travelers survey only | Not applicable — requires local-side interviews (5–8 planned) | Not yet tested |
| H7 | Abandons high-effort journaling | 7/13 fall in the no-effort or automatic-only camp; auto-capture tied #1 journal feature (8/13) | Captures photos but loses names/details; "I'll remember later" — doesn't | Converging |
| H8 | Prefers private-first sharing | "Private by default" now 6/13 (up from 3/8) | Trip archive framed as personal memory tool first; sharing only via close-circle Stories | Strengthening |
| H9 | Plans loosely, adapts in-trip | 9/13 select "rough plan, stay flexible"; 6/13 also build detailed itineraries (dual-mode) | Builds a detailed Google Sheets planner, then improvises 30–40% on the ground | Confirmed |
| H10 | Switching cost is the adoption barrier | Concept appeal very high (11/12 positive); cost is top barrier (7/13, 54%), but privacy and "no one I know uses it" are rising | Would switch for consolidation value alone — utility-based, not price-sensitive | Converging, with a cost/utility split worth probing further |

H6 is included for completeness rather than padded with a false signal: the traveler-side instruments cannot test it, and the synthesis file (`05_Research_Synthesis.md`) correctly flags it as pending a separate local-resident research round before the Local Match feature is finalized.

### 3.2 Key Insights & Affinity Clustering

Rather than reading survey answers question-by-question, findings were grouped into themes — grouping quotes and data points by what they mean, not by which question produced them (Dippner, 2022, Ch. 5.3.4). Five clusters emerged, each converging across both methods.

**Cluster 1 — Fragmentation is a compound, systemic pain, not a simple "too many apps" complaint.** The survey shows a growing but still secondary signal: 5 of 13 respondents (38%) now cite "I have to use many different apps and nothing does everything" as a top-3 frustration, up from 2 of 8 in the earlier partial sample, with "apps don't work offline" appearing for the first time (3/13). P1's interview shows why the survey likely understates this: *"The information is spread across multiple platforms, so I have to collect and organize it myself. The whole process feels pretty fragmented."* P1 uses 8–10 tools per trip — Google, ChatGPT, Gemini, TikTok, YouTube, Facebook, Facebook Groups, Google Maps, Google Sheets, Instagram/Facebook Stories — and the friction isn't discovering information, it's manually re-entering it at every hand-off: a restaurant found on TikTok is checked on Maps, cross-referenced on Facebook, then typed into a spreadsheet by hand. Tellingly, even AI tools now embedded in the planning workflow (ChatGPT, Gemini) add to the fragmentation rather than resolving it, because their outputs cannot be saved alongside Maps bookmarks or social saves. This is treated in the synthesis as the strongest qualitative signal collected so far, and the discrepancy with the survey's 3rd-place ranking is itself an insight: multiple-choice formats compress compound, systemic frustration into a single checkbox.

**Cluster 2 — Trust in discovery is earned through convergence, not authority.** Local residents (4.46/5) and known contacts (4.31/5) sit roughly a full point above platform star ratings (3.38/5) and stranger reviews (3.31/5); AI-generated recommendations, at 3.00/5, now sit at the exact midpoint — no longer bottom-ranked, but still well behind personal sources. P1 names the underlying mechanism directly: *"If a restaurant shows up on TikTok, Google Maps, travel groups, and is also recommended by someone I know, I feel much more confident about trying it."* A single high rating is not enough; confidence comes from a place surviving cross-source scrutiny. This explains the review-disappointment pattern: 10 of 13 respondents have visited a highly-rated place that let them down, and open-text responses put a face on the number — *"Great reviews equals huge crowd and I don't like it"* (Respondent 5, Europe, 55+), and *"Pictures looked great but it was underwhelming IRL — way smaller than expected"* (unattributed survey respondent). P1 adds a second layer: *"A lot of recommendations online eventually become tourist spots because everyone keeps recommending the same places. Sometimes I just wanted to know where locals actually go."*

**Cluster 3 — Local connection needs both safety and zero cost, and neither substitutes for the other.** 12 of 13 respondents are open to or have already experienced connecting with a local outside a paid arrangement; only one prefers to travel without it. But willingness is conditional: verified identity (11/13, up from 7/8), no money involved (9/13, up from 6/8), and — newly prominent in the expanded sample — shared interests visible on a profile (8/13, 62%, up sharply from 5/8) are now near-equally weighted comfort factors. P1's account gives these numbers a face: a comfortable local contact must be *genuinely* local, participating voluntarily, and show a profile with interests and past traveler feedback — *"I don't really know how to find the right local person to ask"* is the barrier, not distrust of locals themselves. The interaction should feel low-pressure — a quick question, not an obligation.

**Cluster 4 — Documentation is aspirational until it becomes effortless, and effortless still means "presentable."** 7 of 13 respondents fall into the no-effort or automatic-only camp, and a new "batch it all after the trip" style (2/13) emerged that wasn't visible in the earlier partial sample — travelers willing to spend time on memories, just not during the trip. Auto-capture and "beautiful layout I can show friends and family" are now tied as the top-wanted journal feature (8/13 each) — capture and presentation have become co-equal requirements, not sequential ones. P1 embodies the aspiration/execution gap precisely: *"I think, 'I'll remember this later,' or 'I'll organize everything when I get home,' but that doesn't always happen"* — and the cost is real: specific restaurant names and locations from past trips are already lost. When offered the concept of automatic trip organization, P1 responded positively but flagged two conditions: privacy over how captured data is used, and control to edit or delete unwanted entries.

**Cluster 5 — Concept appeal is strong, but the "why not" list is shifting.** Concept reaction is close to unanimous (11 of 12 valid responses positive, 0 negative). Cost remains the top stated barrier (7/13, 54%), but its dominance has weakened as the sample expanded (from 75% at n=8), while privacy concern (now 31%, tied for 2nd) and — for the first time — "none of my friends use it" (15%) are rising. This partially revives the original H10 network-effect prediction that the smaller sample had appeared to reject. P1 complicates the cost story further: switching intent is framed entirely around consolidation value — *"If it can help me discover places, organize recommendations, plan my itinerary, and keep everything in one place, then I'd definitely be interested"* — with no mention of price. One respondent's unsolicited feedback (Respondent 2, Asia, 25–34) widened the feature lens further, requesting video-based recommendations, social-media content import, budget transparency, travel-style matching, and safety tips — none of which were directly asked about, suggesting the discovery feed's scope may need to extend beyond text tips.

The clearest strategic surprise across both methods is a **reversal in feature priority**: "flexible trip planning" jumped from last place (3.00/5, n=8) to first (4.38/5, n=13), while "effortless journaling" dropped from first (4.38) to third (3.62). P1's planning-heavy workflow corroborates this shift directly — the pain of fragmentation is most acute, and most valuable to solve, in the planning stage, not the memory-capture stage. This one finding materially changes the feature framing carried into Section 4: Trip Planner becomes the primary onboarding hook, not journaling.

Given the sample sizes involved, these clusters are best read as a well-evidenced starting hypothesis set for personas and feature prioritization — not as conclusions immune to revision once the remaining interviews and local-resident research round are complete.

### 3.3 Competitive SWOT Analysis

Five competitors were researched in full (`03_Competitor_Research_SWOT.md`), each evaluated against Travel Buddy's three pillars — Discover, Connect, Plan & Share (Dippner, 2022, Ch. 5.2) — to answer what existing platforms do well and what gaps remain unaddressed. A sixth, AI planning tools (ChatGPT/Gemini), was added after P1's interview as an emerging indirect competitor: not travel-specific, but now embedded in the planning workflow for at least part of the target user base, generating itinerary text that is never actually connected to a map, a booking, or a saved plan.

**TripAdvisor (Discover).** Over 1 billion user-generated reviews and $1.788B revenue in 2023 (20% YoY growth) establish scale and brand trust built since 2000 — but net income was only $10M, reflecting heavy dependence on an advertising model vulnerable to economic cycles (The Strategy Story, 2024). Its structural weakness is twofold: persistent, widely reported fake and manipulated reviews undermine the platform's core credibility, and the UI is cluttered with commercial placements with no social or personal layer — it is built for browsing, not for accompanying a trip in progress (The Strategy Story, 2024; Fu, 2023). It is a reference tool consulted before a trip and abandoned during it — precisely the gap Travel Buddy occupies.

**Google Maps (Discover).** Near-ubiquitous through deep OS integration on Android and iOS, with unmatched real-time navigation and business-location accuracy. Its weakness is that it is entirely impersonal: it surfaces what is nearby, not what is meaningful, with no traveler-specific narrative and no trip planning or journaling layer. Even within its core competency, specialized alternatives such as Waze outperform it on real-time incident avoidance (Rigorous Themes, 2024). Google Maps is infrastructure Travel Buddy sits on top of, not a rival experience.

**Foursquare/Swarm (Discover).** With roughly 15 million users across two apps (City Guide and Swarm), Foursquare pioneered hyper-local, personally-contextual tips ("best table is by the window") ahead of the star-rating model — but its consumer base has been in active decline as the company pivoted to B2B location data, leaving the brand largely unknown to Gen Z travelers and its tips increasingly outdated with no verification mechanism (MBA Skool, 2024). Foursquare is the clearest proof-of-concept that contextual, personal tips beat numeric scores — and the clearest cautionary tale that the idea alone doesn't sustain a product without continued investment.

**Polarsteps (Plan & Share).** Launched in 2015 in Amsterdam, grown to 18M+ downloads entirely through organic, product-led growth with no paid marketing (Startuprad.io, 2024), Polarsteps automates trip journaling via GPS tracking into a beautiful, map-centred timeline, with strong tiered privacy controls. Its entire revenue model — 100% — comes from photo-book printing, a feature that originated from user requests rather than internal roadmap planning (Peecho, 2022). Its weakness is that it is purely retrospective: zero discovery, zero connection, always-on GPS drains battery, and user feedback analysis shows real frustration with the photo-book ordering flow itself (Kimola, 2024). Polarsteps owns the memory layer completely but stops there.

**Airbnb Experiences (Connect).** Operating inside Airbnb's $9.9B (2024) revenue ecosystem as a secondary product to core Stays (Streetwise Journal, 2024), Experiences offers a proven trust-and-safety model — host verification, reviews, global scale across 220+ countries — for traveler-local connection. Its structural weakness is that every interaction is transactional: a paid booking is required, host commissions run up to 20% (discouraging casual participation), and the relationship ends when the paid session does. A systematic 15-year literature review of Airbnb research (Emerald Publishing, 2024) confirms that authenticity, not transaction, is the primary driver of positive guest experience — directly undermining the paywalled model's long-term fit with what travelers actually want. Airbnb Experiences proves the demand for local connection exists; it just proves it inside a paywall Travel Buddy doesn't need.

**Table 3. Comparative feature matrix** (Full / Partial / None).

| Feature | TripAdvisor | Google Maps | Foursquare | Polarsteps | Airbnb Exp. | Travel Buddy |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Local discovery | Full | Full | Full | None | Partial | Full |
| Curated / personal tips | None | None | Full | None | Partial | Full |
| Local connection | None | None | Partial | None | Full | Full |
| Trip planning | Partial | Partial | None | None | None | Full |
| Travel journaling | None | None | Partial | Full | None | Full |
| Privacy-first design | None | None | None | Full | Partial | Full |
| Free to use | Yes | Yes | Yes | Yes | No | Yes |

No column is full across every row, and no single row of "Full" belongs to more than one competitor per pillar — the matrix visualizes the same conclusion the individual profiles point to: the market is pillar-siloed. TripAdvisor and Google Maps own discovery; Polarsteps owns journaling; Airbnb Experiences owns connection, behind a paywall. Foursquare proved contextual tips work, then vacated the space.

**Table 4. Travel Buddy SWOT.**

| Strengths | Weaknesses |
|---|---|
| Only researched platform spanning all three pillars in one coherent flow | Greenfield product — no existing user base, reviews, or trust signals |
| Non-transactional local connection as the core differentiator vs. Airbnb Experiences | Must build local-guide supply from zero before Connect has any value |
| Real-time journaling embedded in the trip flow, vs. Polarsteps' purely retrospective model | Dependent on third-party APIs (maps, possibly booking) for core functionality |
| No commercial bias in discovery recommendations, unlike TripAdvisor's ad-driven ranking | Limited resources relative to incumbents with existing infrastructure and brand recognition |
| Privacy-first design as a stated principle, not an afterthought | |

| Opportunities | Threats |
|---|---|
| Clear market gap — no competitor covers all three pillars at once | Google could add social/connection/travel features at any time, leveraging existing infrastructure |
| Rising distrust of commercial review platforms (TripAdvisor's fake-review problem) | Airbnb could lower commission fees to enable free local connections, closing Travel Buddy's differentiator |
| Foursquare's consumer-market retreat leaves contextual, personal-tip discovery underserved | Deeply entrenched habit of using multiple specialized apps is hard to displace (H3's own flip side) |
| Academic confirmation that authenticity, not transaction, drives positive travel experience (Emerald Publishing, 2024) | GDPR and location-privacy regulation could constrain always-on or auto-capture features |
| AI planning tools generate stranded itinerary output with nowhere to land — a ready-made entry point for Travel Buddy | |

The primary strategic risk is Google: it has the infrastructure to replicate any single feature at scale. Travel Buddy's defensibility has to come from community depth, non-transactional trust, and a UX shape — one continuous flow across discovery, connection, and memory — that a platform built around search and navigation is not structurally organized to build.

## 4. Feature Strategy

### 4.1 Feature Pool & Prioritization

The Solution Pool (`07_Solution_Pool.md`) generated 26 candidate solutions across five problem areas, each capped at five entries and selected for survey signal strength before any ranking occurred. The full pool, organized by area, is reproduced below because the MoSCoW table alone hides which specific research signal justified each call.

**Discover** — D1 Peer-sourced tip feed (ads-free, tied to verified contributors); D2 Traveler-style matching (filters tips by declared travel style); D3 Crowd/popularity signal (flags over-visited spots); D4 Video tip snippets (closes the photo-vs-reality expectation gap); D5 Safety context on places (recent traveler notes on conditions and accessibility).

**Connect** — C1 Verified identity system; C2 Interest and style matching; C3 Reciprocal exchange model (two-way, no money changes hands); C4 In-app messaging (opens only after mutual interest); C5 Report and block controls.

**Plan** — P1 Living shortlist (reorderable, not day-locked); P2 Map view of saved places; P3 One-tap save from Discovery; P4 Offline access; P5 Collaborative trip planning; P6 AI itinerary import (converts pasted ChatGPT/Gemini output into a structured shortlist).

**Journal & Memory** — J1 Auto-capture (location + time, no user action); J2 Auto-generated layout; J3 Private-first sharing (opt-in, not default); J4 Selective sharing with named contacts; J5 Contextual memory layer (links photos to place, contributor, and visit).

**Adoption & Trust** — A1 Free-first model; A2 Value-first onboarding (value shown within 60 seconds); A3 Granular location controls; A4 No-account browsing; A5 Lightweight onboarding (three questions maximum).

**Prioritization methodology.** The pool's cross-user coverage map tags each solution against the three persona types — Explorer, Connector, Documenter. "Weighted by cross-user reach" means concretely this: any solution checked against all three types (D1, D5, P4, A1, A2, A3, A4, A5) was pulled toward Must-have regardless of which pillar it originated from, because it reduces friction for every persona rather than one. Within a pillar, single-type solutions were then ranked by the strength of their underlying survey signal — for example P1 (Explorer-only reach) still lands in Must-have because Trip Planning is the #1-rated feature overall (4.38/5), while D3 and D2 (also Explorer-only) sit in Should-have because their signal, while positive, is secondary to the #1 frustration driver (D1, cited by 9/13 as the top frustration). P4 (offline access) is treated as cross-pillar infrastructure rather than a bonus feature because it is reinforced from two independent directions — cited as a standalone frustration and as a desired Journal condition — a pattern the Solution Pool flags explicitly as strong evidence rather than coincidence. P6 (AI itinerary import) is the one Could-have addition sourced only from the P1 qualitative interview rather than the n=13 survey; it is retained because it represents a real, observed workflow gap (AI-generated plans currently have nowhere structured to go) but is not over-weighted against quantitatively confirmed signals.

**Table 5. MoSCoW prioritization** (full 26-solution mapping, IDs per Solution Pool).

| Priority | Solutions |
|---|---|
| Must have | Peer-sourced tips (D1); safety context (D5); living shortlist (P1); one-tap save (P3); offline access (P4); verified identity (C1); free reciprocal exchange (C3); auto-capture + auto-layout journal (J1, J2); free-first model (A1); value-first onboarding (A2); location controls (A3); no-account browsing (A4); lightweight onboarding (A5) |
| Should have | Style/interest matching (D2, C2); crowd signal (D3); messaging (C4); report/block (C5); map view (P2); collaborative planning (P5); private-first sharing (J3); selective sharing (J4) |
| Could have | Video snippets (D4); AI itinerary import (P6); contextual memory layer (J5) |
| Won't have (v1) | Booking integration; in-app payment; live events — all reintroduce the transactional model Objective 3 moves away from |

Three of the fourteen Must-have solutions anchor the entire v1 scope as standalone core features, because each resolves the highest-confidence problem in its pillar while the remaining Must-haves function as supporting infrastructure (onboarding, trust, offline access) rather than destinations in their own right.

**Trip Planner** is built as a living, reorderable shortlist rather than a locked itinerary because the evidence points in two directions at once: Trip Planning is the single highest-rated feature in the survey (4.38/5), yet 5/13 respondents separately cite multi-app fragmentation, and the P1 interview independently names planning fragmentation as the #1 pain point — 8–10 apps used per trip, with information manually transferred between them. A fixed, day-by-day schedule would solve the organization problem but not the adaptability problem; travelers plan in detail before departure and then improvise heavily once in-destination. The living shortlist is the only structure that serves both behaviors with one artifact, and P5 (collaborative planning) extends it into a shared coordination tool — confirmed directly by P1, who shares her Google Sheets planner with travel companions on every trip.

**Local Match** is framed as a free, reciprocal exchange rather than a paid booking because the underlying willingness signal is conditional, not unconditional: 12/13 respondents are open to local connection, but that openness is gated by two near-required conditions — verified identity (11/13) and no cost (9/13) — with shared interests close behind (8/13). A paid model would directly contradict the second condition and reintroduce the exact transactional framing Objective 3 was defined to move away from (see Section 1, SO3; Airbnb Experiences' paywall gap in Section 3.3). Framing the exchange as two-way — someone guides visitors in their own city, others reciprocate elsewhere — is what keeps the interaction feeling like genuine connection rather than a service.

**Travel Journal** auto-captures location and time in the background instead of relying on manual entry because effort, not desire, is what kills travel documentation. Auto-capture and auto-generated layout are tied at 8/13 in desirability, and journaling ranks #3 in overall feature importance (3.62/5) — but the P1 interview supplies the behavioral mechanism behind those numbers directly: "I always think I'll organize my photos when I get home. I never do." Any capture step requiring a decision is a capture step that gets abandoned. The journal therefore defaults to private (J3), with sharing (J4) as an explicit opt-in choice, so that the documentation experience carries no social-performance pressure.

**Table 6. Feature–persona–journey map.**

| Feature | Pillar | Journey stage | Primary persona | Secondary persona |
|---|---|---|---|---|
| Trip Planner | Plan | Pre-Trip: Plan → In-Destination: Navigate | Aisha (Explorer/Pragmatic Planner) | Ji-yeon (via P5 collaborative planning) |
| Local Match | Connect | In-Destination: Connect | Marco (Connector) | Aisha (open to local contact but gated on trust signals) |
| Travel Journal | Journal | In-Destination: Capture → Post-Trip: Journal & Share | Ji-yeon (Documenter) | Aisha (documents passively today but has no system) |

## 5. System Flow & Information Architecture

### 5.1 Card Sorting

The information architecture is grounded in card sorting — the standard method for discovering users' actual mental models rather than assuming a structure and testing it after the fact (Dippner, 2022, p. 112). An **open card sort** was chosen over a closed sort specifically because Travel Buddy has no existing IA to validate against: in an open sort, participants both group the cards and name their own groups, which surfaces the vocabulary and conceptual boundaries users bring to the product, rather than confirming labels the design team already picked (Spencer, 2009, as cited in Dippner, 2022, p. 118).

The study, documented in full in `09_Card_Sorting_IA.md`, uses all **26 solutions from the Solution Pool as cards**, each shown to participants as a plain-language feature name and description with solution IDs hidden to avoid biasing groupings toward the pillar structure already used internally. The tool of choice is **OptimalSort (Optimal Workshop)**, selected because it auto-generates a similarity matrix and dendrogram rather than requiring manual clustering, with Maze and Miro identified as fallback options. The session is capped at 20 minutes given the moderate card load, and closes with three open-text questions — which group was hardest to name, which cards felt like they belonged in more than one place, and what the participant would call the app's main navigation sections — the last of which directly surfaces candidate nav labels rather than inferring them from grouping alone.

Recruitment targets **5–8 participants**, a range chosen on Tullis and Wood's (2004) finding that card-sort grouping patterns stabilize well before 15 respondents (as cited in Dippner, 2022, p. 120). Inclusion criteria require at least one leisure trip in the past 12 months, active use of a digital travel-planning tool, an age range of 20–45, and a deliberate mix of travel frequency (at least two frequent travelers, at least two occasional ones). Recruitment is further balanced across the three persona types — 2–3 Explorer/Pragmatic Planner participants, 1–2 Social Connector, 1–2 Documenter — screened by self-identifying language rather than by title. UX, product, or app-development professionals are explicitly excluded, since familiarity with conventional IA patterns would bias groupings toward existing app norms rather than a naive traveler's mental model.

It must be stated plainly: **this card sort is designed but has not been run.** `09_Card_Sorting_IA.md` is logged as "Ready to run," and no similarity matrix, dendrogram, or group-label data currently exists. Everything in Section 5.2 below is therefore a **hypothesis derived from the E2E flow's phase structure**, offered as the pre-sort baseline the study is designed to confirm, challenge, or reframe — not a validated finding. The one hypothesis the study is explicitly built to test is whether users separate *Discover* from *Plan* as distinct sections, or collapse them into a single "Trip Planning" category; survey data rates Trip Planning as the #1 feature overall, but the E2E flow treats discovery and planning as two separate phases, so the sort result could go either way.

### 5.2 IA Sitemap

The hypothesised sitemap below follows directly from the five natural groupings proposed in `09_Card_Sorting_IA.md`, cross-referenced against the phase structure in `08_E2E_User_Flow.md`. Each leaf node is annotated with its Solution Pool ID so the structure remains traceable back to the evidence that produced it. As above, this is a pre-sort hypothesis, not a confirmed structure.

```
Travel Buddy App
├── Onboarding
│   ├── Browse without account (A4)
│   ├── Quick sign-up — 3 questions (A5)
│   ├── Free access granted (A1)
│   ├── Personalised first moment (A2)
│   └── Location controls set (A3)
│
├── Dashboard (home hub — bridges Onboarding to all three feature pillars)
│   ├── Active trip status (from Trip Planner)
│   ├── Discovery feed entry point
│   └── Journal quick-capture indicator
│
├── Discover
│   ├── Peer-sourced tip feed (D1)
│   ├── Filter by travel style (D2)
│   ├── Crowd/popularity signal (D3)
│   ├── Video tip snippets (D4)
│   ├── Safety context per place (D5)
│   └── Place detail → Save to Trip Planner (P3)
│
├── Plan / Trip
│   ├── Living shortlist (P1)
│   ├── Map view of saved places (P2)
│   ├── One-tap save from Discovery (P3)
│   ├── Offline access to shortlist/map/notes (P4)
│   ├── Collaborative planning with companions (P5)
│   └── AI itinerary import (P6)
│
├── Connect
│   ├── Browse verified local profiles (C1)
│   ├── Match by interest & style (C2)
│   ├── Reciprocal exchange framing (C3)
│   ├── In-app messaging (C4)
│   └── Report / block controls (C5)
│
├── Journal / Memories
│   ├── Auto-captured entries (J1)
│   ├── Auto-generated layout (J2)
│   ├── Private-by-default view (J3)
│   ├── Selective sharing with contacts (J4)
│   └── Searchable contextual memory (J5)
│
└── Profile & Settings
    ├── My trips (past + upcoming)
    ├── Local guide profile (opt-in)
    └── Location & notification privacy controls (A3)
```

### 5.3 Multi-Feature User Flow

The end-to-end flow, drawn from `08_E2E_User_Flow.md`, runs **Onboarding → Dashboard → Discover / Plan / Connect / Journal → loop back to Discover** for the next trip — the happy-path convention described by Patton (2014), which assumes no errors and a motivated user, with edge cases deferred to later interaction-design phases (as cited in Dippner, 2022, Ch. 8.3, p. 171).

A guest can enter the Discovery feed with no account (A4); registration is required only at the point of saving a place or initiating a connection, which is the transition where the flow places a **Dashboard** — the home hub that surfaces active trip status, the discovery feed, and a journal quick-capture prompt in one view, so that a returning user lands somewhere that already reflects all three pillars rather than a single one. From the Dashboard, the three core features are not silos; the E2E flow shows explicit cross-links between them:

- **Discover → Plan.** Any tip or place surfaced in the feed can be saved to the Trip Planner with one tap (P3), and a pasted AI-generated itinerary can be converted into the same structured shortlist (P6) — both close the gap between browsing and organizing without a tool switch.
- **Plan → In-Destination.** The living shortlist (P1) carries into the destination and becomes reorderable in real time; if connectivity drops, offline access (P4) keeps the shortlist, map, and notes available regardless.
- **Connect → Journal.** This is the flow's most direct cross-feature link: once a user matches with and messages a local (C1–C4), the auto-capture layer (J1) is already running in the background and logs the location and timestamp of that meet-up without any separate action — a Local Match interaction becomes journal content automatically, rather than requiring the user to remember to document it afterward.
- **Journal → Discover (loop).** Post-trip, the auto-generated, private-by-default journal (J2, J3) becomes a searchable memory layer (J5); when the user starts planning the next trip, they re-enter Discovery already carrying saved places, updated travel style, and a record of what worked — closing the loop with more context than a first-time visit.

Two structural tensions surface directly from tracing this flow and carry forward as trade-offs into Section 8.2. First, **auto-capture versus location privacy**: J1's value depends on background location access, which sits in direct tension with the always-visible location toggle promised at onboarding (A3) — the design resolution is to make opting out feel safe and reversible without silently degrading J1's core value. Second, **onboarding brevity versus personalization depth**: A5 caps onboarding at three questions to minimize drop-off, but D2 (style filtering) and C2 (interest matching) both perform better with richer profile data — a progressive-disclosure model, prompting for more detail only at the moment it adds value, is the candidate resolution rather than lengthening onboarding itself.

## 6. Prototyping & Navigation Design

### 6.1 Low-Fidelity Wireframes

Before any visual design commitment was made, Travel Buddy's structure was tested in low-fidelity form (`Travel_Buddy_Wireframe.html`). Dippner (2022, Ch. 8.3) frames prototyping as a staged progression in fidelity, where each stage answers a different question at a different cost: low-fidelity prototypes are cheap to produce and discard, and are deliberately stripped of colour, typography, and imagery so that reviewers cannot be distracted by visual polish — they exist to test whether the *structure* of a flow (screen sequence, information grouping, navigation logic) holds together before a single hour is spent on pixel-level design. High-fidelity prototypes, by contrast, closely approximate the final product and are appropriate only once the underlying structure is validated, because their purpose shifts to testing usability with real users, presenting a concept credibly to stakeholders, and validating emotional response to visual identity (Dippner, 2022, Ch. 8.3).

This sequencing was followed deliberately on Travel Buddy. The lo-fi wireframe pass covered the skeleton of all four flows that later became the 32-screen high-fidelity build — onboarding entry and gating logic, the discovery feed and its mode-switching behaviour, the shortlist/planning sequence, the connect flow, and the journal/memory structure — without colour tokens, final iconography, or photography. The wireframes existed to answer structural questions that are expensive to change once designed in full fidelity: does the guest need to hit a sign-up gate before or after seeing value; does the discovery feed need three distinct modes (Near Me, Country, Map), or would two suffice; does the shortlist require a dedicated map view, or can it be folded into the list. Resolving these questions at wireframe stage — before the design system existed — meant the 32 high-fidelity screens described in 6.2 were built against an already-validated skeleton rather than a moving target, consistent with the rationale that lo-fi work precedes hi-fi work specifically to avoid re-litigating structure after visual investment has been made (Dippner, 2022, Ch. 8.3).

The four flows prototyped at both fidelity stages follow the happy-path convention (Patton, 2014, as cited in Dippner, 2022, Ch. 8.3, p. 171): each assumes a motivated user with no input errors. Edge cases and empty states (e.g., a destination with too few tips to populate Country mode, a network failure mid-video, a rejected companion invite) were noted in the requirements documentation but deliberately excluded from this first prototyping iteration, since validating the primary journey is the priority before investing in exception handling.

### 6.2 Mid/High-Fidelity Prototype

The high-fidelity prototype (`Travel_Buddy_HiFi.html`) translates the validated wireframe structure into 32 interactive mobile screens (390 × 844 px, iOS-style) across the same four flows: Onboarding (9 screens), Discovery & Planning (12 screens), Connect (5 screens), and Journal & Memory (6 screens). Every screen traces to at least one solution ID from the project's solution pool, so nothing in the prototype is decorative — each screen exists because a specific validated user need required it.

**Visual system and rationale.** The design direction is photography-forward, chosen because Travel Buddy's core value proposition is authentic, peer-sourced discovery — a category where imagery carries more trust signal than text, and where competitor precedent (Airbnb, Wanderlog, Polarsteps) has already established that travelers respond to full-bleed destination photography over listing-style layouts. Typography uses DM Sans throughout, a geometric, friendly typeface chosen for readability at the small sizes travel content demands (captions, stats, tab labels), with a defined scale running from a 32–38px/weight-800 display style for splash headlines down to 10px/weight-500 tab labels — giving the interface a clear hierarchy without relying on colour to separate importance levels.

The colour system centres on a green primary (`#5DB85C`) for CTAs, active icon fill, and verified badges, paired with a lime accent (`#C4E03A`) reserved specifically for active-state indication (the nav pill, highlighted chips) so that "green" as a family reads as the brand, while lime is reserved as a functional "you are here" signal distinct from the brand colour itself. A near-black dark navy (`#1C1C2E`) grounds the bottom navigation bar, chosen so navigation reads as a permanent, separate layer from the white/light-grey (`#FFFFFF` / `#F7F7F7`) content surface — echoing the reference apps' pattern of a dark chrome layer beneath light content. Semantic colours are separated from the brand palette: amber (`#F5A623`) for crowd-level caution, red (`#E74C3C`) for safety flags and destructive actions (report/block), and a distinct gold (`#F5C518`) for star ratings — so that a user scanning a screen can distinguish "this is a brand action" from "this is a warning" without reading text. A topographic contour-line motif (very light grey, `#E8E8E8`, on white) recurs on splash and memory/map screens, giving the product a distinct visual signature tied to travel/cartography without competing with photo content or text legibility, and doubles as the map rendering style in the Explore-by-Map mode rather than a satellite or standard street-map style.

Interaction patterns are standardised into a small reusable component set rather than designed per-screen: a dark `BottomNavBar` with lime active-pill indication; full-bleed `PhotoCard` and horizontally-scrolling card rows (cards deliberately cut off at ~48% width to signal further scrollable content); pill-shaped filter chips with a clear active/inactive contrast; bottom sheets with a 24px top-corner radius used consistently for save actions, filters, safety context, and reporting, so the gesture "swipe up from bottom" always means the same thing across the app; and floating circular back/favourite buttons on photo-hero screens. Building these once and reusing them across all 32 screens (rather than re-solving each screen's chrome) is itself a consistency decision, discussed further under heuristics below.

**Screen inventory by flow.**

**Flow A — Onboarding (9 screens).** Splash/Welcome offers both a "Get started" primary path and an "Explore without signing up" ghost-button path into a read-only Guest Discovery Feed; only when a guest attempts to save does a Sign-up Gate bottom sheet appear, framed around "It's free — always" rather than a hard wall. Screens 4–6 are a three-question onboarding sequence (travel style, interests, home city) with visible progress ("Q1/3", "Q2/3", "Q3/3"), followed by a Free Access Confirmation celebration screen, a Personalised First Moment screen that surfaces a tip card matched to the user's just-given answers ("we picked this for you"), and a Location Controls screen that explains location permission tiers (while using / background / never) in plain language before the user reaches the main app.

**Flow B — Discovery & Planning (12 screens).** This is the largest and most functionally detailed flow, covered exhaustively in `11_Explore_Requirements.md` and expanded below. Structurally it runs: Discovery Feed → Tip Detail (with Crowd Signal, Video Snippet Player, and Safety Context Panel reachable as sub-screens/sheets from Tip Detail) → Filter Panel (bottom sheet) → Save to Shortlist → Trip Shortlist in both List and Map view → Companion Invite → AI Itinerary Import (paste a ChatGPT/Gemini itinerary, preview detected places, import) → Offline Mode.

**Flow C — Connect (5 screens).** Local Browse presents a grid of local profiles with an interest-match percentage badge; tapping a profile opens Local Profile Detail (verified badge, interest tags, a "free exchange" label emphasising no commercial fee sits between traveler and local); a Reciprocal Exchange Intro screen is shown once before a user's first message, explicitly stating "this is free — no fees, no tours" alongside a community-guidelines link; this leads into a Message Thread with an in-context "share a tip" shortcut, and a Report/Block modal reachable from the thread's overflow menu.

**Flow D — Journal & Memory (6 screens).** An Auto-Capture Indicator sits as a persistent status-bar pill ("Capturing your trip") with pause/stop controls; when a trip ends, a Journal Auto-Generated screen assembles a map header, photo grid, and timeline automatically; the Journal Private View carries an explicit "only you can see this" badge by default; Share Options is a bottom sheet for sharing with named contacts or a view-only link — deliberately excluding public posting as an option; and a Memory Layer screen lists past trips (searchable, filterable by city/year), each opening into a Past Trip Detail with a map trace and day-by-day breakdown.

*(see Fig. 1, prototype screenshot — Discovery Feed and Tip Detail annotated)*
*(see Fig. 2, prototype screenshot — Onboarding sequence S01–S09 annotated)*
*(see Fig. 3, prototype screenshot — Journal Auto-Generated and Private View annotated)*

**The Explore flow in requirement-level detail.** Because Explore/Discovery is the app's primary entry point — the first surface even unauthenticated guests encounter, and the main return-visit driver between trips — it was specified to a level of interaction detail the other three flows were not, documented fully in `11_Explore_Requirements.md`. Three discovery modes share one filter system: **Near Me**, the location-aware default that labels itself "Tips near [City]" when location is available and falls back to a style-based "Tips for you" feed when it is not; **Country**, which deliberately opens with contextually curated destination suggestions rather than a blank search box — search is present but demoted to a secondary action reached via the top-bar search icon, so that browsing never requires the user to know what to type; and **Map**, rendered in the same topographic contour style as the rest of the design system, with tips shown as colour-coded pins (green = local favourite, amber = popular, red = very touristy) that cluster at proximity and surface a partial bottom-sheet "peek card" on tap rather than a full-screen jump.

Two content signals were specified as always-visible rather than tap-to-reveal: the crowd signal badge (a three-level low/medium/high scale, appearing on every tip card and every map pin without exception, per requirement ED3-01) and, where applicable, a safety indicator surfacing a bottom-sheet panel of recency-tagged, traveler-submitted safety notes. Video content is similarly signalled by a badge that opens a muted-by-default, full-screen vertical player with swipe-up/swipe-down gestures to advance or dismiss. Guest access is explicit and bounded rather than implicit: all three modes and the full Tip Detail screen are browseable with no account, but the save action and local-profile access are both gated behind a "Sign up free / Log in" bottom sheet, and the guest feed shows exactly six tips before an inline sign-up nudge — a quantified, tested threshold rather than an arbitrary paywall. Filters (travel style, category, timing, verified-only toggle) persist across all three mode switches within a session, so a user narrowing to "Food, Solo, Local favourites" in Near Me does not lose that context when checking the same destination on the Map. Non-functional requirements were specified alongside the functional ones: sub-2-second render for the first six feed cards, sub-1.5-second pin rendering on map switch, and a 44×44px minimum tap target on every interactive element per iOS HIG — treating performance and accessibility as first-class requirements for the app's highest-traffic screen, not an afterthought.

### 6.3 Navigation Design Decisions

Travel Buddy uses a dark bottom tab bar with five destinations — Explore, Plan, a centre floating quick-add action, Connect, and Journal — with Profile deliberately kept out of the tab bar and placed in the top-bar avatar icon instead, so the fifth primary slot stays available for a core journey rather than account settings.

The decision to use a bottom tab bar rather than a hamburger/drawer menu rests on three converging arguments. First, thumb-zone accessibility: Travel Buddy is a mobile-first, one-handed product used in transit and on-location, and Nielsen Norman Group's research on mobile reachability (cited under Dippner, 2022, Ch. 8.2) establishes that controls placed at the bottom of the screen fall within comfortable one-handed thumb reach, while a hamburger icon in the top corner does not — a cost that compounds every time a user needs to switch context. Second, frequency of switching: the E2E flow analysis behind this prototype shows users moving repeatedly between an active trip and the discovery feed within a single session (checking a tip while planning, checking the plan while discovering); a persistently visible tab bar makes each of those switches a single tap, whereas a hamburger menu requires opening a drawer, scanning a list, and tapping — adding navigation cost precisely at the moments switching is most frequent. Third, precedent: both Airbnb and Polarsteps — the two closest reference products for a photography-forward, discovery-plus-planning travel app — use bottom tabs successfully in this exact category, giving the pattern established user familiarity rather than requiring users to learn a novel navigation model.

The explicitly rejected alternative is a hamburger menu. It was rejected because it hides primary features behind an extra tap and an extra cognitive step (recalling what is inside the drawer rather than recognising a visible icon), which directly works against two of the personas this project is designed around: a user who wants to check Discover and Journal in the same short session gets penalised twice by drawer navigation, once per feature. The accepted trade-off of this decision — capping primary navigation at five destinations, which forces Profile out of the tab bar and any future sixth feature into a secondary surface — is carried forward into Section 8.2 as a constraint the product must live with as it grows.

This navigation structure, together with several of the interaction decisions described in 6.2, was deliberately designed against specific heuristics from Nielsen's Ten Usability Heuristics (Dippner, 2022, Ch. 8.1), summarised below.

**Table 7. Heuristic-to-decision mapping.**

| Heuristic (Dippner, 2022, Ch. 8.1) | Concrete UI decision |
|---|---|
| Visibility of system status | Crowd signal and safety badges are always rendered on tip cards and map pins rather than hidden behind a tap (ED3-01); onboarding shows explicit "Q1/3" progress; the auto-capture pill and offline sync indicator surface background app state continuously |
| User control and freedom | Guests can explore all three Explore modes and full tip detail without an account; the sign-up gate appears only at the point of a save attempt, not as a blocking wall; the nudge banner is dismissable rather than persistent |
| Recognition rather than recall | Active filters are shown as a removable, horizontally scrollable chip row rather than requiring the user to reopen the filter panel to recall what is applied; the location context label ("Near Chiang Mai") with a "Change" link keeps current context visible instead of requiring the user to remember it |

Taken together, the navigation pattern and the heuristic-driven micro-decisions inside individual screens reflect the same underlying design principle: reduce the cost of moving between the product's core loops (discover → plan → connect → remember) rather than treating each as an isolated destination, since the research underpinning this project found that fragmentation across separate apps — not any single missing feature — was travelers' primary frustration.

## 7. Testing & Refinement

### 7.1 Test Design

Testing was scoped as two complementary rounds rather than one, following the method distinction Dippner (2022, Ch. 9) draws between moderated (Ch. 9.1) and unmoderated (Ch. 9.2) usability testing. A **moderated round** (think-aloud, one participant per persona) was run first to surface *why* users struggle — reasoning, hesitation, in-the-moment reaction — the kind of causal detail only a live observer can capture. A second, **unmoderated round** (8–12 participants, remote, task-based via Maze or Lyssna) was planned to confirm *how often* and *for whom* those same struggles recur, at a scale the moderated round cannot reach, and to resolve specific open product questions (e.g., should Map default to current location or trip destination; does the sign-up gate feel like a blocker) that need broader statistical signal rather than depth.

Both rounds recruit against the same screener and archetypes used throughout Discovery (`01_Research_Hypotheses.md`): the Explorer/Pragmatic Planner (Aisha), the Cultural Connector (Marco), and the Documenter (Ji-yeon), explicitly excluding anyone who had already seen the prototype, participated in the interview, survey, or card sort, to avoid cross-round contamination. The unmoderated round's persona quota (4–5 Aisha, 2–3 Marco, 2–3 Ji-yeon) mirrors the card-sort recruitment logic so findings can be segmented by persona rather than pooled as one undifferentiated sample.

All five tasks trace the same chronological journey across both rounds — discover, plan, connect, remember — deliberately not randomized, since later-stage screens (e.g., a completed journal) are not meaningful out of sequence:

**Table 8. Usability test task set.**

| # | Task | Entry screen | Success signal |
|---|---|---|---|
| T1 | Find a food-related tip in Chiang Mai from another traveler and save it to a trip | Discovery Feed | Tip saved to a trip shortlist |
| T2 | Get an AI-chatbot-written itinerary into the trip plan | Trip Shortlist | Import completes, places visible in plan |
| T3 | Find a named local (Niran) and reach out for a genuine recommendation | Local Browse | Message sent to Niran |
| T4 | Find the record of what happened on a completed trip | Journal / app home | Auto-generated journal opened, unprompted |
| T5 | Share the trip journal privately with one named friend (Ji-yeon), not publicly | Journal Private View | Recipient selected, share completed |

This set operationalizes the outline's five required tasks (onboarding/dashboard, find-and-save a tip, connect via Local Match, add a journal entry, share privately) against actual prototype screens, phrased functionally rather than by UI label so navigation-finding itself remains an observable, not a given.

Metrics combined quantitative and qualitative signal: **task completion rate** and **time on task** per participant; a **Single Ease Question** (1–7) immediately after each task; the full, unmodified 10-item **System Usability Scale** (Brooke, 1996) at the end of the session; and, in the unmoderated round specifically, misclick rate and first-click accuracy captured automatically by the testing platform. Think-aloud narration during the moderated round supplied the open-text "why" behind any low SEQ score.

*Limitation stated plainly, and central to how these results should be read:* due to time pressure ahead of the submission milestone, the moderated round (n = 3, one per persona) was executed as an AI-simulated pilot — the researcher, via Claude, role-played each persona in character against the live prototype — rather than with three independently recruited human participants. The unmoderated round remains at the planning stage in `12_Unmoderated_Usability_Test_Plan.md` and was not fielded. The instruments, task set, and reporting format are identical to what a real study would use, but the results below are hypotheses for a real test to confirm or disconfirm, not validated findings, and should not be read as evidence that any issue is fixed by the recommendations proposed.

### 7.2 Findings & Iterations

Aggregated SEQ and SUS scores by persona: Aisha (Discover & Plan, T1–T2) scored 6/7 and 6/7 (SUS 80/100); Marco (Connect, T3) scored 3/7 (SUS 62.5/100); Ji-yeon (Journal, T4–T5) scored 7/7 on T4 but only 1/7 on T5 (SUS 65/100). The average SEQ across all five tasks (4.6/7) and average SUS (69.2/100) look nominally healthy but are propped up by Aisha's strong run — they hide that two of five tasks had serious friction and should not be read as "the prototype is fine" without the per-task breakdown.

The pattern is sharper than the average suggests: every task that involved *browsing* open content (T1, T2, T4) scored SEQ ≥ 6/7; every task that instead required *finding or selecting a specific named person* (T3, T5) scored SEQ ≤ 3/7. This is one missing interaction pattern — person search and invite — surfacing in two structurally unrelated flows (Local Browse and the Journal share sheet), not two separate defects. Notably, desirability was never in question: the Explorer called AI-import "exactly my workflow," the Documenter called the auto-journal "exactly the fantasy I have and never get," and the Connector welcomed the "Free exchange, no fees" label — including the two participants who then hit the Critical failures below. That distinction matters: a findability gap is more fixable than a desirability failure.

**Table 9. Top findings and design response.**

| Issue observed | Quote / behavior | Severity | Change made |
|---|---|---|---|
| Local Browse has no search or filter; the only path to a named local (Niran) is backtracking through a tip he authored | *"I only found him by backtracking through a tip I'd already saved."* | Critical | Add a name-search field to Browse, matching the existing Explore search pattern, plus a "Message [Name]" shortcut directly on any tip authored by a verified local |
| Journal share sheet offers a fixed 3-person contact list with no search or invite-by-name option | *"I'm stuck; the exact task I was given can't be completed as written."* | Critical | Add a search/invite field above the contact list, reusing the same component built for the Local Browse fix — resolving both Critical findings with one build |
| Local Browse mixes locals from unrelated destinations (Hanoi, Lisbon) with Chiang Mai locals, with no location filter | Observed directly while scrolling for Niran; compounds the search gap above | Major | Default Browse to the active trip's destination (already known and displayed elsewhere in the app), with an explicit toggle to browse other destinations |

Beyond these three, the pilot logged nine further issues at Major-to-Cosmetic severity — the AI-import parser retaining "Day 3:" as literal place-title text instead of routing content into the matching itinerary day; empty "Interests" and "% match" placeholders on a local's profile; an unexplained match-score badge; inconsistent CTA wording between Browse and tip-detail messaging; an undiscoverable share-link workaround; visually incomplete imported items; and minor copy/labelling ambiguities — plus two methodological flags: the sign-up gate required no email or password in this build, so the Explorer's ease with it ("no email/password screen, which feels too easy for a real app") cannot be read as evidence the real gate will feel acceptable; and the destination picker's pre-highlighted default may have inflated first-click accuracy on T1. Both are logged as open items for the real round rather than treated as resolved. A second cross-cutting observation shaped the fix priority: the Documenter trusted the Journal's privacy copy completely ("Only you can see this") before hitting the share-sheet wall — pairing strong trust language with a flow that cannot fulfil it risks the failure generalizing to the trust claim itself, which is why the Local Browse and Journal fixes were ranked above the AI-import fix despite comparable severity.

Consistent with the method note above, none of this constitutes a validated before/after: no redesign has actually been implemented against these findings yet, and the real moderated and unmoderated rounds described in Section 7.1 remain the mechanism by which these hypotheses would be confirmed, revised, or discarded.

## 8. Portfolio & Strategic Reflection

### 8.1 What Problem Travel Buddy Solves

Three research signals converge on one validated problem. Travelers juggle three or more disconnected apps per trip — P1's interview put the real number at 8–10, with fragmentation named the single most important problem to fix (H3) — because no existing platform spans discovery, connection, and memory-keeping together (comparative matrix, Section 3.3). Travelers also distrust commercially-biased discovery: TripAdvisor's fake-review problem is well documented (The Strategy Story, 2024), and H1 confirms travelers rate peer tips over stranger reviews. And where local connection exists at all, it is transactional — Airbnb Experiences proves the *demand* for authentic local interaction (Emerald Publishing, 2024) but gates every contact behind a paid booking, a structural gap H4 confirms travelers want closed for free, not worked around.

These three findings map directly onto Travel Buddy's three strategic objectives (Section 1): SO1 (unify discovery, connection, and journaling to remove fragmentation), SO2 (replace commercial bias with peer-sourced trust), and SO3 (enable local connection without a paywall). Each objective, in turn, is what one persona experiences as pain and what another experiences as opportunity: Aisha (Explorer/Pragmatic Planner) is the clearest evidence for SO1, having already stitched together Google Maps, Reddit, and AI chatbots per trip; Marco (Connector) validates SO3, wanting a genuine local relationship without a booking fee attached; Ji-yeon (Documenter) sits downstream of SO1 and SO2 — she benefits from the same unified, trust-first data the other two personas generate, in the form of an effortless, privately-shareable trip record.

The product design consequence is that none of the three pillars can be built to serve one persona at the expense of another. Local Match must stay non-transactional for Marco without becoming friction for Aisha, who may never open it; the auto-journal must stay zero-effort for Ji-yeon without capturing data Marco or Aisha didn't consent to share. Serving all three without compromise is the actual design constraint behind Sections 4–6, not a slogan layered on afterward.

### 8.2 Key Design Decisions & Trade-offs

**UX strategy summary.** A UX strategy needs four tenets working together (Levy, 2021, in Dippner, 2022, Ch. 6.1.1), each also mapping to a persona:

**Table 10. Four-pillar UX strategy.**

| Pillar | How Travel Buddy applies it |
|---|---|
| Business strategy | Differentiation, not price — no rival spans all 3 pillars (Section 3.3) |
| Value innovation | Airbnb's proven connection value, delivered free and frictionless |
| Validated research | Every core belief tested against real signal before a screen was built — with the sample-size limits of that validation stated plainly (Section 3.1, Section 8.4) |
| Frictionless UX | One-tap save, zero-input journaling, 5-item navigation |

**Table 11. Key decisions & trade-offs.**

| Decision | Alternative considered | Reason chosen | Trade-off accepted |
|---|---|---|---|
| Non-transactional Local Match | Paid booking model (Airbnb-style) | Emerald Publishing (2024) links authenticity, not payment, to positive peer-to-peer experience; H4 confirms travelers want connection without a fee | Harder to monetize directly; supply of local guides must be built on trust and reciprocity, not a commission incentive |
| Auto-journaling (GPS + one-tap capture) | Manual journaling | H7 confirmed travelers abandon high-effort journaling; Polarsteps' growth (18M+ users) validates automatic capture as the retention driver | Requires always-on location access; must stay opt-in and clearly reversible, or it repeats Polarsteps' battery/privacy criticism |
| Bottom tab navigation (5 tabs) | Hamburger menu | Thumb-zone accessibility on mobile; users switch frequently between an active trip and the discovery feed, and tabs reduce that switching cost | Caps primary navigation at 5 destinations, forcing disciplined information hierarchy rather than deferring scope decisions into a hidden menu |
| Peer-sourced tips over algorithmic/star ratings | Commercial review or algorithmic recommendation model | H1 and TripAdvisor's fake-review weakness confirm distrust of commercially-influenced review systems; Foursquare proved contextual peer tips outperform star ratings before it abandoned the consumer market | Quality control becomes an editorial challenge at scale — without paid moderation, curation depends on community trust mechanisms that are unproven at Travel Buddy's current size |

Two of these four decisions were stress-tested directly in Section 7: the usability pilot's Critical findings did not question non-transactional Local Match or peer-sourced tips as concepts (both were received positively — "Free exchange" and the verified-badge trust signal both worked as intended) but exposed that the *findability* layer supporting them (person search) was incomplete. That is a meaningful distinction for portfolio purposes: the strategic decisions held up under first contact with a user; the interaction design implementing them did not, yet.

### 8.3 Value Logic

**User value.** Travel Buddy reduces the cognitive load of coordinating 8–10 separate tools into one flow (H3, P1 interview) — discovery, planning, and connection share one data model instead of requiring manual transfer between apps. It offers connection that stays genuine rather than commercial: the "Free exchange, no fees" framing tested as an immediate reassurance in the usability pilot, directly resolving the reciprocity question H4/H5 predicted travelers would have before making first contact. It preserves memory with effectively no effort — the auto-generated, private-by-default journal was the single strongest moment across the pilot ("exactly the fantasy I have and never get"), validating H7 and H8 together: capture without labor, privacy without a settings hunt.

**Business value.** Monetization follows Polarsteps' validated precedent rather than Airbnb's: a freemium model where discovery, connection, and basic journaling stay free, and revenue comes from optional physical outputs (photo-book printing accounted for 100% of Polarsteps' revenue, Peecho, 2022) plus a premium tier for advanced journaling, collaborative trip features, and enhanced privacy controls — monetizing what users already want to do, not gating what makes the product trustworthy in the first place. Network effects compound in both directions: every local who joins Local Match creates value for future travelers passing through that destination, and every privately-shared journal is a plausible acquisition channel, echoing the organic, no-paid-marketing growth loop that took Polarsteps to 18M downloads. Over time, anonymized, GDPR-compliant behavioral data — what travelers actually save, message about, and journal — becomes a recommendation asset no commercially-biased competitor can replicate without undermining the trust that produces the data in the first place.

### 8.4 Critical Reflection

The honest state of validation across this project is uneven, and should be read as such rather than smoothed over. Of several interviews planned during Discovery, only one (P1) was completed, so most qualitative claims about fragmentation and workflow rest on a single account, not a saturated pattern. The card sort referenced throughout (Section 5.1) was never actually run with participants; the information architecture in Section 5.2 is a researcher-authored hypothesis structured *as if* validated, not a tested outcome. Usability testing, detailed in Section 7, was an AI-simulated pilot substituting a single role-playing rater for three independent participants, and the planned unmoderated round of 8–12 was never fielded. Every number in this document that looks like a usability metric — SEQ, SUS, completion — describes a formative pilot's structure, not empirical human behavior.

If this project were repeated, the sequencing would change materially: the card sort and a fuller interview round would run *before* the high-fidelity prototype was built, not be retrofitted as hypothesis-generating exercises alongside it — building screens ahead of structural validation risks anchoring the design on an IA that only feels tested.

Two open questions remain genuinely unresolved rather than rhetorical. First, is "no cost" a hard requirement for Local Match, or would a light-touch monetization (e.g., optional tipping) be acceptable to travelers without reintroducing the transactional friction H4 identifies in Airbnb Experiences — this pilot's participants welcomed the free framing but were never asked to react to a paid alternative directly. Second, can free-first local supply actually scale past early adopters, given that Travel Buddy has no existing user base, reviews, or trust signals to bootstrap guide participation (Section 3.3) — Airbnb needed a commission incentive to build supply at scale, and whether trust and reciprocity alone can substitute for that incentive is untested by anything in this project so far.

---

## References

Brooke, J. (1996). SUS: A "quick and dirty" usability scale. In P. W. Jordan, B. Thomas, B. A. Weerdmeester, & A. L. McClelland (Eds.), *Usability evaluation in industry* (pp. 189–194). Taylor & Francis.

Dippner, D. (2022). *User experience design – Principles & methods* (1st ed.). SRH Fernhochschule.

Emerald Publishing. (2024). 15 years of Airbnb's authenticity that influenced activity participation: A systematic literature review. *Journal of Humanities and Applied Social Sciences, 6*(1), 55–71. https://www.emerald.com/jhass/article/6/1/55/1217647

Fu, Y. (2023, March 2). *Analysis of TripAdvisor's UX*. Medium. https://medium.com/marketing-in-the-age-of-digital/analysis-of-tripadvisors-ux-22fcb8bee46a

Garrett, J. J. (2011). *The elements of user experience* (2nd ed.). New Riders.

Kimola. (2024). *Unlock travel app success: Polarsteps feedback analysis*. https://kimola.com/reports/unlock-travel-app-success-polarsteps-feedback-analysis-google-play-en-141063

Martin, B., & Hanington, B. (2012). *Universal methods of design*. Rockport Publishers.

MBA Skool. (2024). *Foursquare SWOT analysis*. https://www.mbaskool.com/swot-analysis/media-and-entertainment/1409-foursquare.html

Nielsen, J. (2000, March 18). *Why you only need to test with 5 users*. Nielsen Norman Group. https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/

Patton, J. (2014). *User story mapping*. O'Reilly Media.

Peecho. (2022). *Peecho print API helps Polarsteps monetize user content with print on demand travel books* [Case study]. https://www.peecho.com/case-studies/polarsteps

Portigal, S. (2013). *Interviewing users*. Rosenfeld Media.

Rigorous Themes. (2024). *10 best Google Maps alternatives*. https://rigorousthemes.com/blog/best-google-maps-alternatives/

Spencer, D. (2009). *Card sorting: Designing usable categories*. Rosenfeld Media.

Spies, H. (2014). *UX strategy*. O'Reilly Media.

Startuprad.io. (2024). *Polarsteps growth: Privacy-first travel app at 18M users*. https://www.startuprad.io/post/polarsteps-growth-privacy-first-travel-app-at-18m-users-startuprad-io

Streetwise Journal. (2024). *Airbnb SWOT analysis: Risks, opportunities & insights for 2024*. https://streetwisejournal.com/airbnb-swot-analysis/

The Strategy Story. (2024). *TripAdvisor SWOT analysis*. https://thestrategystory.com/blog/tripadvisor-swot-analysis/

Tullis, T., & Wood, L. (2004). How many users are enough for a card-sorting study? In *Proceedings of the Usability Professionals Association Conference*.

*Note.* In-text citations follow APA 7th edition (Author, Year); page or chapter locators are added for direct quotations and specific claims (e.g., Dippner, 2022, Ch. 4.2). Project working files referenced throughout the text (e.g., `01_Research_Hypotheses.md`) are internal Discovery-phase documents, not published sources, and are listed in the Appendix rather than above.

---

## Appendix

Supplementary material available in the project's Discovery folder, not reproduced in full here for length: the complete 20-question survey instrument and anonymized response data (`04_User_Survey.md`), the P1 interview guide and notes (`05_User_Interview_Guide.md`), the full 26-card card-sorting instrument prepared for the not-yet-run study (`09_Card_Sorting_IA.md`), the complete E2E flow and prototype specification documents (`08_E2E_User_Flow.md`, `10_Prototype_Plan.md`, `11_Explore_Requirements.md`), the full 32-screen wireframe and high-fidelity prototype files (`Travel_Buddy_Wireframe.html`, `Travel_Buddy_HiFi.html`), and the complete simulated usability test plan and findings (`12_Unmoderated_Usability_Test_Plan.md`, `13_Simulated_Usability_Findings.md`).

**Project working files cited throughout this document:** `01_Research_Hypotheses.md` · `02_Stakeholder_Ecosystem.md` · `03_Competitor_Research_SWOT.md` · `04_User_Survey.md` · `05_Research_Synthesis.md` · `05_User_Interview_Guide.md` · `06_User_Personas.md` · `07_Solution_Pool.md` · `08_E2E_User_Flow.md` · `09_Card_Sorting_IA.md` · `10_Prototype_Plan.md` · `11_Explore_Requirements.md` · `12_Unmoderated_Usability_Test_Plan.md` · `13_Simulated_Usability_Findings.md`. Full URLs for industry sources are catalogued in `Discovery/03_Competitor_Research_SWOT.md` → References.
