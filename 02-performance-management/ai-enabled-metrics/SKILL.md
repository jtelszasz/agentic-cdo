---
name: ai-enabled-metrics
description: >
  Help city staff identify new AI-enabled performance measures for existing government problems. Use this skill
  whenever someone describes a city service, program, or operational challenge and wants to think about what
  new metrics AI could enable — or when they mention performance measurement, KPIs, metrics, 311, service
  delivery measurement, outcome measurement, or say things like "how should we measure this," "what should
  we be tracking," "our current metrics don't tell us much," "we need better data on this," or "how do we
  know if this is working." Also trigger when someone references the xG/Expected Goals framework for
  government, the four-type AI performance measure typology, or asks about measuring process quality vs.
  outputs. This skill is designed for practitioners — city staff, CDOs, performance managers, innovation
  teams — not academics.
---

# AI-Enabled Performance Measure Brainstorming

## Purpose

This skill helps city government staff move beyond traditional output and outcome metrics by applying a
four-category typology of AI-enabled performance measures to their specific operational challenges.

The core insight: AI doesn't just help cities count faster. It enables fundamentally new types of measurement
that reveal what traditional metrics hide. Two of these categories are genuinely new capabilities that didn't
exist before modern AI. Two are techniques that existed but were only feasible for the most well-resourced
cities — AI now makes them accessible to everyone.

## The Typology

### Genuinely New Capabilities

**1. Surfacing Invisible Work**
Extracting structured metrics from the digital exhaust of how work actually happens — emails, case notes,
system logs, workarounds — that the official measurement system never captured. AI reads what humans
generate in the course of doing their jobs and turns it into measurable data.

Key questions to probe:
- What informal communications happen to make the formal process work?
- Where do staff use workarounds, side channels, or manual follow-ups?
- What gets written in free-text fields, case notes, or email that never becomes a metric?
- Are there system logs or timestamps that could reveal how work actually flows vs. how it's supposed to?

**2. 360° Context Intelligence**
Synthesizing across all available signals — text, photos, video, lidar, geolocation, sensor data, timestamps,
historical patterns — to assess the actual meaning and quality of a government action or interaction.
Individual analysis techniques existed before; the integrated multimodal judgment is new.

Key questions to probe:
- What data types are generated during service delivery? (photos, GPS, text, sensor data, video, etc.)
- Is there a verification gap — do you trust that completed work was actually done and done well?
- Could you assess quality or severity better if you combined multiple data sources?
- Are field staff uploading photos, logging GPS, or generating other data that nobody systematically reviews?

### Newly Scalable (existed but now feasible for any city)

**3. Expected Outcomes**
Modeling what should happen — or should have happened — given circumstances like seasonality, staffing,
caseload complexity, and weather, then measuring the gap between expected and actual. This is the literal
Expected Goals (xG) of government. The technique has existed for 15+ years but previously required
dedicated data science teams. AI makes it feasible for any city.

Key questions to probe:
- What external factors affect performance that your current metrics don't account for?
  (weather, seasonal demand, staffing levels, caseload complexity, budget cycles)
- Do you compare raw numbers across time periods or units without adjusting for difficulty?
- Could the same output number mean very different things depending on context?
- Are there cases where staff are being penalized (or rewarded) for circumstances outside their control?

**4. Equity Gap Measurement**
Comparing actual service delivery patterns against expected patterns to isolate unjustified disparities — not
"are outcomes equal" but "are outcomes equal given equivalent conditions." Simple disparity analysis never
required AI; the adjusted version that controls for confounding factors does at scale.

Key questions to probe:
- Do you currently track any service delivery metrics by geography, demographics, or neighborhood?
- If outcomes differ across areas, do you know whether those differences are explained by
  legitimate factors (distance, call volume, case complexity) or indicate actual inequity?
- Is there a population that might be underserved but doesn't show up in complaint-driven data
  because they don't use the reporting system?
- Could the quality (not just quantity) of service differ across populations in ways you can't currently see?

## Workflow

### Step 1: Understand the Problem

When someone describes a city challenge, gather enough context to generate useful measure ideas.
Don't interrogate — have a conversation. But make sure you understand:

**The service or program:**
- What does this department/program actually do day-to-day?
- Who are the "customers" (residents, businesses, other agencies)?
- What's the process from start to finish?

**Current measurement:**
- What do they currently track? (Be specific — get the actual metric names and definitions)
- What do those metrics tell them? What do they NOT tell them?
- What questions can't they answer with current data?
- Are current metrics mostly outputs (things done) or outcomes (conditions changed)?

**Known pain points:**
- Where do they suspect the metrics are misleading or incomplete?
- What do frontline staff know that doesn't show up in the data?
- Have there been surprises — situations where metrics looked fine but reality wasn't?

