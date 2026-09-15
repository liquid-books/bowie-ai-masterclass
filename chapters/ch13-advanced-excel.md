---
title: "Chapter 13: Week 4, Session C — Advanced Copilot in Excel"
subtitle: "Automation, Anomaly Detection, and Scenario Modeling for City Budget Analytics"
short_title: "Advanced Copilot in Excel"
description: "Moving beyond the basics — how City of Bowie employees use Copilot in Excel to build repeatable analytical systems, detect anomalies in contractor billing and infrastructure costs, model budget scenarios and sensitivities, write complex formulas in plain English, and automate recurring analysis with Copilot Cowork. The shift from answering one-off questions to building analysis that runs every budget cycle."
label: ch-13-advanced-excel
tags: [Excel, Copilot, advanced analytics, anomaly detection, scenario modeling, sensitivity analysis, Python in Excel, dashboards, Copilot Cowork, City of Bowie, infrastructure costs, workforce analysis, overtime analysis, department expenditure, contractor invoices, budget analytics, fiscal year closeout, grant reporting, sustainability]
---

```{admonition} Download this Chapter as PDF
:class: tip

```

# Chapter 13: Week 4, Session C — Advanced Copilot in Excel

:::{figure} ../images/ch13-advanced-excel-infographic.png
:label: fig-ch13-infographic
:alt: Illustrated explainer infographic for Advanced Copilot in Excel — showing six capability pillars arranged as a hexagonal system diagram: Repeatable Templates, Anomaly Detection, Scenario Modeling, Complex Formulas, Department Portfolio Dashboards, and Automated Recurring Analysis. Each pillar connects to a central hub labeled "Analytical Systems." Blue and green color scheme with City of Bowie government examples in each segment such as infrastructure cost variance, overtime spikes, and contractor invoice anomalies.
:width: 80%
:align: center

The six pillars of advanced Copilot-in-Excel mastery — each one represents the shift from answering a question to building an analytical system that runs every budget cycle. This chapter maps the journey from power user to institutional asset.
:::

> *"The goal is to turn data into information, and information into insight."*
> — Carly Fiorina

There is a frustration experienced city government professionals recognize immediately. It is not the frustration of not knowing how to do something. It is knowing exactly what needs to be done — the infrastructure project cost comparison, the contractor invoice variance across six capital projects, the overtime picture by department and bargaining unit — and watching hours evaporate in mechanical execution while the actual thinking waits.

Chapter 7 resolved one layer of that. Formatting tables, generating formulas, building Pivot Tables from plain-English questions removed a large share of the mechanical overhead. This chapter operates at a different level.

The distinction between a casual Copilot user and a power user is not knowing more prompts. It is a shift in what you are building. A casual user asks Copilot questions. A power user builds **analytical systems** — templates that run the same rigorous analysis on every budget cycle without being rebuilt, anomaly workflows that flag a mis-billed contractor invoice before a payment is processed, scenario models that answer *"what happens to the department budget if this infrastructure project is deferred to next fiscal year"* in an afternoon rather than a week.

At the City of Bowie that shift is arithmetic, not preference. We serve **more than 70,000 residents** across departments spanning City Administration, Parks & Recreation, Public Works, Finance, Planning, HR, Public Safety Communications, and Constituent Services. The same analysis — expenditure budget versus actual, forecast versus actual labor hours, pre-project estimate versus reconciled cost — repeats dozens of times a year with a different project code or department on top. **That repetition is exactly what justifies automation.** A one-off analysis is worth doing well. An analysis that runs every budget cycle is worth *engineering*.

::::{admonition} 🧭 Accountability Check — Excellence
:class: note

**Accountability: We are answerable for our decisions and actions.**

Excellence at this level is not producing one brilliant analysis. It is producing the *same* correct analysis for the first quarter's expenditure review and the fourth, when the analyst who built it is on leave and someone else is running it. Systems are how accountability survives contact with a full municipal budget calendar.
::::

---

## 1. From Questions to Systems — What Advanced Looks Like

Watch two city finance analysts handle the same request: a monthly cross-department contractor cost and expenditure variance review the Finance Director expects on the first Monday of every month.

**The basic user** pulls the expenditure exports, formats each as a table, asks Copilot for a chart and a Pivot Table, adjusts by hand, pastes into a deck, sends it. Forty-five minutes. Next month, from scratch, again.

**The advanced user** built the analysis once: a defined input zone, validation checks that catch a missing department code or blank contract amount before anything downstream breaks, formulas that recalculate the moment new data lands, a summary populating from one source table, and a documentation sheet so any analyst can run it. Each subsequent month takes eight minutes: paste, refresh, review, send.

The time saving is real but not the point. The point is **institutional leverage**. Errors get caught in design rather than discovered in quarter four. A coordinator who joined last week can run it on day one. And when the Finance Director asks the same question about a different program portfolio, the answer is a copy of the workbook, not a new project.

Copilot is not the hero here. The analytical design is. But Copilot dramatically lowers the construction cost of that design — formula logic, outlier rules, scenario structure — work previously available only to people with deep Excel expertise, which in most city departments means one person, and they are busy.

:::{figure} ../images/ch13-basic-vs-advanced-user.png
:label: fig-ch13-basic-vs-advanced
:alt: Side-by-side comparison infographic contrasting the Basic Copilot User workflow versus the Advanced Copilot User workflow for city budget analytics. Left side shows a linear, manual monthly loop with icons for export, format, analyze, present — labeled "Rebuilt every budget cycle." Right side shows a hub-and-spoke system with a central template feeding automated outputs — labeled "Built once, runs every cycle." Blue and green color scheme, textbook quality.
:width: 80%
:align: center

The basic user answers a question with Copilot. The advanced user uses Copilot to build a system that answers the same question every budget cycle — more reliably, faster, and with less cognitive overhead.
:::

**The three hallmarks of an advanced Copilot user:** **Reproducibility** — the logic is documented and anyone qualified can run it again and get the same answer. **Scalability** — the template works for every project in a department, then every department in the city, then the full capital and operating budget portfolio. **Auditability** — every formula is reviewed and validated before it produces a number that reaches a contractor payment, a grant report, or a City Council presentation. The human is always the last check before output becomes decision.

