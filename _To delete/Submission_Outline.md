# Travel Buddy — Submission Outline
**Module:** User Experience Design – Principles & Methods  
**Submission:** MUXDCI Alternative C | **Due:** 31.01.2027 | **Total:** 100 pts | **Scope:** 20 pages  
**Status key:** ✅ Evidence exists → ⚙️ Needs writing/synthesis → 🔲 Not yet started

---

## Document Structure

```
Cover page
Table of contents
Introduction                               (~0.5 page, does not count toward 20-page limit)
1. Process Framing & Planning              (~1 page)
2. Stakeholder Ecosystem                   (~2 pages)
3. Research & SWOT                         (~4 pages)
4. Feature Strategy                        (~2 pages)
5. System Flow & IA                        (~3 pages)
6. Prototyping & Navigation Design         (~4 pages)
7. Testing & Refinement                    (~2 pages)
8. Portfolio & Strategic Reflection        (~2 pages)
References
Appendix (raw survey data, interview transcripts, full wireframes)
```

---

## Introduction *(~0.5 page, separate from Section 1)*

**Purpose:** Orient the examiner before the structured process begins. This is not a summary — it sets the scene.

> **What to write (3–5 short paragraphs):**

**What Travel Buddy is**  
Travel Buddy is a mobile experience platform designed to help people discover places, connect with locals, and plan and share travel experiences. Unlike existing platforms that serve one part of the travel journey, Travel Buddy integrates three pillars — Discover, Connect, and Plan & Share — into a single, coherent experience.

**The problem it addresses**  
Travelers today rely on multiple disconnected apps, distrust commercially biased review platforms, and lack a free, authentic way to connect with local people at their destination. Existing solutions each serve one pillar well but leave the others unaddressed — a gap confirmed through competitive analysis and grounded in ten research hypotheses developed prior to primary data collection.

**What this document covers**  
This submission documents the end-to-end UX strategy for Travel Buddy, following the Double Diamond process model. It moves from research and stakeholder analysis (Sections 1–3), through feature definition and information architecture (Sections 4–5), into prototyping and usability testing (Sections 6–7), and concludes with a strategic reflection on the full UX value logic (Section 8).

**Scope and methods**  
The project applies two primary research methods — a quantitative user survey and semi-structured qualitative interviews — alongside competitive SWOT analysis of five established travel platforms. Design decisions throughout are grounded in research findings rather than assumption.

---

## Section 1 — Process Framing & Planning *(5 pts, ~1 page)*

**Task:** Select a UX process model and define strategic objectives.  
**Textbook anchor:** Dippner (2022), Ch. 4 — Design Thinking Process & Double Diamond.

### 1.1 Chosen Process Model: Double Diamond + Lean UX

The submission applies the **Double Diamond** (discover → define → develop → deliver) as the primary process frame, with Lean UX principles informing iteration pace. Rationale: the travel app space has well-established competitors (see `03_Competitor_Research_SWOT.md`) but no single platform spans all three pillars (Discover · Connect · Plan & Share), which means the project genuinely needs an exploratory divergence phase before converging on features.

> **What to write:** ~1 paragraph explaining why Double Diamond fits a greenfield, multi-pillar product better than a purely agile sprint model. Cite Dippner (2022, Ch. 4.2) for the Double Diamond and note the Lean UX connection to hypothesis-driven research (H1–H10 from `01_Research_Hypotheses.md`).

### 1.2 Strategic Objectives

Three objectives derived from the competitive gap analysis in `03_Competitor_Research_SWOT.md` and research hypotheses in `01_Research_Hypotheses.md`:

| # | Objective | Evidence basis |
|---|-----------|----------------|
| SO1 | Reduce trip planning fragmentation by unifying discovery, connection, and journaling in one platform | H3: travelers use 3+ apps per trip; comparative matrix shows no competitor covers all three pillars |
| SO2 | Replace commercial bias with peer-sourced trust as the primary discovery signal | H1: travelers distrust paid review platforms; TripAdvisor's fake review weakness (The Strategy Story, 2024) |
| SO3 | Enable authentic local connection without a transactional paywall | H4: non-transactional connection; Airbnb Experiences' structural gap — every local contact requires a paid booking (Streetwise Journal, 2024) |