**Available data:**
- What systems generate data? (311, permitting, CRM, GIS, fleet GPS, body cameras, etc.)
- What data exists but isn't used for measurement? (emails, free-text fields, photos, logs)
- Are there external data sources they could tap? (census, satellite, social media, sensor networks)

Ask follow-up questions for anything unclear. You need enough specificity to generate measures
that are grounded in their reality, not generic suggestions that could apply to any city.

### Step 2: Identify the Measurement Gaps

Before brainstorming new measures, name what's missing. Common gaps:

- **Counting activity, not quality:** "We know how many inspections we did, but not whether they were good inspections."
- **Ignoring context:** "Our numbers look bad in winter but that's because of weather, not performance."
- **Missing the informal process:** "Half the work happens over email and none of that is tracked."
- **No verification:** "We mark things complete but we don't really know if they were done right."
- **Blind spots in who's served:** "We respond to whoever calls, but we don't know who isn't calling."
- **Lagging indicators only:** "By the time it shows up in our data, it's already a problem."

State what you see as the key gaps clearly and directly. Get confirmation before moving on.

### Step 3: Brainstorm New Measures by Category

For each of the four categories, generate 2-3 specific, concrete new measures that address the
identified gaps. Not every category will apply to every problem — that's fine. Skip categories that
don't fit rather than forcing weak suggestions.

For each proposed measure:
- **Name it** — give it a clear, plain-language name that a department director would understand
- **Define it** — one sentence on what it measures
- **Explain what it reveals** — what would this tell you that you can't see now?
- **Describe the data inputs** — what existing data would feed this measure?
- **Flag the difficulty** — is this easy to implement, moderate, or hard? What's the main barrier?

### Step 4: Apply the Quality Gate

Before presenting measures to the practitioner, evaluate each proposed measure against these six
criteria, drawn from GovEx, ICMA, GFOA, Results-Based Accountability, and What Works Cities
standards. A measure failing two or more criteria should be revised or dropped before Step 5.

**Criterion 1: SMART-I Validity**
*(ICMA Getting Started Guide; GFOA Performance Measures best practice; What Works Cities 43-criterion standard)*

- **Specific** — Would two different analysts independently produce the same number?
- **Measurable** — Can it be consistently quantified or scored?
- **Achievable** — Is it feasible with available data and city capacity?
- **Relevant** — Does it directly address a gap identified in Step 2?
- **Time-bound** — Can it be reported on a schedule that matches the decision cycle?
- **Inclusive** — Does it disaggregate by geography or demographics, not just report an aggregate average?

Fail condition: Any of S/M/A/R/T are No, or the measure produces only population-level averages
with no path to disaggregation.

**Criterion 2: Causal Chain Placement**
*(RBA "How Much / How Well / Better Off" framework — Friedman; GovEx Performance Alignment Guide)*

Classify the measure: Input / Activity / Output / Outcome / Impact.

Does the department control the levers that drive this measure? A measure at the Outcome or Impact
level where government controls less than half the variance requires an explicit caveat. An output
measure needs a paired quality or outcome indicator — otherwise you're just counting activity.

Fail condition: Measure is at the wrong level for the stated purpose, or the department has no
meaningful leverage over the measured variable.

**Criterion 3: Data Readiness**
*(What Works Cities Certification criteria; GovEx Data Inventory Guide — labs.centerforgov.org)*

Rate each measure before presenting it:
- 🟢 **Green** — Data already exists in a maintained system; minimal lift required
- 🟡 **Yellow** — Data exists but requires extraction, system joins, or NLP processing
- 🔴 **Red** — Requires new data collection infrastructure or vendor procurement

Red measures should be presented as longer-term aspirations unless the practitioner confirms
capacity. Always surface the rating explicitly so practitioners can sequence implementation.

**Criterion 4: Causal Distance**
*(Formalizes the causal distance guidance in the "Important Guidance" section below)*

Rate 1–4:
- **1 (Direct)** — Government controls the process being measured (e.g., time-to-completion)
- **2 (Near)** — Government action is one step from the outcome (e.g., quality → re-inspection rate)
- **3 (Moderate)** — Outcome is influenced by government but shaped by many external factors
- **4 (Distal)** — Outcome depends primarily on forces outside government control

For measures rated 3 or 4, add this caveat explicitly: *"This measure is several causal steps from
the program's direct actions. Use alongside companion leading indicators."*

**Criterion 5: Goodhart's Law / Gaming Risk**
*(ICMA practitioner literature on perverse incentives; behavioral public administration)*

Ask: If this became an official KPI reported to leadership, what behavior would it incentivize?
Could a rational staff member hit the number without improving the underlying condition?

Common examples:
- Closure Rate → incentivizes fast closure, not resolution quality
- "Inspections completed" → incentivizes volume over thoroughness
- "Calls answered in under 2 minutes" → incentivizes short calls, not call quality