---

## 2. Building Repeatable Analytical Templates

The most powerful thing you can do with Copilot in Excel is not ask a question. It is design a **template** — a structured workbook producing the same rigorous output every time, regardless of who runs it or which department it points at.

Consider the monthly contractor cost and workforce review. Every department director needs to know how projects performed against budget, how actual labor hours landed against forecast, where overtime concentrated by classification and bargaining unit, and which programs closed below their pre-project cost estimate. Historically that required a dedicated analyst, or a department head building formula chains under deadline during year-end — when the question always arrives.

:::{figure} ../images/ch13-workflow-template-design.png
:label: fig-ch13-workflow-template
:alt: Flowchart infographic showing the five-stage design process for a repeatable analytical template in Excel for city budget data. Stage 1: Data Input Zone (raw expenditure export pasted here). Stage 2: Validation Layer (Copilot-assisted error checks for missing department codes, blank contract amounts, unit mismatches). Stage 3: Calculation Engine (formulas built with Copilot). Stage 4: Summary Output (auto-populating charts and tables). Stage 5: Documentation Sheet (instructions for any user). Blue and green, connected by arrows, white background.
:width: 80%
:align: center

A well-designed template separates concerns across five layers. Copilot accelerates construction of Stages 2, 3, and 4 — the validation logic, formula chains, and summary architecture that previously required deep Excel expertise.
:::

### Designing the Template Architecture

**Step 1 — Define the input zone.** One clean sheet where the raw expenditure export lands. Nothing else lives there. Headers must be identical across every export — the discipline Chapter 7 argued for: `Contract Amount (USD)`, not `Amt`; `Regular Straight Time Hours`, not `Hrs`.

**Step 2 — Build the validation layer.**

> *"My input table has Project Code, Department, Cost Category, Start Date, Contracted Amount (USD), Expenditure to Date (USD), Budget Target (USD), Actual Expenditure (USD), Workforce Forecast Hours, and Workforce Actual Hours. Build validation formulas flagging any row with a missing department or cost category, any blank or zero contract amount where an expenditure exists, any project code appearing twice, and any actual expenditure more than three times the budget target. Explain each formula before generating it."*

"Explain before generating" is not politeness. It is what keeps you in the loop on logic that will run unattended for a year.

**Step 3 — Build the calculation engine.**

> *"Add calculated columns for expenditure variance as a percentage of budget target, contractor cost per project deliverable unit, cost per resident served, workforce hour variance as a percentage of forecast, and overtime as a share of total labor hours. Explain each formula's logic and tell me how each behaves if the denominator is zero."*

That last clause matters. A project with a zero budget target — which happens when a grant fully covers costs — produces a divide-by-zero that cascades through every summary above it.

**Step 4 — Create the summary layer.** Have Copilot propose structure before you build: *"What four or five views would give a department director the clearest picture of program portfolio health in under 60 seconds? Suggest chart types and tell me what each is designed to reveal."*

**Step 5 — Document it.** What data to paste, where it comes from, what each output means, who to call when a number looks wrong. A template only you can run is a productivity tool. A template any analyst can run is an institutional asset — and at a city serving 70,000 residents, only the second kind matters.

::::{admonition} ⚠️ The Approved Rate Rule Still Applies — Especially in Templates
:class: danger

Chapter 7 established the rule: **Copilot can compute on rates. Copilot must never supply them.** Contractor billing rates, wage rates and overtime multipliers by classification, grant reimbursement rates, infrastructure unit costs — these come from the approved contract, the adopted budget, the collective bargaining agreement, or the published rate schedule. Never from a generated answer.

In a template the rule gets *harder*, because the rate is now buried in a design that runs for a year without anyone re-reading it. Two disciplines protect you:

1. **Put every rate in a labeled, dated reference sheet** — `Rate Reference — Source: [contract name or CBA], Effective: [date]` — and have every formula point at that sheet rather than embedding a number inline.
2. **Put an expiry check in the validation layer.** Flag the workbook if the rate reference date predates the project's expenditure period. Contracts and bargaining agreements are renegotiated. A template quietly using last year's rate is the most expensive kind of automation.

A wrong formula produces a number nobody believes. A wrong *rate*, running on a schedule, produces a year of numbers everybody believes.
::::

---

## 3. Advanced Anomaly Detection

Chapter 7 introduced outlier detection as a question you can ask. This section treats it as a system you run.

The stakes are specific here. An anomalous contractor charge per deliverable unit may be a legitimate change order for unforeseen site conditions, or a billing error that becomes a payment dispute after the invoice is processed — the least recoverable moment in the procurement cycle. Budget margin eroding across three consecutive fiscal years for the same recurring program is almost never visible in one expenditure report and almost always visible across the series.

Copilot finds these patterns in seconds. What it cannot do is validate them, investigate them, or decide whether they are a real problem or a normal operating fact. That division of labor is the whole discipline.

:::{figure} ../images/ch13-anomaly-detection-workflow.png
:label: fig-ch13-anomaly-detection
:alt: Three-panel infographic showing the Anomaly Detection workflow for city budget data. Panel 1 (Detect): Copilot flags outliers in a contractor billing dataset — colored markers highlight unusual rows. Panel 2 (Validate): Human analyst cross-references flagged lines against the invoice and the contract — magnifying glass icon over data. Panel 3 (Investigate): Root cause analysis determines whether the anomaly is a data error, a legitimate change order, or a genuine billing problem — branching decision tree. Blue and green color scheme.
:width: 80%
:align: center

Anomaly detection is a three-stage process. Copilot handles Stage 1 with speed and consistency. Stages 2 and 3 — validation and investigation — require operational judgment Copilot does not have.
:::

### What Questions to Ask

Vague questions produce vague flags. The useful pattern defines the **comparison baseline**, the **threshold**, and the **output format** in the prompt itself.

**Contractor invoice and billing anomalies:**

> *"Compare contractor cost per deliverable unit for every invoice line against the median for the same department and the same cost category. Flag any line more than two standard deviations from that median, sorted by dollar impact."*

The baseline is the design decision: same department, same cost category. A Public Works infrastructure project and a Parks & Recreation facility improvement are not comparable, and treating them as comparable flags thirty normal lines and buries the one real billing error.