> **What to write:** Present the three objectives in a short table or structured paragraph. Each must be tied to a research signal (hypotheses) and a competitive gap (SWOT). Do not invent new objectives — these three are grounded in existing files.

---

## Section 2 — Stakeholder Ecosystem *(10 pts, ~2 pages)*

**Task:** Stakeholder map + 2 user personas.  
**Textbook anchor:** Dippner (2022), Ch. 5.2 — Product objectives, stakeholder mapping; Spies (2014).  
**Source file:** `02_Stakeholder_Ecosystem.md` ✅

### 2.1 Stakeholder Map

The stakeholder map is structured as three concentric rings representing proximity of influence to the product (see Figure 1).

**Core stakeholders** have direct decision-making power over the product's direction and quality. This group includes the **Product Owner/Founder**, who sets the strategic vision; the **UX Product Designer/Design Team**, responsible for the user experience; the **Tech Lead/CTO**, overseeing technical implementation; and **Business Development**, driving growth and partnerships.

**Direct stakeholders** interact with the product regularly and shape its delivery. This ring includes **Developers** (who build and maintain the platform), the **Marketing Lead** (who defines how Travel Buddy is communicated to users), the **Investor Rep** (whose interests influence product priorities and scaling decisions), and **SMEs** (subject-matter experts who inform domain-specific content and features).

**Peripheral stakeholders** operate at a distance but still affect or are affected by the product. These are **Locals (supply side)** — the hosts and community contributors who provide authentic travel experiences; **App Stores Team** (Apple/Google), who govern distribution and policy compliance; **Tourism Boards**, potential institutional partners with destination-level interests; and **Legal & Compliance**, who set regulatory boundaries around data, privacy, and platform operations.

This layered structure reflects the principle that UX decisions must balance the needs of those closest to the product with the constraints imposed by external actors (Dippner, 2022, Ch. 5.3).

> *Figure 1: Travel Buddy Stakeholder Map (three-ring model) — see `02_Stakeholder_Ecosystem.md` and Figma diagram.*

The following four stakeholder tensions directly affect design decisions (see `02_Stakeholder_Ecosystem.md`, Section 2.5 for full detail):

- **Speed vs. quality** (Product Owner vs. UX Lead → MVP scope discipline)
- **Monetization vs. user trust** (Investor vs. UX Lead → no dark patterns)
- **Content authenticity vs. partnerships** (Marketing vs. BD → no drowning out local voices)
- **Technical feasibility vs. design ambition** (Tech Lead vs. UX Lead → offline + real-time features need early feasibility testing)

### 2.2 User Personas

⚙️ **Needs synthesis.** Persona profiles are not yet written as standalone documents. They must be built from:

- The four traveler archetypes defined in `01_Research_Hypotheses.md` (The Explorer, The Cultural Connector, The Documenter, The Pragmatic Planner)
- The three interview participant profiles from `05_User_Interview_Guide.md` (Independent Explorer, Social Planner, Memory Keeper)
- Survey dimensions mapped in `04_User_Survey.md` (Sections A1–A6 for identity, motivation, expectation)

**Two personas to write for submission:**

**Persona A — The Explorer / Independent Traveler**  
Composite of "The Explorer" archetype + Interview Participant 1. Key attributes:
- Travels solo or in pairs, 3–6x/year internationally
- Primary frustrations: commercial bias in reviews (H1), information fragmentation (H3), difficulty finding off-the-beaten-path spots (H2)
- Discovery behavior: Reddit, local advice, friend recommendations over TripAdvisor
- Connection: open to local contact but needs trust signals (H5)
- Documentation: takes photos but has no system (camera roll dependency)
- Adoption barrier: "already has apps, why add another" (H10)