Fail condition: A clear perverse incentive exists AND no companion measure is proposed to
counterbalance it. Either revise the measure definition or require a paired metric before recommending.

**Criterion 6: Equity Representation**
*(GFOA equity framework; Urban Institute Elevate Data for Equity; What Works Cities Standard)*

Ask three questions:
1. **Denominator problem** — Is the denominator the full eligible population, or only those who
   engaged with the system? Complaint-driven data structurally undercounts low-engagement populations.
2. **Formal channel dependence** — Does the measure require residents to have used 311, a web portal,
   or another formal channel that not all residents use equally?
3. **Disaggregation path** — Can the measure be reported by neighborhood, income, or demographics
   with available or obtainable data?

Fail condition: The measure's structure systematically excludes underrepresented residents from
the numerator or denominator, with no correction mechanism proposed.

### Step 5: Prioritize

After presenting options, help the user think about what to pursue first. Consider:
- Which measures address their most urgent blind spots?
- Which ones use data they already have vs. requiring new collection?
- Which would be easiest to explain to elected officials and the public?
- Which could produce a quick win that builds support for more ambitious measures?

Don't overwhelm. If you've generated 8-10 possible measures, help narrow to 2-3 to start with.

## Important Guidance

**Be concrete.** "Use AI to analyze 311 data" is useless. "Run NLP on 311 resolution text to score
whether each response was substantive vs. boilerplate, producing a monthly Resolution Quality Rate
alongside your existing Closure Rate" is useful.

**Respect what exists.** Current metrics aren't worthless — they're the foundation. New measures
supplement, not replace. Frame additions as "and also" not "instead of."

**Acknowledge difficulty honestly.** Some of these measures require data integration work, technical
capacity, or political will that a city may not have. Say so. Suggest what's feasible now vs. what's
a longer-term aspiration.

**Watch for causal distance.** AI-enabled measures work best where government controls most of the
process (permitting, maintenance, service requests). They get harder and higher-stakes as you move
toward outcomes shaped by forces beyond government's control (crime, public health, homelessness).
Be honest about where models explain 30% of the variance and where they explain 80%.

**Don't oversell AI.** The point is never "AI is amazing." The point is "we've been asking the wrong
questions, and now we have tools that let us ask better ones."

## Resources and Professional Standards

These authoritative sources inform the skill's typology and quality criteria. Practitioners who want
to deepen their understanding of government performance measurement should start here.

### Bloomberg Center for Government Excellence (GovEx) — Johns Hopkins University
- Performance Management Getting Started Guide: govex.gitbook.io/performance-management-getting-started-guide/
- Setting Performance Targets Guide: govex.gitbook.io/setting-performance-targets-getting-started-guide/
- Benchmarking Guide: govex.gitbook.io/benchmarking/
- Full guide index: labs.centerforgov.org/guides/

### What Works Cities Certification (Bloomberg Philanthropies / Results for America)
The most comprehensive operational definition of a data-driven, well-managed city — 43 criteria
across 8 practice areas. Directly applicable for assessing whether a measurement architecture is
institution-grade.
- whatworkscities.bloomberg.org

### ICMA (International City/County Management Association)
- *Getting Started: Performance Management for Local Government* (PDF guide)
- *Guide to Results-Oriented Government and Performance Measurement*
- *Eleven Ways to Make Performance Measurement More Useful to Public Managers*
- icma.org/topic-search/performance-management

### GFOA (Government Finance Officers Association)
- *A Performance Management Framework for State and Local Governments* — the most rigorous
  multi-dimensional PM standard for state and local governments
- *Performance Measures* best practice statement
- *State and Local Government Performance Management Sourcebook*
- gfoa.org/materials/pmcommission-framework

### Results-Based Accountability (RBA)
Mark Friedman's "How Much / How Well / Better Off" framework is the canonical method for
determining what level in the causal chain a measure belongs — directly applicable to the quality
gate's Criterion 2.
- Friedman, *Trying Hard Is Not Good Enough* (foundational book)
- clearimpact.com/results-based-accountability/

### IBM Center for Business of Government
- *Responsible AI for Public Evaluation* (2025) — framework for integrating AI into performance
  auditing responsibly; addresses bias, human oversight, and evidence-based decisionmaking
- businessofgovernment.org/report/responsible-ai-public-evaluation

### Urban Institute
- *Practical AI Insights for Local Leaders* (2025) — practitioner-focused AI guide for local government
- *Elevate Data for Equity* initiative — methodology for equity-adjusted analysis
- Spatial Equity Data Tool — operational example of the equity gap measurement typology
- urban.org/elevate-data-equity

### National League of Cities
- *AI in Cities Report* (2025) — landscape of current AI use in local government with governance guidance
- *AI Toolkit for Municipalities* (with Google) — readiness assessment and implementation questionnaires
- nlc.org/resource/ai-report-and-toolkit/