**Budget target variance outliers by department:**

> *"Calculate actual expenditure versus budget target as a percentage for every project. Group by department and show which departments have a consistent overage pattern — more than half their projects over target — versus which have isolated outliers. Flag the projects driving each."*

That is a different question from "which projects blew their budget target." A department with a *systematic* pattern means the targets are wrong. A department with one bad project means that project was unusual. Different owners, different actions — and only the grouped question distinguishes them.

**Overtime spikes by department and classification:**

> *"Calculate overtime as a percentage of total labor hours for each pay period. Compare each to the median for the same department classification and the same season. Flag any period in the top decile for its department and season."*

Comparing within department classification is essential. A department with a seasonal program peak produces a structurally higher overtime share than one with steady-state operations. A portfolio-wide comparison ranks departments by their program calendar rather than managers by their scheduling decisions.

**Budget erosion program-over-program:**

> *"For every recurring program appearing three or more years, calculate reconciled direct cost per year and identify any where cost increased in each successive year while resident service output held flat or declined. Break out the change in labor cost, contractor cost, and materials cost so I can see which line is moving."*

This is the highest-value anomaly in the chapter and the hardest to see manually, because it is slow. Two percent a year for three years is a six-percent stewardship problem that never once triggered an alarm on a single expenditure report.

**Service delivery rate anomalies:** flag any recurring program where resident enrollment or service delivery rate dropped more than 5 points versus its prior year — and, separately, any program above 70 percent enrollment but below the portfolio median on cost per resident served. That second condition finds programs where residents *are* participating but unit costs are high: an efficiency question, not an outreach question, and one no single-metric ranking surfaces.

### Validating What Copilot Flags

Every flag clears two gates. **Data validation:** tie the line to source — the invoice, the contract, the payroll record, the project log. Export errors, a charge posted to the wrong project code, or a unit mismatch manufactures convincing false positives all day. **Operational validation:** if the data is right, is the pattern explainable? An infrastructure cost spike during an emergency road repair is normal. An overtime surge where the prior contract ran long was probably escalated at the time. Checking context first protects the credibility you will need on the day a flag turns out to be real.

::::{admonition} 🔑 The Anomaly Investigation Protocol
:class: tip

Before treating any flag as significant:

1. **Verify against source.** Pull the same figure from the invoice, contract, or payroll record. Does it match?
2. **Check for known events.** Emergency repair order, a grant-mandated deadline, a staffing gap, or a citywide event compressing the schedule?
3. **Apply the peer comparison.** Is this the only department with the pattern, or does every similar department have it? One is an incident. All of them is a structural issue with the target or the rate.
4. **Escalate or close.** If unexplained and verified, escalate through the department or finance chain. If explained, document the explanation *in the workbook* so the next person running the template does not re-investigate it.

Copilot provides the flag. The protocol provides the judgment.
::::

::::{admonition} 🧭 Responsiveness Check — Understanding
:class: note

**Responsiveness: We listen and act on the needs of our community.**

An overtime outlier is a crew that stayed until 2am to finish an emergency repair. A budget erosion line is a program team absorbing scope creep without saying so. A service delivery gap is a resident who could not access a program they needed.

When a system flags a name — a crew, a department manager, a program — find the explanation before you circulate the ranking. Automated detection scales the finding. It does not scale the fairness. That part is still yours.
::::

---

## 4. Scenario Modeling and Sensitivity Analysis

If one advanced Excel capability has historically required specialized software or a very senior analyst, it is scenario modeling. *"What happens to the department budget if this infrastructure project is deferred to next fiscal year"* sounds simple. Building the model that answers it — defensible assumptions, consistent logic, clear output — is laborious. Copilot cuts the construction time without cutting the rigor, provided you bring the right assumptions.

:::{figure} ../images/ch13-scenario-modeling-framework.png
:label: fig-ch13-scenario-modeling
:alt: Infographic showing a three-scenario budget planning framework in Excel. Three columns labeled Scenario A (Current Scope, Full Timeline), Scenario B (Scope Reduction), Scenario C (Project Deferral). Row labels show Workforce Hours, Overtime Share, Contractor Cost, Materials Cost, Total Direct Cost, and Net Program Cost. Color-coded cells: green for favorable, yellow for neutral, red for stress. A bar chart below compares the three scenario costs. Blue and green color scheme.
:width: 80%
:align: center

A well-structured scenario model presents clear alternatives with consistent assumptions across each. Copilot helps build the formula structure and the visualization — the assumptions themselves come from your operations team, the adopted budget, and the approved contracts.
:::

### The Project Deferral Scenario

A department director asks: the City is considering deferring a major infrastructure rehabilitation project to the next fiscal year. What happens to our cost structure and our program delivery?

"Deferring a project" is not a model input. The inputs are the escalation rate on materials and contractor costs, the workforce hours and classification mix required during the deferral period, the carrying cost of any borrowed funds, the grant compliance deadlines that may be affected, and the resident service impact of delayed delivery. Every one is a real number in a real document, and **Copilot cannot supply any of them.**

So build the assumption layer first: one labeled table, a row per variable, a column per scenario, a source note per row. Every downstream formula reads from this table and nowhere else.

> *"My assumption table has rows for Contractor Hourly Rate, Overtime Multiplier, Standard Work Hours per Day, Materials Unit Cost, Escalation Rate per Month Deferred, Workforce FTEs Required, Project Duration (Months), Grant Compliance Deadline, and Available Budget Appropriation, with columns for Scenario A, B, and C. Build the calculation structure deriving total workforce hours, overtime hours, total labor cost, total contractor cost, and total direct cost for each. Explain each formula and list every assumption the structure makes that I did not explicitly give you."*

That last sentence is the most valuable clause you can put in a scenario prompt. Copilot will make implicit assumptions — how workforce size scales with project scope, whether overtime applies to all hours or only those beyond the threshold, whether escalation is compounded or simple. Enumerating them converts silent risk into a review checklist.

### The Budget Compression Scenario

The most operationally interesting scenario in city government is time, not money. What happens if a project timeline compresses from twelve months to eight?