**Persona B — The Memory Keeper / Social Planner**  
Composite of "The Documenter" archetype + "Social Planner" Interview Profile. Key attributes:
- Travels 1–4x/year, often in groups
- Primary frustration: memories fade or scatter across apps, journaling feels like a chore (H7)
- Sharing preference: private-by-default — WhatsApp, close friends, not public posts (H8)
- Planning style: rough plan, high flexibility on arrival (H9)
- Connection: willing to be guided by locals, values genuine exchange over paid experiences (H4)
- Feature priority: auto-journaling, private sharing, collaborative trip planning

> **Format for each persona:** Name + photo placeholder, 3–5 attribute tags, Goals (2–3), Frustrations (2–3), Current tools, Quote. Keep to ~half a page each. Cite survey questions (A4, A5, A6, B3) as the behavioral basis.

---

## Section 3 — Research & SWOT *(20 pts, ~4 pages)*

**Task:** Two research methods + SWOT of 2–3 competitors.  
**Textbook anchor:** Dippner (2022), Ch. 5.3 — User Research, quantitative (5.3.2) and qualitative (5.3.3) methodologies; Ch. 5.3.4 — Analyzing research insights.  
**Source files:** `01_Research_Hypotheses.md` ✅ · `03_Competitor_Research_SWOT.md` ✅ · `04_User_Survey.md` ✅ · `05_User_Interview_Guide.md` ✅

### 3.1 Research Design

Two methods applied:

**Method 1 — User Survey (Quantitative)**  
Instrument: 6 sections (A–F), 20 questions, targeting 30+ respondents. Fully designed in `04_User_Survey.md`.  
Priority hypotheses tested: H1, H3, H4, H7, H10 (all 🔴 critical).  
Analysis approach: hypothesis validation table (pass/fail signal per hypothesis) + behavioral clustering for personas.

> **What to write in submission:** Brief methodological rationale (why survey for this phase), 2–3 sentence description of instrument design, and — once survey is distributed and results collected — key findings table. If data is not yet collected at time of writing, present the instrument and planned analysis approach; note that findings will be inserted before final submission.

**Method 2 — Semi-Structured Interviews (Qualitative)**  
Instrument: 5-phase script (45–60 min per session), 3 participant profiles. Fully designed in `05_User_Interview_Guide.md`.  
Focus: lived trip walkthrough → pain deep-dive → opportunity exploration.  
Participants: Independent Explorer (P1), Social Planner (P2), Memory Keeper (P3).

> **What to write in submission:** Methodological rationale (depth over breadth; stories reveal behavior that surveys cannot), participant selection logic tied to research archetypes (`01_Research_Hypotheses.md`), and — after interviews are conducted — a findings table per participant (dominant pain, hypothesis confirmed/challenged, opportunity signal, direct quotes). Cite Portigal (2013) for semi-structured interview methodology.

### 3.2 Key Insights & Affinity Clustering

⚙️ **Needs data.** Once survey responses and interview notes are collected, synthesize using affinity mapping:

- Group all quotes and observations by theme (not by question)
- Expected clusters based on hypotheses: Review distrust, App fragmentation, Non-transactional connection, Low-effort journaling, Switching cost
- Each cluster becomes a design insight that feeds directly into Section 4 (Feature Strategy)

> **What to write:** Present 4–5 insight cards or a thematic table. Each insight: theme label + supporting evidence (quote from interview or % from survey) + design implication. If data is still being collected, present the planned affinity mapping structure.

### 3.3 Competitive SWOT Analysis

✅ **Fully documented** in `03_Competitor_Research_SWOT.md`. Condense for submission:

- **3 competitors** (of the 5 analyzed): TripAdvisor (Discover leader, fake-review weakness), Polarsteps (Plan & Share leader, no discovery/connection), Airbnb Experiences (Connect leader, paywall limits authenticity). Foursquare and Google Maps stay in the matrix only.
- **Matrix:** reuse the 9-row comparative matrix (Section 3.4) — most efficient way to show the market gap without five full SWOTs.
- **Travel Buddy SWOT:** reuse the synthesized SWOT (Section 3.5). State the key insight explicitly — no competitor covers all three pillars — since it anchors Section 4.

---

## Section 4 — Feature Strategy *(10 pts, ~2 pages)*

**Task:** Prioritize features using MoSCoW or 2×2 matrix; define 3 core features; map to personas.  
**Textbook anchor:** Dippner (2022), Ch. 6.1.1 — Four pillars of UX strategy; Ch. 6.1.2 — Prioritization methods.  
**Source files:** `01_Research_Hypotheses.md`, `03_Competitor_Research_SWOT.md` (Section 3.6 — Design Implications)

🔲 **Not yet started.** However, evidence from existing files is sufficient to build this section now.

### 4.1 Feature Pool

Derived from research hypotheses and competitive gaps:

| Feature idea | Evidence basis |
|---|---|
| Peer-sourced discovery feed (local tips, no ads) | H1, H2; TripAdvisor fake review weakness |
| Local Match (free traveler-local connection) | H4, H5; Airbnb Experiences paywall gap |
| Auto-journaling (GPS + one-tap capture) | H7, H8; Polarsteps' journaling model but limited to retrospective |
| Collaborative trip planner | H3, H9; no competitor offers flexible group planning |
| Offline support | Competitive matrix — only Google Maps and Polarsteps offer this |
| Privacy-first sharing (private by default) | H8; Polarsteps' privacy model as precedent |
| Onboarding (travel style quiz → personalized feed) | Persona differentiation (Explorer vs. Memory Keeper have opposite entry needs) |
| Dashboard (trip status + discovery + journal prompt) | Assignment requirement; connects all three pillars in one view |

### 4.2 Prioritization: MoSCoW

> **What to write:** Apply MoSCoW to the feature pool above. Recommended classification (justify each in the submission):