> *"Using my assumption table, model the workforce impact of reducing available project months from 12 to 8 while holding total required work constant. Assume hours beyond the standard daily window in each remaining month are charged at the overtime multiplier. Show total, straight time, and overtime hours, overtime share, and total labor cost for both cases, plus the incremental cost of compression."*

Build this once and reuse it constantly, because the question recurs on nearly every capital project — a grant deadline is accelerated, a seasonal window closes earlier than expected, a Council resolution changes a project start date. Having the answer in ten minutes instead of a day decides whether the conversation with the City Manager happens before the decision or after it.

### Sensitivity Analysis

A sensitivity table shows how the output moves as one input varies across a range — revealing which assumptions actually matter. *"Build a sensitivity table showing total project cost as overtime share varies from 10 percent to 60 percent in 10-point increments, holding total hours constant at the Scenario B value."*

Run the same structure on the inputs that drive the City's budget: contractor rate escalation against capital project costs, resident enrollment against program unit costs, grant match ratio against net City cost. In most municipal cost models two or three inputs explain nearly all the variance and the rest is noise. The sensitivity table tells you which is which — and therefore where to spend estimating effort on every future project.

### Program Enrollment Forecasting and Grant Compliance Risk

Enrollment is a forecasting problem with a grant compliance deadline at the end of it — an ideal modeling target.

> *"Using the historical enrollment curves in this table — cumulative residents enrolled by week for the last four program years — build a projected enrollment curve for the current program year based on sign-ups to date, and calculate projected final enrollment as a percentage of the grant-required minimum. Then calculate compliance shortfall risk in dollars at the grant threshold for projected enrollment, projected minus 10 points, and projected minus 20 points."*

Then the strategic version: *"Across all four program years, is the enrollment window compressing — are residents signing up later relative to program start each year?"* If the curve is compressing across the portfolio, that changes how outreach is timed and when grant compliance is renegotiated — invisible in any one year, unmistakable across four.

::::{admonition} ⚠️ A Model Is Only As Good As Its Assumptions
:class: warning

This is the defining risk of the chapter.

Copilot will model a scenario built on a wrong assumption with complete confidence, perfect arithmetic, and a beautifully formatted output. It has no mechanism for noticing that your overtime multiplier belongs to a different bargaining unit, that your contractor rate is from last year's contract, or that your workforce ratio came from a project with a different scope. The model will not fail. It will produce a precise, plausible, wrong number — far more dangerous than an obviously broken one, because it gets forwarded.

Three protections:

1. **Source-note every assumption.** Every row gets a source and a date. If you cannot name the document a number came from, it is not an assumption — it is a guess wearing a suit.
2. **Ask Copilot to enumerate its implicit assumptions.** Every time. Then check each one.
3. **Test the model against a project you already closed.** Feed it the known inputs and see whether it reproduces the actual result. A model that cannot retrodict the past has no business predicting the future.
::::

---

## 5. Copilot Cowork — Automating the Analysis That Repeats

Everything so far describes Copilot working inside a workbook you have open, on a task you initiated. That is the right model for building a template. It is the wrong model for **running** one across every budget cycle, every department, every fiscal year.

This is the natural home of **Microsoft 365 Copilot Cowork**, generally available worldwide since **June 16, 2026**. Chapter 7 introduced it for analysis spanning more than one file. Here we use it for analysis that repeats on a **schedule** or fires on an **event** — Cowork supports both. And because it runs in a hosted, sandboxed cloud environment, work proceeds whether or not your laptop is open, which for a city workforce that operates in the field, at public meetings, and across facilities is not a footnote. It is the entire proposition.

### The Monthly Cross-Department Expenditure Variance Report

The template from Section 2 produces the analysis. Cowork runs it without you.

> **Outcome:** A monthly cross-department contractor cost and expenditure variance report covering every project active in the prior calendar month.
>
> **Inputs:** The expenditure files in the SharePoint library *City Budget Reports FY26*, the department and program attributes in *Program Reference Data.xlsx*, and the approved rate schedule in *Contract Rate Reference — Current.xlsx*.
>
> **Definition of done:** One workbook saved to the *Monthly Analytics* folder, named with the reporting month, with labeled tabs — *Summary*, *Cost per Deliverable Unit by Department*, *Contractor vs. In-House Split*, *Budget Target Variance by Project*, *Flagged Lines*, and *Source Notes* listing every file used and the date pulled. Plus a Teams post in *Finance Analytics* with a five-bullet summary and a link.
>
> **Constraints:** Use only rates present in the approved rate schedule — do not infer, estimate, or supply any rate not found there. If the reference schedule's effective date predates any project's expenditure period, flag it on the Summary tab and skip per-unit costs for that project. Flag missing fields rather than filling gaps.
>
> **Approval scope:** Ask before posting to Teams. Do not email anyone.
>
> **Schedule:** The third business day of each month.

That is the five-part structure Microsoft recommends — outcome, inputs, definition of done, constraints, approval scope — with a schedule attached. Notice how much of it is constraints. That ratio is correct. When a human runs an analysis, judgment fills the gaps in the instructions. When a scheduled task runs at 6am on the third while you are at a public works site, the constraints *are* the judgment.

### The Event-Driven Project Closeout Reconciliation

The more powerful pattern fires on an event rather than a date. A project closes. The final workforce actuals file posts to the project's SharePoint library. That posting is the trigger.

The **outcome** is a project closeout reconciliation package. The **inputs** are the contractor invoices, workforce actuals, resident service log, and pre-project cost estimate, all in that library. **Done** means an Excel workbook with a cost bridge from pre-project estimate to reconciled actual, a variance tab isolating contractor, labor, and materials cost contributions, and an exceptions tab listing every line that failed validation — plus a one-page Word summary for the department director and a draft email to the project team, *held for review, not sent*. The **constraints** carry the weight: rates come only from the project's approved contract and the applicable collective bargaining agreement, both in the folder; do not contact any contractor or resident; if a workforce entry is missing a classification code, flag it rather than inferring it from the department. **Approval scope:** ask before sending anything or sharing outside the project team.

The value here is timing, not effort. A reconciliation that starts the moment the last file lands — rather than when an analyst has a free afternoon — closes days earlier. Across a full city project portfolio, that is a materially different reporting position at every quarterly review.

```{list-table} Recurring City of Bowie Analyses Worth Automating with Cowork
:header-rows: 1
:label: table-ch13-cowork-patterns

* - Analysis
  - Trigger
  - Persona
  - Why It Justifies Automation
* - Cross-department expenditure variance report
  - Monthly schedule
  - Finance analyst
  - Same analysis, new projects, every month, forever
* - Project closeout reconciliation package
  - Final workforce file posts
  - Finance / project manager
  - Fires for every capital project; timing beats effort
* - Grant enrollment and compliance exposure review
  - Weekly schedule
  - Grants coordinator
  - Compliance deadlines move; exposure must be current
* - Overtime exception report by department
  - Weekly schedule
  - HR / department director
  - Catches overtime trends while the pay period is live
* - Department portfolio cost roll-up
  - Monthly schedule
  - Department director
  - Multi-project, multi-file, always needed before the quarterly review
* - Cost per resident served benchmark
  - Quarterly schedule
  - Finance analyst
  - Comparing across all programs is beyond manual effort
* - Sustainability and environmental compliance pack
  - Quarterly schedule
  - Sustainability coordinator
  - Cadence is fixed and externally committed
```

Two of those entries deserve a note, because they are effectively impossible by hand and routine once automated. **Cost per resident served benchmarking across all city programs** — direct cost per resident for every program in every department over 24 months, split into labor, contractor, and materials, normalized for program size, and ranked with each department's own trend alongside. Nobody was ever going to build that for a Tuesday budget meeting, and the output separates which programs are structurally expensive from which had unusual project conditions. And **sustainability trend modeling** — emissions per program delivery unit, energy use per city facility, waste diversion rates, water consumption across parks and facilities, normalized by quarter. The City's externally committed environmental reporting is exactly the fixed-cadence work where a scheduled job pays for itself immediately.

::::{admonition} ⚠️ Automation Multiplies Whatever You Built
:class: danger

An analysis with a subtle logic error, run once, produces one wrong answer someone probably catches. The same error on a monthly schedule produces twelve wrong answers, each more credible than the last because the format is familiar and nobody re-reads a report they have seen eleven times.

Before putting any analysis on a schedule:

- **Run it manually at least twice** and verify both outputs against source documents end to end.
- **Require a Source Notes tab** listing every file used and the date pulled. Read it. It is the only way to notice when an upstream file stopped updating.
- **Build in a staleness check** — flag if any input file is older than expected, or if the rate reference predates the project's active period.
- **Set a review cadence for the automation itself.** Once a quarter, re-verify the scheduled job against source. Automation is not fire-and-forget. It is fire-and-audit.

Every Cowork task runs with **your** permissions and sees only what you can see. Data stays in the tenant, permissions are respected, actions are auditable. Microsoft's own guidance stands: always review details before approving. People remain responsible for business decisions — and that does not lapse because the task ran at 6am while you were at a public meeting.
::::

::::{admonition} 🧭 Stewardship Check — Responsibility
:class: note

**Stewardship: We responsibly manage the resources entrusted to us.**

Delegating an analysis to a scheduled task does not delegate accountability for it. If a report reaches a department director with your name in the "prepared by" field, you own it — whether you assembled it at your desk or reviewed it on your phone between a site visit and a community meeting.

The discipline that makes automation safe is non-negotiable: **you read every artifact before anyone else does.** If you would not have time to review it, you do not have time to schedule it.
::::

---

## 6. Python in Excel — The Expanding Frontier

**Python in Excel** brings Python computation directly into Excel worksheets. Instead of a formula, you write Python in a cell and it executes with access to pandas, matplotlib, and scikit-learn, running in a secure Microsoft cloud environment rather than on your machine — which is what makes it viable in an enterprise tenant.

:::{figure} ../images/ch13-python-in-excel-overview.png
:label: fig-ch13-python-excel
:alt: Split-screen infographic showing Python in Excel integration. Left panel shows a traditional Excel formula bar with standard syntax. Right panel shows a Python code cell in Excel with a pandas DataFrame operation and a matplotlib chart of expenditure variance appearing directly in the worksheet. Labels highlight the Python editor, the output cell, and the connection to external libraries. Blue and green, modern design.
:width: 80%
:align: center

Python in Excel removes the separation between spreadsheet analysis and data science computation. Python executes directly in the worksheet, with outputs rendered as values, charts, or tables that integrate with the rest of the workbook.
:::

**Current status, stated precisely.** Python in Excel is generally available across commercial Microsoft 365 subscriptions. **Copilot's ability to write Python inside Excel is expanding but is not confirmed as generally available** as of this writing — in some tenant configurations you can ask Copilot to suggest Python for a cell; in others you cannot. Check your City of Bowie tenant before building a workflow that depends on it. What *is* confirmed: Copilot and Python work side by side — Copilot for formula design, Python cells for computation native formulas handle badly.

**What it enables:** pandas joins a contractor invoice file, a workforce actuals log, and a program service record with mismatched keys and dates far more gracefully than nested lookup chains. `scipy.stats` supports significance testing, which matters when deciding whether a department's overtime share is genuinely different or just noisy across a handful of pay periods. And predicting workforce hours from program characteristics — resident enrollment, program scope, facility type, season — is a regression problem, which is where Python earns its place.

For most City of Bowie employees this is a capability to leverage with IT or analytics colleagues. For those with a Python background, it removes the round trip between the analytical environment and the reporting environment leadership reads.

---

## 7. Natural Language to Complex Formula

Chapter 7 covered formula generation at a foundational level — SUMIFS, XLOOKUP, basic nested logic. Advanced work requires more, and Copilot scales when the prompt is specific. The key insight: **Copilot does not just generate formulas, it explains them.** When it produces a nested condition chain with six paths, the explanation is the only practical way to assess whether the logic matches your intent.

:::{figure} ../images/ch13-complex-formula-examples.png
:label: fig-ch13-complex-formulas
:alt: Infographic showing five advanced Excel formula examples for city budget analytics. Each formula is shown in a code-style box with a plain-language explanation below. Formulas include: nested IF for expenditure variance classification, XLOOKUP for joining department and program attributes, SUMPRODUCT for weighted average contractor rate, dynamic array for multi-project filtering, and the LET function for a readable project risk score. Blue and green accent colors, clean typography.
:width: 80%
:align: center