| Priority | Features |
|---|---|
| **Must have (MVP)** | Peer-sourced discovery feed · Local Match (basic) · Auto-journaling · Onboarding · Dashboard |
| **Should have** | Collaborative trip planner · Offline support · Privacy-first sharing controls |
| **Could have** | Physical photo book export (à la Polarsteps' revenue model) · AI-assisted itinerary suggestions |
| **Won't have (v1)** | Booking integration · In-app payment · Live event listings |

### 4.3 Core Features & Persona Mapping

Three core features across the travel journey:

| Feature | Pillar | Journey stage | Primary persona | Secondary persona |
|---|---|---|---|---|
| **Feature A: Trip Planner** | Plan & Share | Pre-travel | Persona B (Memory Keeper) | Persona A (Explorer, loose planning) |
| **Feature B: Local Match** | Connect | During travel | Persona A (Explorer, seeks authentic contact) | Persona B (Social Planner) |
| **Feature C: Travel Journal** | Plan & Share | During + post-travel | Persona B (Memory Keeper) | Persona A (documents but has no system) |

> **What to write:** Present the MoSCoW table and the 3×3 feature-persona-journey mapping table. Add 2–3 sentences per core feature explaining the design rationale (e.g., why auto-journaling rather than manual; why Local Match is free not paid). Cite research signals for each decision.

---

## Section 5 — System Flow & IA *(15 pts, ~3 pages)*

**Task:** Card sorting → IA sitemap → multi-feature user flow (Onboarding → Dashboard → all 3 features).  
**Textbook anchor:** Dippner (2022), Ch. 7 — Information Architecture & User Flows, Mental Models.

🔲 **Not yet started.** This section requires primary design work.

### 5.1 Card Sorting

> **What to do:** Conduct an open card sort with 5–8 participants using 15–20 cards representing Travel Buddy content and features. Online tool recommended: Maze or Optimal Workshop.
> **What to write:** Document method (open vs. closed, number of participants, cards used), results (top groupings that emerged), and how those groupings informed the IA. Include a dendrogram or similarity matrix if the tool generates one.

### 5.2 IA Sitemap

> **What to design and write:** A hierarchical sitemap showing all screens and their parent–child relationships. Expected top-level structure based on existing research:

```
Travel Buddy App
├── Onboarding
│   ├── Welcome screen
│   ├── Travel style quiz (→ persona-based personalization)
│   └── Permissions (location, notifications)
├── Dashboard (home)
│   ├── Active trip status
│   ├── Discovery feed (peer tips, local match prompts)
│   └── Journal quick-capture
├── Discover
│   ├── Feed (peer-sourced tips by destination)
│   ├── Place detail
│   └── Save to trip
├── Local Match
│   ├── Match profile browse
│   ├── Send connection request
│   └── Chat / meet-up planning
├── Trip Planner
│   ├── Create trip
│   ├── Collaborators
│   └── Itinerary view
├── Travel Journal
│   ├── Auto-captured entries
│   ├── Manual add (photo + note)
│   └── Sharing settings (private / specific people / public)
└── Profile & Settings
    ├── My trips (past + upcoming)
    ├── Local guide profile (if user opts in)
    └── Privacy & notifications
```

> Finalize this structure after the card sort reveals actual user mental models. The above is a hypothesis — card sort results may reorganize it.

### 5.3 Multi-Feature User Flow

> **What to design and write:** One connected flow diagram covering: Onboarding → Dashboard → Feature A (Trip Planner) + Feature B (Local Match) + Feature C (Travel Journal). Show how the three features connect at key moments (e.g., a journal entry can be triggered from a Local Match interaction; a Local Match recommendation can be added to the Trip Planner). This connected logic is what separates Travel Buddy from apps that treat each feature as a silo.

---

## Section 6 — Prototyping & Navigation Design *(20 pts, ~4 pages)*

**Task:** Low-fi sketches → mid/high-fi clickable Figma prototype; document navigation decisions.  
**Textbook anchor:** Dippner (2022), Ch. 8 — Prototypes (8.3), Navigation Design (8.2), Ten Usability Heuristics (8.1).

🔲 **Not yet started.** This is the largest section by points and page count.

### 6.1 Low-Fidelity Wireframes

> **What to design:** Paper or Figma lo-fi sketches for: Onboarding (3 screens), Dashboard (1 screen), each core feature entry point (3 screens). Total: ~7 lo-fi screens.
> **What to write:** 1 paragraph explaining what lo-fi wireframes validate (structure and flow, not visual design) and why they precede high-fi work. Cite Dippner (2022, Ch. 8.3) on prototyping fidelity stages.

### 6.2 Mid/High-Fidelity Prototype

> **What to design:** Clickable Figma prototype covering:
> - Onboarding flow (welcome → travel style quiz → permissions → dashboard)
> - Dashboard
> - Navigation pattern (see 6.3)
> - Feature A: Trip Planner (create trip → add collaborators → view itinerary)
> - Feature B: Local Match (browse profiles → send request → chat)
> - Feature C: Travel Journal (auto-captured entry → add photo → share settings)
>
> **What to write:** Include key prototype screenshots in the submission. Annotate each screen to show design decisions (e.g., why a field is placed where it is, what interaction pattern was chosen and why).

### 6.3 Navigation Design Decisions

> **What to write:** Document the chosen navigation pattern and justify it with evidence. Recommended decision to argue:

**Bottom tab bar (5 tabs: Home · Discover · Trips · Journal · Profile)** because:
- Mobile-first app: thumb-zone accessibility is critical (Nielsen Norman Group research on mobile navigation)
- Users switch frequently between active trip and discovery feed — tabs reduce navigation cost
- Allows Dashboard and Discover to coexist as separate entry points (the Explorer browses Discover first; the Memory Keeper goes straight to Journal)
- Precedent: Airbnb and Polarsteps both use bottom tabs successfully in travel contexts

Alternative considered and rejected: Hamburger menu — hides primary features, increases taps to reach core journeys.

---

## Section 7 — Testing & Refinement *(10 pts, ~2 pages)*

**Task:** Usability test with 3+ users; document what failed, what worked, what changed.  
**Textbook anchor:** Dippner (2022), Ch. 9 — Moderated Usability Testing (9.1); Unmoderated Usability Testing (9.2).

🔲 **Not yet started.** Depends on Section 6 prototype completion.

### 7.1 Test Design

> **What to plan:**
> - Method: Moderated usability testing (think-aloud protocol, task-based)
> - Participants: 3 minimum; recruit from the same archetypes used in interviews (Explorer, Social Planner, Memory Keeper) to maintain consistency
> - Tasks to test: (a) Complete onboarding and reach Dashboard; (b) Find a local tip and save it to a trip; (c) Connect with a local via Local Match; (d) Add a journal entry; (e) Share journal privately with one person
> - Metrics: Task completion rate, time on task, self-reported confusion points (think-aloud quotes)

### 7.2 Findings & Iterations

> **What to write:** A before/after table showing at least 3 design changes triggered by test findings. Format:

| Issue observed | User quote or behavior | Change made | Before / After |
|---|---|---|---|
| [e.g., Users couldn't find Journal from Dashboard] | "I kept tapping Discover by mistake" | Moved Journal quick-capture to persistent Dashboard widget | Screenshots |
| ... | ... | ... | ... |

> This is the highest-signal section for demonstrating UX process maturity. The examiner wants to see that design decisions changed because of evidence — not because of preference.

---

## Section 8 — Portfolio & Strategic Reflection *(10 pts, ~2 pages)*

**Task:** Full UX strategy summary; key decisions + trade-offs; value logic (user + business).  
**Textbook anchor:** Dippner (2022), Ch. 6.1 — UX Strategy (four pillars); Ch. 5.1 — Defining the strategy.

⚙️ **Partially available.** Strategic framing exists across `01_Research_Hypotheses.md` through `03_Competitor_Research_SWOT.md`. This section synthesizes everything rather than presenting new material.

### 8.1 What Problem Travel Buddy Solves, For Whom, and How

> **What to write:** 2–3 paragraphs. Restate the validated problem (fragmentation + distrust + transactional connection) in terms of user experience. Name the two personas and explain how Travel Buddy serves both without compromising either. Reference the three strategic objectives from Section 1.

### 8.2 Key Design Decisions & Trade-offs

> **What to write:** 3–4 decisions worth discussing:

| Decision | Alternative considered | Reason chosen | Trade-off accepted |
|---|---|---|---|
| Non-transactional Local Match | Paid booking model (like Airbnb) | Authenticity research shows paywall undermines genuine connection (Emerald, 2024) | Harder to monetize; requires building trust-based supply |
| Auto-journaling (GPS + one-tap) | Manual journaling | H7 confirmed: travelers abandon high-effort journaling | Privacy concern — must be opt-in, transparent |
| Bottom tab navigation | Hamburger menu | Thumb zone + frequent switching between pillars | Limits tab count to 5; requires careful information hierarchy |
| Peer-sourced tips over star ratings | Algorithmic recommendations | H1 and TripAdvisor weakness confirm distrust of commercial review systems | Quality control becomes editorial challenge at scale |

### 8.3 Value Logic

> **What to write:** Explain how Travel Buddy creates value for users AND for the business, separately:
>
> **User value:** Reduces cognitive load of multi-app juggling (H3); enables genuine local connection without commercial friction (H4); preserves travel memories without effort (H7); respects privacy by default (H8).
>
> **Business value:** Freemium model — core features free, premium for advanced journaling (physical print à la Polarsteps' 100%-revenue model), collaborative features, and enhanced privacy controls. Network effects: every traveler who uses Local Match creates value for local guides; every journal shared brings new users into the app. Data moat: behavioral travel data (anonymized, GDPR-compliant) informs destination recommendations without relying on commercial placements.

---

## References to Include in Submission

All citations already grounded in existing Discovery files. Consolidate into a single reference list:

**Textbook (primary)**
- Dippner, D. (2022). *User Experience Design – Principles & Methods.* SRH Fernhochschule.

**Academic**
- Garrett, J. J. (2011). *The Elements of User Experience* (2nd ed.). New Riders.
- Spies, H. (2014). *UX Strategy.* O'Reilly.
- Portigal, S. (2013). *Interviewing Users.* Rosenfeld Media.
- Martin, B., & Hanington, B. (2012). *Universal Methods of Design.* Rockport Publishers.
- Emerald Publishing. (2024). *15 years of Airbnb's authenticity.* Journal of Humanities and Applied Social Sciences.
- ScienceDirect. (2018). *Tourists' memorable hospitality experiences: An Airbnb perspective.*

**Industry & Market Sources**
- The Strategy Story. (2024). *TripAdvisor SWOT Analysis.*
- Peecho. (2022). *Polarsteps case study.*
- Startuprad.io. (2024). *Polarsteps at 18M users.*
- Streetwise Journal. (2024). *Airbnb SWOT Analysis.*
- MBA Skool. (2024). *Foursquare SWOT Analysis.*
- Rigorous Themes. (2024). *Google Maps alternatives.*
- Kimola. (2024). *Polarsteps feedback analysis.*

> Full URLs available in `03_Competitor_Research_SWOT.md` (Section: References).

---

## Appendix Checklist

- [ ] Survey instrument (full `04_User_Survey.md` or formatted version)
- [ ] Raw survey responses (anonymized)
- [ ] Interview transcripts or notes per participant (P1, P2, P3)
- [ ] Full Figma prototype screenshots (all screens)
- [ ] Card sort raw results
- [ ] Usability test session notes

---

## Progress Tracker

| # | Section | Points | Status | Source files ready? |
|---|---------|--------|--------|---------------------|
| 1 | Process Framing & Planning | 5 | ⚙️ Ready to write | ✅ H1–H10, SWOT |
| 2 | Stakeholder Ecosystem | 10 | ⚙️ Write personas; map ready | ✅ `02_Stakeholder_Ecosystem.md`; ⚙️ personas need synthesis |
| 3 | Research & SWOT | 20 | ⚙️ Instruments ready; data pending | ✅ `03_SWOT`, `04_Survey`, `05_Interviews`; 🔲 data collection |
| 4 | Feature Strategy | 10 | 🔲 Not started | ✅ Sufficient evidence in existing files |
| 5 | System Flow & IA | 15 | 🔲 Not started | 🔲 Card sort needed first |
| 6 | Prototyping & Navigation | 20 | 🔲 Not started | 🔲 Depends on Section 5 |
| 7 | Testing & Refinement | 10 | 🔲 Not started | 🔲 Depends on Section 6 |
| 8 | Portfolio & Reflection | 10 | ⚙️ Strategic material exists | ✅ Synthesis of Sections 1–7 |

---

## Recommended Next Steps (in order)

1. **Distribute survey** (`04_User_Survey.md`) — target 30+ responses before analysis
2. **Conduct 3 interviews** (`05_User_Interview_Guide.md`) — recruit P1 Explorer, P2 Social Planner, P3 Memory Keeper
3. **Synthesize findings** — affinity map → validate/challenge H1–H10 → write Section 3.2
4. **Write personas** (Section 2.2) — based on survey clusters + interview archetypes
5. **Write Sections 1 + 2 + 3** — all evidence is now ready
6. **Write Section 4** (Feature Strategy) — evidence is ready; no new data needed
7. **Run card sort** → build IA → draw user flows → write Section 5
8. **Design lo-fi → hi-fi prototype** in Figma → write Section 6
9. **Run usability tests** → document iterations → write Section 7
10. **Write Section 8** as final synthesis