Five advanced Excel formulas Copilot can generate for city budget analytics — each representing complexity that previously required dedicated formula expertise to build correctly.
:::

### Tiered Classification with Nested Logic

Classifying project performance means applying threshold rules across several dimensions at once — important to get right, painful to build by hand.

> *"Create a 'Project Risk Tier' column. 'Critical' if actual workforce hours exceed forecast by more than 25 percent OR actual expenditure exceeds budget target by more than 20 percent. 'Watch' if either exceeds by 10 to 25 percent, or overtime share is above 35 percent. 'On Plan' if both are within plus or minus 10 percent and overtime share is at or below 35 percent. 'Under' if both are more than 10 percent below plan. Use IFS, explain each layer, and list every combination of inputs that would not be caught by any of these rules."*

That final clause is the professional move. Nested classification fails at the combinations you did not think about — a project 30 percent over on labor and 15 percent under on contractor costs. Enumerating the uncovered cases turns a hidden gap into a design decision.

### XLOOKUP for Attribute Joining

Every operational file needs department, program type, cost center, and funding source attributes joined on before analysis is meaningful. Ask for XLOOKUP formulas pulling those attributes from a Program Reference table onto the project file, matched on Project Code — and specify that a missing code returns `'Unmapped'` rather than an error, plus a count of unmapped rows.

That unmapped count is the point. A join that silently drops eleven projects produces a portfolio analysis confidently missing eleven projects.

### Dynamic Arrays and the LET Function

`FILTER`, `SORT`, `UNIQUE`, and `SEQUENCE` resize themselves as data changes — essential in a template pointed at a different number of projects every month. *"Write a formula extracting every project in the department named in cell B2 where expenditure variance exceeds 15 percent, sorted by dollar variance descending. The output must resize automatically as projects are added or removed, and display 'No projects above threshold' rather than an error when nothing qualifies."*

For any calculation with intermediate steps, `LET` names those steps — converting an unreadable formula into one a colleague can audit.

> *"Build a Project Health Score combining three weighted factors: workforce hour variance versus forecast at 40 percent, expenditure variance versus budget target at 35 percent, and cost-per-resident variance versus the program median at 25 percent. Use LET to create a named intermediate for each, normalize each to a 0–100 scale, then combine into a final score."*

::::{admonition} 🔑 The Formula Explanation Rule
:class: tip

Never accept a Copilot-generated formula without reading its explanation. For every formula, ask: *"Explain what each component does and identify any assumptions this formula makes that I should verify."*

A formula that is logically correct but built on a wrong assumption is more dangerous than one that fails visibly — because it produces plausible-looking wrong answers that pass every glance test between here and the City Council presentation.
::::

---

## 8. Portfolio Dashboards for Department Leadership

A dashboard is not a collection of charts. It is a curated information experience — the most important signals surfacing immediately, supporting context one layer deeper, and the viewer leaving knowing where performance stands and where attention is needed. Copilot accelerates construction. The curation is yours.

:::{figure} ../images/ch13-dashboard-architecture.png
:label: fig-ch13-dashboard
:alt: Dashboard architecture infographic showing a three-layer structure for city program portfolio reporting. Layer 1 (Executive View): four KPI summary cards at the top — Portfolio Expenditure Rate, Contractor Cost Variance, Overtime Share, Resident Service Rate — with trend indicators. Layer 2 (Operational View): two side-by-side charts — cost per resident served by department bar chart and forecast versus actual workforce hours by project. Layer 3 (Detail View): filterable project-level data table. Each layer labeled with its purpose and audience. Blue and green color scheme.
:width: 80%
:align: center

A three-layer dashboard separates executive summary from operational detail from raw data — each layer serving a different audience and depth. Copilot helps build all three; deciding what belongs in each layer requires business judgment.
:::

**What Copilot can do.** Propose the structure before you build:

> *"I am building a monthly program portfolio dashboard for a department director. The data includes project code, department, cost category, funding source, resident service units, contractor cost, budget target and actual, workforce forecast and actual hours, overtime hours, residents served, and reconciled program cost. What four KPIs belong in an executive summary, what supporting visuals belong in an operational view, and what detail layer supports investigation? For each, state what decision it is meant to support."*

Then generate each visual by description: *"Create a clustered bar chart of cost per resident served by department, with a horizontal reference line at the portfolio average, sorted descending."*

**What humans must do.** **Validate every number** — a dashboard built from an export with a formula error propagates it to every card and chart, and a dashboard is the most trusted artifact in the department precisely because it looks resolved. **Curate ruthlessly** — fourteen charts do not communicate, they overwhelm; the hardest skill in dashboard design is deciding what to leave out. **Interpret** — a dashboard shows *what*; a professional explains *why, so what,* and *now what*. Copilot can draft the commentary. What it means for the department, the budget relationship, or next year's program design is yours.

---

## 9. The Verification Discipline in Advanced Analytics

Chapter 7 introduced verification as a safeguard: check formulas, spot-check chart data. At the advanced level the stakes change. A project deferral model shapes what gets funded in next year's capital budget. A budget erosion finding triggers a program review conversation on a long-standing community service. A scheduled anomaly report decides whether a contractor gets a payment adjustment. Complexity raises consequences, and consequences demand proportional rigor.

:::{figure} ../images/ch13-five-step-review-protocol.png
:label: fig-ch13-review-protocol
:alt: Five-step verification protocol infographic presented as a vertical checklist with numbered steps. Step 1: Logic Review — does the formula do what I think it does? Step 2: Assumption Audit — did Copilot make any assumptions I did not specify? Step 3: Boundary Test — what happens at the edges? Step 4: Source Verification — does this tie to the invoice, contract, or approved rate schedule? Step 5: Peer Review — can a qualified colleague validate the key outputs? Each step has an icon and a brief sub-description. Blue and green color scheme.
:width: 80%
:align: center

The Five-Step Review Protocol scales to any complexity level. Apply all five to any Copilot-assisted model before it informs a leadership decision or reaches the public record.
:::

**Step 1 — Logic Review.** Read every formula and ask whether it does exactly what you intended. For complex conditions, trace one example row by hand. Verify the edge cases you know exist — the project with a zero budget target, the workforce entry with no classification code, the grant funded entirely by external sources.

**Step 2 — Assumption Audit.** Ask directly: *"What assumptions did you make that I did not specify?"* Common ones: how ties break in rankings, what happens when a lookup misses, whether percentages use absolute or relative denominators, whether an overtime multiplier applies to all hours or only those beyond a threshold. Every implicit assumption is a potential error with no error message attached.

**Step 3 — Boundary Test.** What does the risk tier formula output for a project exactly 25 percent over forecast — the boundary between "Watch" and "Critical"? Boundary behavior reveals whether the logic is right for all inputs or only typical ones.

**Step 4 — Source Verification.** For anything informing a decision or entering the public record, tie at least three figures to source: a contractor invoice line, a payroll record, a contract line item, a published rate schedule. Any discrepancy gets investigated before you proceed. The formula might be wrong; the export might be wrong. Either way you need to know before someone else finds out.

**Step 5 — Peer Review.** For any model reaching City leadership, Council, or a grant agency, have a qualified colleague review methodology and key outputs first. Not a reflection on your competence — the standard for analysis that drives material decisions.

::::{admonition} ⚠️ The Complexity–Verification Relationship
:class: warning

There is a counterintuitive risk in advanced tools: as building gets easier, the temptation to skip verification grows.

A project deferral model that took two days was scrutinized at every step, because every step hurt. The same model built in two hours *feels* finished long before it has been reviewed. Speed of construction does not reduce the obligation to verify — it makes deliberate, non-negotiable verification more important, not something you do if there is time left.

The rule: **the review budget is set by the stakes of the output, never by the effort of the build.**
::::

::::{admonition} 🧭 Pride Check — Trust
:class: note

**Pride: We take pride in our city and in the quality of our work.**

When a department director takes your portfolio analysis into a City Council briefing, they are not re-checking your arithmetic. They are trusting that you did. That trust is the actual asset — built over years, spent in seconds.

Automation raises the stakes. A number you produced by hand carries your attention. A number produced by a scheduled task at 6am carries it only if you gave it. Be the colleague whose numbers can be trusted, whichever way they were made.
::::

---

## 10. Building the City of Bowie Analytics Playbook

Individual capability is valuable. Institutional capability is transformational. The difference between one analyst who is excellent at Copilot-assisted Excel and a City of Bowie analytics culture is documentation — capturing templates, prompts, assignments, and protocols so any qualified professional can operate at a level that currently requires one specific person.

:::{figure} ../images/ch13-analytics-playbook-structure.png
:label: fig-ch13-playbook
:alt: Infographic showing the structure of a City of Bowie Analytics Playbook. Five sections arranged as notebook tabs: (1) Standard Templates — monthly, per-project, ad-hoc. (2) Proven Prompt and Assignment Library — categorized by analysis type. (3) Verification Protocols — by stakes level. (4) Data Standards — column naming, units, currency, source requirements. (5) Escalation Guidelines — what to flag, who to notify. Blue and green color scheme, clean professional design.
:width: 80%
:align: center

A well-structured playbook converts individual expertise into institutional capability. Each section addresses a distinct failure mode — missing templates, weak prompts, skipped verification, inconsistent data, and unclear escalation.
:::

**Standard Templates** — validated workbooks for the analyses that run on a cadence: monthly cross-department expenditure variance, per-project closeout reconciliation, quarterly cost-per-resident benchmark, weekly grant enrollment and compliance review, and the project deferral and timeline compression models. Each documented for inputs, outputs, and meaning.

**Proven Prompt and Assignment Library** — prompts and Cowork assignments that have produced reliable, validated outputs, organized by analysis type, each recording the context it assumes and its known limitations. The Cowork assignments matter most: a five-part assignment with tested constraints is a genuine asset, and rewriting one from memory every quarter is exactly the waste this chapter exists to eliminate.

**Verification Protocols by Stakes Level** — three tiers: lightweight (internal), standard (shared with department leadership), rigorous (City Council-facing, grant-reported, or publicly disclosed figures). Prevents both under-verification of high-stakes outputs and over-verification that slows routine work to a crawl.

**Data Standards** — column naming with units spelled out, required structure, source documentation, currency normalization, known quality issues in common exports. Prevents the failure mode where the formula is right and the input is wrong.

**Escalation Guidelines** — what a flagged anomaly requires, from whom, through what channel. Prevents under-escalation of real findings and the credibility damage of escalating routine variation.

**How to build it.** Not in a day — in the course of the work. Each time you build a template, record it. Each time an assumption audit surfaces something Copilot assumed silently, add it to the checklist. Each time a flagged anomaly turns out to be normal, document the distinguishing feature so nobody investigates it twice.

The playbook is the institutional return on every hour invested here. It means the analysis does not live in one person's head or one person's laptop. It lives in the City — which, as the largest city in Prince George's County and a community that has grown from a railroad junction to a thriving municipality of 70,000+ residents, sets its own standard for what good government analytics looks like. Nobody else defines that for us. That is a responsibility and an opportunity in the same sentence.

---

## 🧪 Try This — Build a Project Timeline Compression Model


Build a scenario model in Excel using Copilot, then apply the full review protocol before trusting a single output.

::::{admonition} 🧪 Try This: The Timeline Compression Scenario
:class: tip

**Time required:** 30–40 minutes

**Setup.** In a OneDrive workbook, build two tables (Ctrl + T on each).

*Project Profile:* Project Code, Department, Cost Category, Estimated Resident Service Units, Project Duration (Months), Contractor FTEs Required.

*Assumptions:* one row per variable — Contractor Hourly Rate (USD), Overtime Multiplier, Standard Work Hours per Day, Workforce FTEs, Estimated Install Hours per Service Unit, Materials Unit Cost (USD) — with columns for Value, **Source**, and **Effective Date**. Placeholder values are fine.

**Step 1 — Baseline.** *"Using my Assumptions table, calculate total required workforce hours for the project in my Project Profile table, then split those hours into straight time and overtime given the available project months, workforce FTEs, and standard hours per day. Calculate total labor cost. Explain each formula and list every assumption you made that I did not provide."* Read the enumerated assumptions carefully — that list is the most important output of this exercise.

**Step 2 — Compression.** *"Model the same project with the timeline reduced from 12 to 8 months, holding total required workforce hours constant. Show straight time hours, overtime hours, overtime share, and total labor cost for both cases, plus the incremental cost of compression in dollars and as a percentage of baseline."*

**Step 3 — Sensitivity.** *"Build a sensitivity table showing total labor cost as Estimated Hours per Service Unit varies from 6 to 16 in increments of 2, at 8 project months."* Which input moves the answer most? That is where your estimating effort belongs on every future project.

**Step 4 — Approved Rate Rule check.** Go through the Assumptions table row by row. For every value, can you name the document it came from and its effective date? Any blank Source is a guess — and a model built on it is a guess with better formatting. Fix it or flag it on the face of the model.

**Step 5 — Review protocol.** Apply all five steps: logic review on every formula; assumption audit using Copilot's own enumeration; boundary test at zero project months and 100 percent overtime share; source verification against a closed project whose answer you already know; then a colleague on the methodology.

**Step 6 — Write the assignment.** Write (do not run) a Cowork assignment using the five-part structure that would run this model across a department's full capital project portfolio quarterly. Include an explicit Approved Rate Rule constraint and a staleness check on the Effective Date column. Notice how different that feels from writing a prompt — you are specifying a deliverable to a colleague who will work while you sleep, which is the professional shift this chapter has been building toward.
::::

---

## Glossary

```{glossary}
Analytical Template
  A pre-built, validated workbook that produces consistent output when given new input data, letting any qualified user run the same rigorous analysis without rebuilding it.

Anomaly Detection
  Identifying data points that deviate significantly from expected patterns — at the City of Bowie, unusual contractor charges, budget overages, overtime spikes, and program cost erosion.

Approved Rate Rule
  The discipline that Copilot may perform arithmetic on rates but must never supply them. Contractor billing rates, workforce wage rates, and grant reimbursement rates come from the approved contract, the adopted budget, or the collective bargaining agreement — never from a generated answer.

Copilot Cowork
  Microsoft 365 Copilot's delegated-work experience, generally available June 16, 2026. Executes long-running, multi-step, multi-file tasks in a hosted cloud environment and returns finished artifacts. Supports scheduled prompts and event-driven tasks, and keeps working while your device is off.

Cost per Resident Served
  Total direct cost divided by residents served — the primary normalization metric for comparing programs of different sizes and benchmarking across departments.

Event-Driven Task
  A Cowork pattern that runs when something happens — a file posting, an invoice arriving — rather than on a fixed schedule. The natural trigger for project closeout reconciliation.

LET Function
  An Excel function that names intermediate calculations within a formula, making complex logic readable and auditable — essential for any composite score a colleague must review.

Budget Erosion
  A sustained increase in program cost year-over-year without a corresponding increase in resident service output. Rarely visible in one expenditure report; reliably visible across a multi-year series.

Project Timeline Compression
  A reduction in the available project window without a matching reduction in required work — a common scenario in municipal projects, driven by grant deadlines, seasonal constraints, or Council directives, and primarily increasing overtime costs.

Python in Excel
  A Microsoft 365 feature allowing Python to execute directly within Excel worksheets, accessing pandas, matplotlib, and scikit-learn, running in a secure Microsoft cloud environment.

Scheduled Prompt
  A Cowork pattern that runs a defined assignment on a recurring cadence, producing finished artifacts without a human initiating each run.

Sensitivity Analysis
  Showing how an output changes as a single input is systematically varied, revealing which assumptions actually drive the result and which are noise.

Bargaining Unit Classification
  The labor agreement and work rules governing a city workforce classification — rates, overtime thresholds, and the applicable collective bargaining agreement. The correct comparison baseline for any workforce anomaly analysis.
```

---

## Discussion

Using Copilot as a system-building accelerator rather than a question-answering tool changes how analytics creates value at the City of Bowie. Instead of one-off analyses living in individual inboxes, advanced workflows build infrastructure that scales across the full annual program portfolio, all city departments, and every budget cycle.

Consider the analyses you produce regularly. Which are genuinely the same analysis with a different project code or department on top? What would it take to turn one into a template, then into a scheduled Cowork assignment? And what would have to be true about your verification discipline before you would let it run without you?

::::{admonition} 📝 Discussion Guidelines
:class: note

Post your reflection in the course discussion forum before the next session. Your response should:

- Identify one recurring analysis in your role — contractor cost variance, workforce forecast-to-actual, grant enrollment, project closeout, sustainability reporting — that repeats often enough to justify building as a system rather than running by hand
- Address the relationship between analytical speed (which Copilot increases) and verification rigor (which must not decrease), with specific reference to the Approved Rate Rule
- Respond to at least **two peers** with substantive feedback — engage with their specific examples and reasoning, build on their ideas, or respectfully challenge their assumptions
- Include at least one citation from a credible source (Microsoft documentation, municipal government best practices, or City of Bowie operational guidance) supporting a claim in your response

Minimum 300 words for your main post.
::::

---

## Leader's Takeaway

Advanced Copilot in Excel changes the role of analysis at the City of Bowie. When a project deferral model takes two hours instead of two days, and a monthly expenditure variance report runs on a schedule instead of an analyst's Tuesday, the question is no longer whether to do the analysis. It is whether the organization has the discipline to do it well at that speed and volume.

The leaders who extract the most will invest equally in two things: the technical infrastructure — templates, prompt and assignment libraries, verification protocols, data standards — and the culture that makes it safe: rigorous review as habit, assumptions that carry a source and a date, and the absolute non-negotiability of the Approved Rate Rule.

Automation multiplies whatever you built. Build carefully, verify deliberately, audit on a cadence — because a wrong number produced once is an incident, and a wrong number produced on a schedule is a policy.

Copilot makes analytical systems easier to build. The verification discipline, the playbook, and the operational judgment that reads a variance and knows whether it means a crew worked overtime on an emergency repair or a rate was misapplied on a contractor invoice remain irreducibly human. Speed without rigor is acceleration toward error. Rigor enabled by speed is competitive advantage for the residents we serve.

The goal, as always, is not to automate judgment. It is to give judgment better raw material — and more time to actually exercise it.
