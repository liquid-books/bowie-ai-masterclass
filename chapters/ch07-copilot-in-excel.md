---
title: "Chapter 7: Week 3, Session C — Copilot in Excel"
subtitle: "Data Analysis, Visualization, and the Death of the Manual Pivot Table"
short_title: "Copilot in Excel"
description: "How Microsoft Copilot transforms Excel into a natural-language data analyst for City of Bowie, Maryland government employees — generating formulas, explaining calculations, cleaning data, surfacing trends, and building charts and Pivot Tables from plain English questions. Built for the Bowie world: Parks & Recreation staffing and scheduling, Public Works project costs, department budget tracking, grant expenditures, city tax receipts, fee collections, contractor comparisons, and fiscal management across all city departments."
label: ch-07-copilot-in-excel
tags: [Excel, Copilot, data analysis, formula generation, data cleaning, visualization, pivot tables, trend identification, outlier detection, City of Bowie, Parks and Recreation, Public Works, Finance, budget tracking, grant expenditures, staffing forecasts, city analytics, Microsoft 365, Copilot Cowork]
---

```{admonition} Download this Chapter as PDF
:class: tip

[Download PDF](https://github.com/liquid-books/bowie-ai-masterclass/raw/main/pdfs/ch07-copilot-in-excel.pdf)
```

# Chapter 7: Week 3, Session C — Copilot in Excel

:::{figure} ../images/ch07-excel-overview-infographic.png
:label: fig-ch07-infographic
:alt: Illustrated explainer infographic summarizing Copilot in Excel's confirmed capabilities — formula generation, data exploration, natural-language charts, Pivot Tables, sorting and filtering, trend identification, and outlier detection — arranged as a capability wheel with City of Bowie government data examples in each segment such as Parks and Rec staffing costs, Public Works infrastructure budgets, department grant expenditures, contractor comparison tables, and city fee collections
:width: 80%
:align: center

Copilot in Excel's confirmed capability pillars — each one eliminating a category of mechanical analytical work that has consumed city department staff, budget analysts, and project managers' time for decades. The shift is not from human to machine. It is from mechanical execution to professional judgment.
:::

> *"The goal is to turn data into information, and information into insight."*
> — Carly Fiorina

Here is a question worth sitting with for a moment.

How much of your last week was spent *thinking* about data — drawing real conclusions from it, making decisions based on it, seeing patterns that changed how you understand a program or project — versus *wrestling* with data? Fighting with formulas. Manually formatting columns. Rebuilding a department budget reconciliation Pivot Table that took 45 minutes and had to be redone when the final staffing report landed. Searching for which row in the contractor invoice log had the inconsistent date format that broke the entire import.

For most City of Bowie employees, the honest answer is uncomfortable. A disproportionate share of what we call "analysis" is actually **data wrangling** — the mechanical, unglamorous labor that precedes the thinking. The thinking is what we were hired for. The wrangling is what we do instead.

That ratio is about to change.

Copilot in Excel does not make you a better data wrangler. It makes data wrangling significantly faster and less painful. What used to take hours — building the right formula, cleaning an inconsistent payroll export, creating a chart, surfacing the outliers in a contractor cost dataset — now takes minutes, and often seconds. The ceiling of what you can ask of your data, without being a data scientist, rises dramatically.

This matters more for city government than it might elsewhere, and the reason is scale and accountability. The City of Bowie serves **70,000+ residents** across Parks & Recreation, Public Works, Finance, Planning, HR, Public Safety Communications, and Constituent Services. Every one of those departments generates data: a staffing schedule, a project budget, a grant expenditure report, a fee collection summary, a contractor invoice log, an infrastructure maintenance tracker. Multiply a 45-minute reconciliation task by dozens of active programs and projects, and you are looking at an ocean of mechanical work that no amount of headcount will ever fully drain. This is exactly the kind of problem where a small per-task saving compounds into something structural.

This chapter covers every confirmed Copilot-in-Excel capability, grounded in what Microsoft's official documentation actually supports today. We will also be direct about the limits — what Copilot cannot reliably do and why that matters in an environment where a miscalculated project cost estimate or a mis-forecasted staffing call becomes a real budget variance, a real audit finding, and a real conversation with a department director or City Council. By the end, you will know how to use these tools effectively *and* how to use them safely.

Every concept lands on a City of Bowie example — Parks & Recreation staffing costs, Public Works infrastructure project budgets, department grant expenditures, city contractor comparisons, tax receipt and fee collection tracking, capital improvement program costs — because that is the data you work with.

::::{admonition} 🧭 Accountability Check — Stewardship
:class: note

**Stewardship: We are responsible stewards of the public trust and city resources.**

Stewardship in an AI-assisted workflow does not mean trusting the machine. It means being the kind of colleague whose numbers can be trusted. When you hand a budget reconciliation to a department director, they are not re-checking your arithmetic — they are trusting that you did. Copilot changes how fast you produce the number. It does not change who is accountable for it.

Throughout this chapter, every capability comes paired with a verification step. That pairing is not bureaucratic caution. It is what Stewardship looks like in practice.
::::

---

## 1. The Foundation — Setting Your Data Up Correctly

Before a single Copilot feature will work in Excel, one thing must be true: **your data must be formatted as a table.**

This is not a minor technical footnote. It is the architectural requirement that makes everything else in this chapter possible. If you send this chapter to your desk drawer after reading it, take one thing with you: format your data as Excel tables.

:::{figure} ../images/ch07-table-format-requirement.png
:label: fig-ch07-table-format
:alt: Side-by-side comparison infographic showing unformatted Excel data on the left — plain rows and columns with no table structure, Copilot icon grayed out — versus properly formatted Excel table on the right with header row highlighted in blue, alternating row colors, and the Copilot icon active in the ribbon. A green checkmark on the right and a red X on the left.
:width: 80%
:align: center

The table format requirement is the foundation that unlocks every Copilot capability in Excel. Without it, Copilot cannot read your data. With it, every feature in this chapter becomes available.
:::

**Why tables are required:**

Copilot in Excel works by reading the structure of your data — understanding which columns contain what kind of information, where the headers are, where the data begins and ends. An Excel table provides exactly that structure in a form Copilot can interpret. A plain range of cells — even one that looks like a table — does not give Copilot the structural information it needs.

This is worth internalizing because most operational data at the City does *not* arrive as a table. A project expenditure report exported from the finance system arrives as a flat range. A staffing schedule emailed by a Parks & Rec supervisor arrives as a formatted block with merged title cells across the top. A contractor invoice extract arrives with three header rows and a blank spacer. Each of those needs 30 seconds of cleanup before Copilot can do anything with it. Thirty seconds is cheap. Not knowing you need to spend it is expensive.

**How to format data as a table:**

1. Click anywhere inside your data range.
2. Press **Ctrl + T** (Windows) or **⌘ + T** (Mac). Or go to **Insert → Table**.
3. Confirm that the "My table has headers" checkbox is checked.
4. Click OK.

Your data is now an Excel table. The Copilot button in the Home tab ribbon will activate immediately.

**Where Copilot can read your files:**

Copilot in Excel works with files stored in **OneDrive** or **SharePoint** — the cloud-connected Microsoft 365 file locations. If you are working from a file saved locally on your device, Copilot functionality requires that file to be synced to OneDrive. The simplest approach: always save your working Excel files to your OneDrive for Business, and Copilot will have full access.

For city staff this has a practical implication that is easy to miss. If you are working from a file you copied to your laptop desktop during a field visit or a site walk, Copilot cannot see it. Save department files to the department's SharePoint library — which you should be doing anyway so the budget team, the project manager, and the post-project reconciliation analyst are all working from one version.

::::{admonition} 🔑 Setup Checklist Before Using Copilot in Excel
:class: tip

Before your first Copilot session in Excel, verify:

- [ ] You are signed into Excel with your City of Bowie Microsoft 365 credentials
- [ ] Your workbook is saved to OneDrive for Business or the department's SharePoint library (not just on your local hard drive)
- [ ] Your data is formatted as an Excel table (Ctrl + T)
- [ ] Your table has clear, descriptive column headers (not "Column A" or "Data 1")
- [ ] The Copilot button is visible and active in the Home tab ribbon

All five? You are ready. Missing any one of them? That is likely the reason Copilot is not responding to your data.
::::

**Column headers matter more than you think:**

Copilot uses your column headers to understand what the data means. A column labeled "Hrs" is harder for Copilot to interpret correctly than one labeled "Scheduled Staff Hours." A column labeled "Amt" is ambiguous — is that budgeted, encumbered, or expended? "Grant Expenditure Amount (USD)" is not ambiguous. A column labeled "PW" could mean Public Works, part-time wage, or project work depending on who built the sheet; "Public Works Project" removes the guesswork.

This is a genuinely city-specific problem. Our operational vocabulary is dense with abbreviations that are perfectly clear to a department budget analyst and completely opaque to a language model: P&R, CIP, FTE, OT, DT, FICA, PO, RFP, FY. Copilot has no institutional memory. Spell it out in the header. Invest two minutes in naming your columns clearly — it pays dividends in every Copilot interaction that follows, and it makes the file readable to the next person who inherits it, which is the more durable benefit.

```{list-table} Column Header Rewrites That Improve Copilot Accuracy
:header-rows: 1
:label: table-ch07-headers

* - Common City Department Export Header
  - Rewrite As
  - Why It Helps
* - `Hrs`
  - `Scheduled Staff Hours`
  - Distinguishes scheduled from actual; avoids ambiguity with overtime
* - `OT Hrs`
  - `Overtime Hours`
  - Fully spells out the labor category Copilot needs to identify
* - `Amt`
  - `Expenditure Amount (USD)`
  - Distinguishes expenditure from budget or encumbrance
* - `Dept`
  - `Department Name`
  - "Dept" alone could be a code or a name
* - `Rate`
  - `Hourly Pay Rate (USD)`
  - "Rate" alone could be tax rate, fee rate, or hourly wage
* - `FY`
  - `Fiscal Year`
  - Fully expands the abbreviation; prevents date-field confusion
* - `CIP`
  - `Capital Improvement Project`
  - Expands acronym to context Copilot can reason about
* - `PO`
  - `Purchase Order Number`
  - Separates identifier from cost or description columns
```

---

## 2. Formula Generation and Explanation — The End of the Syntax Search Loop

Let's start with the capability that will save you the most accumulated time in the shortest period.

Every Excel user has experienced this: you know what calculation you need. You know roughly which function would do it. But the exact syntax — the argument order, the data type requirements, the nested logic — is just out of reach. So you open a browser tab, search "Excel XLOOKUP syntax," read through three different explanations, come back, try it, get a `#REF!` error, go back to the browser, try again.

That loop is over.

:::{figure} ../images/ch07-formula-generation.png
:label: fig-ch07-formula-gen
:alt: Two-panel infographic comparing the old and new formula workflows — left panel shows a frustrated professional with multiple browser tabs open searching for XLOOKUP syntax, right panel shows a clean Copilot pane with a natural language request and the correctly generated formula appearing instantly with a plain-English explanation below it. Blue and orange color scheme.
:width: 80%
:align: center

The formula syntax search loop was never valuable work. It was a tax on knowing what you want but not knowing the exact language to express it. Copilot eliminates that tax — and then explains what it built, so you understand what is in your workbook.
:::

**How formula generation works:**

Open your Excel workbook (in OneDrive or SharePoint, formatted as a table). Click the **Copilot button** in the Home tab ribbon. The Copilot pane opens on the right side of your screen. Describe the calculation you want in plain English:

*"In a new column, calculate the variance between our budgeted project cost and the actual expenditure for each Public Works project. The budget is in the 'Budgeted Cost (USD)' column and the actual is in 'Actual Expenditure (USD)'. Show it as a percentage of budget."*

Copilot reads your table structure, understands the columns you referenced, and generates the formula:
```
=(([@[Actual Expenditure (USD)]]-[@[Budgeted Cost (USD)]])/[@[Budgeted Cost (USD)]])*100
```

Along with the formula, Copilot provides an **explanation** — in plain English — of what the formula does:

*"This formula calculates the percentage by which actual expenditure differed from the budgeted project cost. A positive result means the project came in over budget; a negative result means it came in under. The result is expressed as a percentage of the budgeted amount."*

Copilot then offers to add this formula as a new column in your table. You click "Insert Column" and it is done.

**The dual value of formula explanation:**

Formula generation has an equally valuable counterpart: **formula explanation**. Click on any existing formula in your workbook — including one you inherited, one built by a former colleague, or one in a budget model that has been passed between three department analysts since 2019 — and ask Copilot: *"Explain what this formula does."*

Copilot reads the formula and explains it in plain English. No more decoding nested IF statements during a deadline crunch. No more inheriting a capital project tracking model and spending half a day figuring out what it is actually calculating and why the remaining balance does not tie to the procurement summary. The explanation feature alone is worth hours of time to every City employee who has inherited a complex spreadsheet model — which is essentially everyone in Finance, Planning, and department administration.

**The City of Bowie formulas where this matters most:**

::::{tab-set}

:::{tab-item} XLOOKUP
The modern replacement for VLOOKUP — more powerful, fewer limitations, but with a syntax that trips up even experienced Excel users. Example prompt: *"Look up each project's department and funding source from the Project Reference table on Sheet2, matching on Project ID."* Copilot handles the exact/approximate match setting, the if-not-found argument, and the column direction automatically. This is one of the most common lookups in city budget analysis — joining funding source, department, and program code onto every expenditure record.
:::

:::{tab-item} SUMIFS / COUNTIFS
Multi-condition aggregation — the bread and butter of department budget reconciliation. Example: *"Sum the values in the 'Expenditure Amount (USD)' column where the 'Department Name' column matches 'Parks and Recreation' AND the 'Funding Source' column is 'Grant'."* This one query separates grant-funded spending from general fund spending — the split that drives half of every budget conversation you will have.
:::

:::{tab-item} Nested IF Logic
The formulas that are readable at 9am and incomprehensible when debugging at 4pm. Example: *"Create a 'Staffing Variance Flag' column that shows 'Critical' if actual staff hours exceed scheduled hours by more than 25 percent, 'Review' if they exceed schedule by 10 to 25 percent, 'On Plan' if within plus or minus 10 percent, and 'Under' if actual hours are more than 10 percent below scheduled hours."*
:::

:::{tab-item} Date Calculations
Project timelines, permit deadlines, grant reporting windows. Example: *"Calculate the number of calendar days between the 'Project Start Date' column and the 'Projected Completion Date' column. Then add a 'Deadline Flag' column that marks anything with fewer than 14 days remaining as 'Urgent'."* Projects nearing their deadline without full expenditure are a leading indicator of lapsed grant funds — a genuinely useful early-warning column.
:::

:::{tab-item} Statistical Functions
Standard deviation, percentile ranking, trailing averages. Example: *"Add a column showing the rolling three-month average of 'Fee Collection Revenue (USD)' for each service category."* Rolling averages smooth out distortion caused by one anomalous month and make period-over-period comparison meaningful.
:::

:::{tab-item} Rate and Unit Math
The cost-per-unit calculations that fill every staffing and infrastructure file. Example: *"Add a column that calculates cost per resident served by dividing 'Total Program Cost (USD)' by 'Residents Served', then a second column that flags any program where cost per resident exceeds $50."* Note the threshold — a real policy threshold that Copilot will honor only if you tell it.
:::

::::

**The Plain-English Interpreter:**

Think of it this way. You speak fluent English. Excel speaks fluent Formula. For 30 years, you had to learn Formula — with its exact argument order, its parenthesis matching, its cryptic error codes — to tell Excel what you wanted. Copilot is the interpreter standing between you and the Formula language. You speak English. Copilot hears you, translates to Formula, hands it back with a receipt (the explanation) so you can verify it got the translation right, and then applies it.

The interpreter does not replace your judgment about *what* to calculate. It removes the barrier between your judgment and Excel's execution.

The analogy is imperfect in one important way: unlike a human interpreter, Copilot can occasionally make a mistranslation — generating a formula that looks right but has a subtle logical error. The control for this is the same as it has always been: read the explanation, spot-check the output on several known rows before accepting it for the full dataset, and never let an AI-generated formula reach a budget report, a grant reimbursement request, or a council presentation without verification.

::::{admonition} ⚠️ The Rate and Fee Schedule Rule — Never Trust a Generated Rate
:class: danger

This is the most important warning in this chapter, and it deserves its own box.

**Copilot can compute. Copilot cannot know your rates, fees, or contracted prices.**

Contractor hourly rates, city fee schedules, grant reimbursement rates, union pay scales, utility rates for city facilities, and capital project cost estimates are all governed by approved budgets, signed contracts, adopted fee schedules, and grant award documents. These change by fiscal year, by contract, and by governing body action.

If you ask Copilot *"what is the standard hourly rate for a Parks and Recreation seasonal employee"*, it may produce a confident, plausible, specific number. **That number is a guess.** It is pattern-matched from training data, not read from your HR pay schedule.

The safe pattern is always the same:

1. **You supply the rate** — from the adopted budget, the signed contract, the approved fee schedule, or the grant award document. Put it in a column or a clearly labeled reference cell in the workbook.
2. **Copilot does the arithmetic** — multiply, aggregate, compare, chart.
3. **You verify the result** against a known invoice, a pay record, or a finance system entry before it goes anywhere.

Copilot is an excellent calculator and a terrible rate sheet. Treat it accordingly. A wrong formula produces a number nobody believes. A wrong *rate* produces a number everybody believes — and in city government, that number may appear in a public budget document or a grant audit. That is far more dangerous.
::::

**The revolution in your day:**

Budget analysts and project managers spend an estimated 3–5 hours per week in the formula search loop. At the department director and program manager level, it is less frequent but more costly per instance — because the calculations are more complex, and the stakes of error are higher when the output is going into a council presentation or a grant reimbursement request. Eliminating that friction does not just save time. It changes which analyses you are *willing to attempt*. If building the right formula costs 90 minutes, you run only the analyses worth 90 minutes of setup. If it costs 90 seconds, you run every analysis worth asking.

That is the real unlock. Nobody was ever going to build a cost-per-resident comparison across all Parks & Recreation programs by hand for a Tuesday planning meeting. Now somebody will.

---

## 3. Natural-Language Data Exploration — Asking Questions, Getting Answers

This is the capability that most changes the nature of your relationship with data.

Excel has always been a tool that answered questions you already knew how to ask in Formula. Copilot makes it a tool that answers questions you know how to ask in English. The difference is enormous for professionals who have deep operational knowledge but limited programming fluency — which describes most of the people who actually run city departments and programs.

:::{figure} ../images/ch07-natural-language-exploration.png
:label: fig-ch07-nl-explore
:alt: Infographic showing three natural-language question examples and their outputs — top example shows a department budget question with a resulting Pivot Table, middle shows a staffing hours trend question with a resulting line chart, bottom shows a contractor cost outlier question with a highlighted summary table. Each question is shown in a speech bubble above the result. Blue and orange color scheme, white background.
:width: 80%
:align: center

Natural-language data exploration collapses the distance between "I want to understand this" and "I understand this." Ask a question. Receive a chart, a Pivot Table, or a summary — whichever format best answers it.
:::

**How it works:**

With your data formatted as an Excel table and your file in OneDrive or SharePoint, open the Copilot pane and type your question — not a formula request, but an actual business question:

*"Which Parks and Recreation programs had the highest cost per resident served over the last four quarters?"*

Copilot analyzes your table, runs the relevant calculations, and responds with one of several output types — whichever is most appropriate to the question:

- A **chart** — a visual rendering of the answer (bar chart, line chart, pie chart, etc.)
- A **Pivot Table** — an interactive summary table you can continue to filter and explore
- A **text summary** — a written synthesis of the finding with key numbers highlighted
- A **highlighted range** — specific cells in your table called out for attention

You can also ask Copilot to generate a specific output type: *"Show me this as a bar chart"* or *"Give me a Pivot Table grouped by department and by fiscal quarter."*

**The chart generation workflow:**

Natural-language chart requests are one of the most practically useful Copilot-in-Excel features for City of Bowie staff. The old process — select range, insert chart, configure type, fix axes, fix labels, resize, format — took 15–30 minutes for a non-trivial chart. The new process is a sentence:

*"Create a bar chart showing total expenditures by department for the current fiscal year, sorted highest to lowest."*

Copilot determines the appropriate chart type, maps your data columns to the correct axes, applies labels, and inserts the chart into your workbook. The chart is a standard Excel chart — fully editable, formatted however you need, exportable to PowerPoint with one click. That last property matters enormously when the same numbers have to appear in a council budget presentation or a department quarterly review.

**City of Bowie data exploration prompts that unlock the most value:**

::::{tab-set}

:::{tab-item} Department Budgets & Expenditures
- *"Show me total expenditures by department, split between personnel costs and non-personnel costs."*
- *"Create a Pivot Table showing average monthly expenditure by department and by fiscal year."*
- *"Which departments have the highest ratio of actual spending to budgeted spending? Rank them."*
- *"Give me a line chart of monthly expenditure totals across all departments over the past 18 months."*
- *"How much of the current fiscal year budget has been expended in each department? Show it as a percentage."*
:::

:::{tab-item} Public Works Project Costs
- *"Show me actual project cost versus budgeted project cost by project as a clustered bar chart."*
- *"Which projects exceeded their budget by more than 15 percent? List them with the dollar variance."*
- *"Create a Pivot Table of project cost variance grouped by project type and by fiscal year."*
- *"Is there a relationship between project scope in square feet and cost overrun percentage? Show me a scatter plot."*
- *"What is our aggregate budget variance year to date for capital improvement projects, and which three projects contributed the most to it?"*
:::

:::{tab-item} Parks & Rec Staffing Analysis
- *"Compare scheduled staff hours to actual staff hours by program. Show me the ten largest overages."*
- *"Create a Pivot Table showing regular time, overtime, and double time hours by Parks and Recreation division."*
- *"What percentage of total staff hours were overtime, by program? Give me a sorted bar chart."*
- *"Which facilities have the highest average overtime percentage during summer programming versus off-season?"*
- *"Show me a line chart of total staffing cost per participant by program over the past year."*
:::

:::{tab-item} Grant Expenditures & Reimbursements
- *"Create a Pivot Table showing awarded amount, expended amount, and remaining balance by grant."*
- *"Which grants have a final expended amount more than 10 percent below the awarded amount? List them."*
- *"Show me a summary breakdown of expenditures by grant category — personnel, equipment, services, supplies."*
- *"Summarize total grant reimbursements requested versus received by funding agency."*
:::

:::{tab-item} City Tax Receipts & Fee Collections
- *"What is our collection rate — actual receipts as a percentage of projected revenue — by revenue category?"*
- *"Show me average monthly fee collection by service type as a bar chart sorted descending."*
- *"Which revenue categories have a collection rate above 90 percent but below projected growth? List them."*
- *"Create a Pivot Table of permit fee revenue by permit type and by fiscal quarter."*
- *"Compare this year's fee revenue to last year's for every service category active in both years. Show the percentage change."*
:::

:::{tab-item} Contractor Comparisons
- *"Show me total contracted amount versus billed amount by contractor as a Pivot Table."*
- *"Which contractors are billing above their contracted rate with fewer than 30 days remaining in the contract term? Flag them."*
- *"Create a line chart of cumulative billings by month for the last four major infrastructure projects, overlaid."*
- *"What is our total potential contract overage exposure in dollars across all active contracts?"*
- *"Which contractors show a consistent pattern of billing surges in the final weeks of a contract period?"*
:::

:::{tab-item} Facilities & Capital Infrastructure
- *"Show me total maintenance cost by facility and the resulting cost per square foot."*
- *"What is our capital improvement cost per resident by project type? Give me a ranked bar chart."*
- *"Which facilities have the highest deferred maintenance costs relative to their assessed value?"*
- *"Compare planned maintenance versus completed maintenance by facility. Flag any variance above 8 percent."*
:::

:::{tab-item} Constituent Services & Program Outcomes
- *"Show me total residents served by program, normalized per staff hour."*
- *"Which programs had the highest participation rates relative to capacity? Rank them."*
- *"Create a Pivot Table of resident satisfaction scores by program and by fiscal quarter."*
- *"Show me a trend line of cost per resident served across the last eight quarters for recurring programs."*
:::

::::

**The key insight:**

Natural-language data exploration is not about replacing analytical thinking. It is about removing the mechanical execution barrier between a business question and a data-driven answer. The business question — the *right* question — still requires a professional who understands how city government actually works: why one park facility burns more overtime than another, why a particular grant program skews toward high administrative cost, why one contractor's invoices grow toward contract ceiling faster than another's. Copilot handles the "now let me go build the Pivot Table to answer that" step. You own the "which question is worth asking" step — which is the more valuable one, and the one that serving Bowie residents actually requires.

::::{admonition} 🧭 Accountability Check — Responsiveness
:class: note

**Responsiveness: We are responsive to the needs of our residents and colleagues.**

There is a version of data analysis that forgets there are people inside the numbers. A staffing variance line is an employee who stayed late. A grant shortfall is a program that may not reach the residents it was funded to serve. A contractor billing overage is a budget that cannot accommodate another priority this fiscal year.

When Copilot hands you a ranked list of "highest cost" programs or "worst performing" projects, remember that the ranking is arithmetic and the explanation is human. Go find the explanation before you circulate the ranking. The number is the beginning of the conversation, not the verdict.
::::

---

## 4. Highlighting, Sorting, and Filtering — Copilot as Your Data Navigator

Before we go deeper into analytical capabilities, it is worth spending a moment on a category of Copilot-in-Excel features that are less dramatic but perhaps the most immediately practical: directing Copilot to highlight, sort, and filter your data on your behalf.

:::{figure} ../images/ch07-sort-filter-highlight.png
:label: fig-ch07-sort-filter
:alt: Three-panel infographic showing Copilot sorting and filtering operations on a City of Bowie department budget dataset — left panel shows a natural language filter request isolating projects over budget with the filtered results, center panel shows a conditional highlighting request marking negative balance cells in red, right panel shows a sort request ordering departments by total expenditure. Clean business data aesthetic, blue and orange color scheme.
:width: 80%
:align: center

Highlighting, sorting, and filtering with natural language — the navigational capabilities that make Copilot feel like a data assistant sitting beside you, rather than a tool you have to configure.
:::

**What this looks like in practice:**

*"Highlight the cells in the Budget Variance column where the value is above 10 percent."*
Copilot applies conditional formatting to those cells — red fill, or whatever you specify — so the projects that exceeded their budget are immediately visible without you building a conditional formatting rule manually.

*"Sort this table by total expenditure from highest to lowest."*
Copilot applies the sort. One sentence, done.

*"Filter the table to show only projects where actual expenditure exceeded the budgeted amount."*
Copilot applies the filter. You see only the projects of interest.

*"Show me only the rows where the department is 'Public Works' and the expenditure amount is above $50,000."*
Multi-condition filter. Applied instantly.

*"Highlight every grant where spending is below 55 percent of the award amount and the reporting deadline is within 21 days."*
The grants manager's entire Monday morning, in one sentence.

**Why this matters in a city government environment:**

The value of these capabilities is in their speed and their repeatability. A monthly budget review might involve the same sequence of sorts, filters, and highlights every single time — and each one, done manually, takes a minute or two of clicking and configuring. The Copilot workflow compresses that sequence dramatically and, importantly, keeps your hands off the mouse and your eyes on the data.

It also matters because a lot of this work happens under pressure. You are preparing for a council meeting, it is late afternoon, and you have eleven minutes before the department director walk-through. Typing one sentence beats navigating four menus. This is one of the few software features that is genuinely *better* under deadline stress.

There is also a less obvious benefit: these operations are fully reversible and leave no permanent changes to your underlying data. Copilot's sorts and filters work through Excel's native sort and filter mechanisms — which means clearing them and returning to the full dataset is a single click.

---

## 5. Trend Identification and Outlier Detection — The Analytical Questions That Previously Required an Analyst

Here is where Copilot in Excel makes its most significant leap from tool to analyst.

The features above — formula generation, chart creation, sorting and filtering — are force multipliers on tasks that city staff already knew how to do. This section is different. This is about the questions you never asked your data before, because asking them required either a dedicated analyst or far more manual work than most professionals could justify between one council deadline and the next.

:::{figure} ../images/ch07-trend-outlier-detection.png
:label: fig-ch07-trends
:alt: Infographic showing Copilot in Excel performing trend and outlier analysis on a City of Bowie department performance dataset — top section shows a natural language trend question with a resulting line chart and text summary identifying the three departments with consistently rising overtime costs — bottom section shows an outlier detection request with flagged contractor invoices highlighted in orange and a summary of what made them unusual
:width: 80%
:align: center

Trend identification and outlier detection at the question level — not the chart level. Copilot surfaces patterns you did not know to look for, in datasets too large for manual inspection.
:::

**Trend identification:**

Ask Copilot to identify trends in your dataset — not just "show me this as a chart" but the analytical synthesis that goes one step further:

*"Are there any consistent trends in staffing cost per program participant across Parks and Recreation facilities over the last six quarters?"*

Copilot analyzes the temporal dimension of your data, identifies directional patterns, and returns a text synthesis alongside a supporting chart. It might find: "Three facilities have shown rising staffing cost per participant in each of the last six quarters. Two facilities have shown declining cost per participant over the same period, driven primarily by a lower overtime share of total hours."

That synthesis — which would have required an analyst to manually examine dozens of data points across multiple facilities and construct a narrative — arrives in seconds.

Other trend questions worth running on a recurring basis:

- *"Is our grant expenditure rate rising or falling across programs at the same funding source over the past three fiscal years?"*
- *"Has the ratio of contractor billings to city staff labor shifted over the last eight quarters for Public Works?"*
- *"Is overtime as a share of total staff hours trending in any consistent direction by department?"*
- *"Are resident service requests being resolved faster or slower over the last 12 months?"*

That last one is a genuinely strategic question. If resolution times are lengthening across the portfolio, that changes how staffing should be allocated and where process improvements are most needed. It is exactly the kind of pattern that is invisible in any single month's data and obvious across a year of records.

**Outlier detection:**

Ask Copilot to find what does not fit:

*"Are there any contractor invoices in this billing file that look unusual compared to the typical patterns in the data?"*

Copilot applies statistical analysis to the dataset — looking for values that deviate significantly from the distribution, timing patterns that are anomalous, or combinations of attributes that appear rarely — and surfaces the findings for your review.

In a staffing context: *"Which pay periods have hours per employee significantly higher than others in the same department and the same season?"* Copilot identifies the statistical outliers within each department, rather than just showing you the overall highest hour totals — which matters, because a high total in a high-activity season may be entirely normal.

In a budget context: *"Are there any projects where actual expenditure per square foot is unusually high or low relative to the rest of the capital program?"* Copilot finds the statistical extremes and flags them.

In a grant context: *"Are there any grant programs where the spending rate in the final quarter is meaningfully different from the pattern across the rest of the grants in this file?"*

**The critical professional discipline:**

Here is what Copilot's outlier detection is not: it is not an audit. It is not a fraud detection system. It is not proof of anything. It is a pattern-recognition starting point — a first pass that surfaces *candidates* for human investigation, not conclusions.

An invoice that Copilot flags as a statistical outlier may be:

- A legitimately large infrastructure delivery for a capital project where $500,000 contracts are routine
- A properly documented change order for scope added by approved council action
- A correctly applied prevailing wage rate for a jurisdiction where the standard rate increased at the start of the fiscal year
- A rebill or adjustment entry that looks unusual but is fully reconciled in the finance system
- An actual data entry error or misapplied rate that warrants investigation and possibly a credit

The professional's job is to investigate the flag, not to act on it. Copilot found the needle candidates in the haystack. You decide which ones are actually needles.

**The City of Bowie analytical questions worth asking regularly:**

```{list-table} High-Value Analytical Questions for City of Bowie Professionals
:header-rows: 1
:label: table-ch07-questions

* - Function
  - Sample Copilot Question
  - Output Type
* - Department Budget Oversight
  - "Which departments have shown rising expenditure relative to budget for three or more consecutive months?"
  - Trend summary + line chart
* - Project Cost Control
  - "Are there any projects where actual cost exceeded the budgeted amount by more than 20 percent?"
  - Flagged table + text summary
* - Staffing Cost Management
  - "Which departments have the highest overtime share of total staff hours? Rank them."
  - Sorted summary table
* - Grant Reconciliation
  - "Which grants closed with a final expenditure more than 10 percent below the award amount?"
  - Pivot Table + variance analysis
* - Fee Revenue
  - "Has service fee collection changed significantly for any recurring permit category over the last three fiscal years?"
  - Pivot Table + trend chart
* - Contractor Benchmarking
  - "Which contractors are above portfolio average on cost per deliverable but below average on project completion rate?"
  - Sorted summary table
* - Capital Projects
  - "Show the top 10 capital projects by remaining budget. Do any have spending curves that look unusual?"
  - Highlighted rows + analysis note
* - Infrastructure Maintenance
  - "Are there any facilities where maintenance cost has spiked unusually in the past two quarters?"
  - Trend summary + flagged rows
* - Resident Services Outcomes
  - "Has cost per resident served changed meaningfully at our five highest-volume programs year over year?"
  - Pivot Table + trend chart
```

::::{admonition} 🧭 Accountability Check — Accountability
:class: note

**Accountability: We are responsible for our actions and accountable to our residents.**

Speed creates a temptation. When a variance analysis that used to take a day now takes four minutes, there is an instinct to send it in minute five. Resist it.

Accountability here means that the four minutes you saved get partially reinvested in verification — not pocketed entirely as time saved. A budget analyst who sends a staffing variance report without checking whether the forecast column was the original budget or the amended budget has not saved time. They have deferred a problem to whoever reads it next.

Be accountable to the result, not just the deadline.
::::

---

## 6. Importing Data — Copilot as Your Data Onboarding Assistant

One of the less-discussed but genuinely useful Copilot-in-Excel capabilities is assistance with data import. Copilot can help you bring data into Excel from external sources — including web pages, files in your OneDrive or SharePoint, and information from your organization's Microsoft 365 communications.

:::{figure} ../images/ch07-data-import.png
:label: fig-ch07-import
:alt: Infographic showing Copilot's data import assistance workflow — a hub-and-spoke diagram with Excel at center, and spokes pointing to three data sources: a web source icon labeled 'Web Data', a cloud icon labeled 'OneDrive/SharePoint Files', and an M365 icon labeled 'Org Communications (Teams, Email)' — each spoke labeled with an example city government use case such as Maryland state grant schedules, department SharePoint document libraries, and project update emails from Public Works supervisors
:width: 80%
:align: center

Copilot's data import capability brings external data into your Excel workbook without requiring manual copy-paste or complex Power Query configurations — a meaningful time-saver for the data-pull step that precedes every analysis.
:::

**Importing from web sources:**

You can ask Copilot to pull publicly available data from the web directly into your workbook. For City of Bowie staff, this is most useful for reference data: published Maryland state grant schedules, Prince George's County population benchmarks, published construction cost indices, state employee pay scale reference data, or publicly available municipal benchmark data that you want to combine with internal performance figures.

Example: *"Import the current Maryland state grant program deadlines and award amounts for the following five funding programs into this workbook."*

Copilot attempts to locate the data, import it into a new sheet or table, and link it in a way that can be refreshed. As with all web-sourced data, you should verify the source and accuracy before incorporating it into analytical outputs. And note the rule from Section 2: published *program deadlines and general benchmark data* are fair game for web import. Published *rates and contracted prices* are not — those come from the approved document, not from a search result.

**Importing from OneDrive and SharePoint:**

Copilot can help you pull data from other files in your Microsoft 365 environment — a related workbook, a SharePoint list, or a file a colleague has shared with you. This is particularly useful when building consolidated reports that draw from multiple sources: the payroll export from HR, the project expenditure report from Finance, the contractor invoice log from Public Works, and the grant reimbursement tracker from Administration all live in different places and belong in one budget analysis.

**Importing from organizational communications:**

Copilot can also bring in data from your organization's Microsoft 365 communications — for example, extracting specific figures mentioned in emails or Teams messages into your spreadsheet for tracking. This is a narrower use case but a genuinely useful one for staff who receive regular data updates by email — weekly project progress counts from a Public Works supervisor, monthly fee collection updates from the Finance team, running program enrollment totals from a Parks & Rec coordinator — and want to bring that data into a running workbook without manual re-entry.

Anyone who has ever maintained a project tracker by copying numbers out of dozens of separate emails understands exactly how much time this returns.

---

## 7. Copilot Cowork — When City Analytics Span More Than One File

Everything to this point has described Copilot working *inside* a workbook you have open. That is the right model for most analysis. But a meaningful share of city analytical work does not fit inside one workbook — and this is where **Microsoft 365 Copilot Cowork** changes the shape of the problem.

Cowork became generally available worldwide on **June 16, 2026**, after debuting in Microsoft's Frontier early-access program in March 2026. It was the fastest-growing feature in the history of that program, and at general availability it was in use at more than half of the Fortune 500. The distinction that matters for this chapter is simple:

```{list-table} Chat vs. Cowork vs. Agents — Which One for Which Job
:header-rows: 1
:label: table-ch07-cowork-compare

* -
  - **Copilot Chat / Copilot in Excel**
  - **Cowork**
  - **Agents**
* - **Best for**
  - Conversational analysis inside the file you have open
  - Delegating long-running, multi-step, multi-file work
  - Ready-made helpers for a narrow, repeatable task
* - **How you interact**
  - A conversation — you steer each step from prompt to response
  - An assignment — you describe the outcome and check in at milestones
  - A workflow — you run the same scoped job on demand
* - **Typical pattern**
  - **You're in the loop** — one prompt, one result, you decide what's next
  - **You step away** — Cowork plans, works across files and apps, delivers finished artifacts
  - **You run it on demand** — same task, same shape, every time
* - **City of Bowie example**
  - "Add a budget variance column to this project file and chart it."
  - "Compare infrastructure project costs across our 10 largest capital projects in 5 departments and build me a labeled workbook."
  - A recurring monthly grant-expenditure-rate formatter
```

**Cowork can build workbooks from scratch.** Not just edit the one you have open — *create* an Excel file, with multiple labeled tabs, populated with analysis it assembled by reading across many source files. Microsoft's own flagship demonstration of this pattern produces "an Excel workbook with labeled tabs" as one of three deliverables from a single research assignment.

**The City of Bowie scenario:**

Imagine the request that lands on a Finance analyst's desk in the second week of January: *the City Manager's office wants to understand infrastructure project cost variation across the ten largest capital projects, spanning five departments, for the past two fiscal years — and they want it before the City Council budget workshop on Thursday.*

The old shape of that task: pull ten project expenditure files from ten different SharePoint folders, normalize ten slightly different column layouts, build a consolidated table, join department and funding source attributes, calculate cost per deliverable and cost per resident, split grant-funded from general fund spending, build the comparison views, and assemble it into something presentable. Two to three days of work, most of it mechanical.

The Cowork shape of that task is a single well-scoped assignment:

> **Outcome:** An Excel workbook comparing infrastructure project costs across our ten largest capital projects for the last two fiscal years.
>
> **Inputs:** The project expenditure reports in the SharePoint folder *Capital Projects FY24–FY26*, and the department reference table in *Dept Reference Data.xlsx*.
>
> **Definition of done:** One workbook saved to my OneDrive with these labeled tabs — *Summary*, *Cost by Project*, *Cost per Deliverable by Department*, *Grant vs. General Fund Split*, *Year-over-Year Variance*, and *Source Notes* listing every file used and the date pulled.
>
> **Constraints:** Use only the rates and amounts present in the source files — do not infer, estimate, or supply any cost not found in the data. Flag any project where a required field is missing rather than filling a gap. Keep the Summary tab to one screen.
>
> **Approval scope:** Ask me before sharing the workbook with anyone or sending any email.

That is the whole skill. Not a prompt — an **assignment**, structured in the five parts Microsoft recommends: outcome, inputs, definition of done, constraints, and approval scope.

**Why the "laptop off" property matters for city staff:**

Cowork runs in a hosted, sandboxed cloud environment. Tasks keep running when your laptop is closed. For a desk-based organization that is a convenience. For city staff, it means you can assign work and keep moving.

A project manager preparing for a council presentation does not have a two-hour block to babysit an analysis. They have a site visit at 8, a contractor meeting at 10, a budget review at noon, and a director check-in at 3. What they *do* have is ninety seconds between meetings to describe an outcome, and eleven minutes at the end of the day to review a finished artifact. That is a fundamentally different working rhythm, and it is the one Cowork was built for. As Microsoft puts it: *"It is easy to have a dozen tasks in flight at once, each one moving forward while you focus on what only you can do."*

Other City of Bowie assignments that fit the Cowork shape:

- **Budget reconciliation package.** "Reconcile the payroll actuals, project expenditures, and contractor invoices for this fiscal quarter; produce a workbook with a budget bridge from adopted budget to amended budget to actual, a Word summary for the department director, and a draft email to the Finance team — hold the email for my review."
- **Staffing benchmark analysis.** "Across every Parks and Recreation program we operated in the last 18 months, build a workbook comparing scheduled to actual staff hours, overtime share, and cost per participant, with one tab per facility."
- **Grant compliance review.** "For every active grant, build a workbook showing expenditure percentage, days to reporting deadline, and remaining balance, with an exceptions tab for any grant below 50 percent expenditure inside 45 days of the deadline."
- **Capital program data assembly.** "Pull project cost and completion data from the project reports in this library and build a workbook with cost per square foot and cost per resident served, with a tab per department."
- **Fee revenue year-over-year comparison.** "For every fee category that was active in both years, compare total revenue, volume, and average fee collected; produce a workbook and a one-page summary of the five largest movers in each direction."

**The governance that comes with it:**

Cowork asks permission before sensitive actions — sending an email, posting in Teams, updating a record. You can approve once, approve for similar actions for the rest of the session, scope approval to a specific recipient or domain, approve everything pending at once, or cancel. Medium- and high-risk actions carry a risk indicator. Every task runs with **your** permissions and sees only what you can see. Data stays in the tenant, existing permissions are respected, and actions are auditable.

Microsoft's own guidance is worth quoting plainly: *always review details before approving — check recipients, content, and other details.* People remain responsible for business decisions. That sentence is not a legal disclaimer. It is the operating model.

::::{admonition} ⚠️ Cowork Does Not Suspend the Rate and Fee Schedule Rule
:class: danger

Everything in the Rate and Fee Schedule Rule applies with more force to Cowork, not less — because Cowork works across many files while you are not watching, and a bad rate assumption propagates silently through every tab it builds.

Always include an explicit constraint in the assignment: **"Use only rates and amounts present in the source data. Do not infer or estimate any cost or rate. Flag missing values rather than filling them."**

Then, when the workbook comes back, tie at least one figure per tab to a known finance system entry or a signed contract line before the workbook goes anywhere near a council presentation, a grant auditor, or a department director. A workbook with six beautifully labeled tabs and one wrong contract rate is more dangerous than no workbook at all, because it looks finished.
::::

**A note on cost:** Cowork requires the Microsoft 365 Copilot user subscription license as a prerequisite, and Cowork itself bills on usage, denominated in Copilot Credits. Task cost is driven by four inputs — model use, context retrieval, tool calls, and runtime — and tasks fall roughly into light, medium, and heavy patterns. A ten-project, five-department, two-year multi-file capital program comparison is a heavy task. It is also a task that used to cost two analyst-days. Judge the economics on that comparison, not in isolation.

---

## 8. The Verification Discipline — Why Human Review Is Non-Negotiable

We have now covered seven categories of Copilot capability. Every one of them is real, confirmed, and genuinely useful. And every one of them requires the same professional discipline: **you verify what it produces before you rely on it.**

This is not a caveat to be skimmed past. It is the central professional skill of effective AI-assisted analysis.

:::{figure} ../images/ch07-verification-discipline.png
:label: fig-ch07-verify
:alt: Infographic illustrating the verification discipline for AI-assisted city government analytics — a workflow diagram showing the steps from Copilot output to verified analytical conclusion: Step 1 receive Copilot output, Step 2 check the methodology explanation, Step 3 spot-check against a known invoice or approved budget line, Step 4 validate edge cases, Step 5 sign off as the professional — each step with a brief explanation and a city government example of what can go wrong if skipped
:width: 80%
:align: center

The verification discipline is not optional overhead — it is the professional skill that separates effective AI-assisted analysis from AI-dependent analysis. Copilot does the mechanical work. You own the results.
:::

**Why verification is especially critical in city government:**

In many professional contexts, an AI error costs you embarrassment and a correction. In city government, an analytical error travels fast and lands on the public record. A miscalculated project cost estimate becomes a budget variance that must be explained at a council meeting — in public, on the record. A staffing forecast built on a wrong overtime assumption becomes a labor cost that was not adequately budgeted. A grant expenditure figure that misstates actual spending becomes a finding in an external audit.

There is no outside authority waiting to catch these before they become public. That is precisely why the discipline has to be internal.

**What Copilot gets wrong in Excel:**

Copilot in Excel is powerful, but it is not infallible. Here are the specific failure modes City of Bowie professionals need to watch for:

::::{admonition} ⚠️ Known Copilot Limitation: Data Scope
:class: warning

Copilot can only analyze the data that is in your Excel table. If your expenditure file covers one department but you ask "what were our total project costs for this fiscal year," Copilot will work with what it has — and may produce an analysis that sounds comprehensive but omits other departments. Always be explicit about the period, the department scope, and the funding source scope of your data in your prompts.
::::

::::{admonition} ⚠️ Known Copilot Limitation: Ambiguous Column Names
:class: warning

If your table has ambiguous column names — "Rate," "Hours," "Amount," "Balance" — Copilot may interpret them differently than you intend. A formula calculating "average labor cost" may be using the budgeted rate column when it should be using the actual rate. A balance column may be remaining budget when you meant cash balance. Always check which columns your generated formula actually references, not just whether the result looks plausible.
::::

::::{admonition} ⚠️ Known Copilot Limitation: Formula Logic Errors
:class: warning

Copilot can generate a formula that is syntactically correct — it runs without an error message — but logically wrong. A budget variance calculation may omit the encumbrance amount. An overtime calculation may apply the multiplier to all hours rather than only the hours beyond the regular-time threshold. Spot-check at least three rows manually against known values — ideally against an actual finance system entry — before accepting any AI-generated formula for a full dataset.
::::

::::{admonition} ⚠️ Known Copilot Limitation: Statistical Interpretation
:class: warning

When Copilot identifies "trends" or "outliers," it is applying basic statistical logic to the data in front of it. It does not know your operational context — it does not know that one project's cost spiked because of an approved change order, that a staffing overage reflects a mandatory event coverage requirement rather than poor scheduling, that a contractor's rates increased at the start of a new contract year, or that a grant underspend reflects a program delay approved by the grantor. Context is yours to provide. Copilot finds the statistical signal; you interpret it.
::::

::::{admonition} ⚠️ Known Copilot Limitation: Fiscal Year and Period Confusion
:class: warning

City government operates on a July–June fiscal year that does not align with the calendar year. If your data does not clearly label fiscal year periods in your column headers or data values, Copilot may aggregate across fiscal years incorrectly, confuse calendar year totals with fiscal year totals, or misread period-end dates. Put "Fiscal Year" and "FY Quarter" in your column headers, and never mix calendar-year and fiscal-year data in one table without clearly labeling which is which.
::::

**The verification protocol:**

```{list-table} Verification Steps Before Relying on Any Copilot Output
:header-rows: 1
:label: table-ch07-verification

* - Output Type
  - Verification Step
  - Why It Matters
* - Generated Formula
  - Spot-check against 3+ known values; read the explanation; confirm column references
  - Syntactically correct formulas can be logically wrong
* - Any Rate-Based Calculation
  - Tie the rate to the approved budget, signed contract, or adopted fee schedule
  - A generated rate is a guess wearing the costume of a fact
* - Chart or Pivot Table
  - Verify the underlying data range; confirm the aggregation method; check that totals tie to the finance system
  - Charts can visualize the right data in a misleading way
* - Trend Summary
  - Confirm the period and scope; check the specific data points cited; validate against a manual sample
  - Copilot synthesizes from what it sees; incomplete data produces incomplete analysis
* - Outlier Flag
  - Investigate each flag individually; do not act on a flag without understanding it
  - Statistical outliers are candidates for investigation, not conclusions
* - Imported Data
  - Verify the source; check freshness; cross-reference against the authoritative finance or HR system
  - Web and external data can be stale, incomplete, or unreliable
* - Cowork Workbook
  - Tie at least one figure per tab to a source document; read the Source Notes tab
  - Multi-file work builds on assumptions you did not watch it make
* - Fiscal Period Data
  - Confirm fiscal year and quarter labels are consistent and correct throughout
  - Mixed fiscal and calendar year data produces totals that are confidently wrong
```

**The professional framing:**

A skilled budget analyst does not trust their own formulas without testing them. A skilled project manager does not present a cost report without knowing where the data came from and what it covers. The discipline you apply to AI-assisted outputs should be the same discipline you apply to any analysis — except that AI speeds up the production, which means the verification step must become *more* deliberate, not less, because there is now time pressure to skip it.

Copilot is not the analyst. You are the analyst. Copilot is the tool that removed the mechanical execution barrier between your question and your answer. The professional responsibility for the answer remains entirely yours.

::::{admonition} 🧭 Accountability Check — Pride
:class: note

**Pride: We take pride in our city and the quality of our work.**

Pride in AI-assisted analysis is not "the fastest answer." It is *the same standard of correctness, arrived at faster, with the recovered time spent on something only a person could do.*

If Copilot saves you six hours on a budget reconciliation and you spend one of them meeting with the program team to understand what drove a variance, or talking with a resident about a constituent services issue, or mentoring a new staff member through their first grant report — that is what Pride looks like. If you pocket all six and ship an unverified number, that is not efficiency. That is a defect with a shorter cycle time.
::::

---

## 9. What Copilot in Excel Cannot Do — Knowing the Limits

Being an effective user of any tool requires knowing where the tool ends. Here is an honest accounting of what Copilot in Excel cannot do — based on its documented capabilities and confirmed limitations.

:::{figure} ../images/ch07-limitations.png
:label: fig-ch07-limits
:alt: Clean infographic showing what Copilot in Excel cannot do — organized as two columns: left column shows tasks Copilot can do well with green checkmarks, right column shows confirmed limitations with red X marks. Examples include: cannot access data in other workbooks without import, cannot interpret operational context it was not given, cannot guarantee formula correctness, cannot supply contracted rates or approved fee schedules from documents it has never seen
:width: 80%
:align: center

Knowing the limits is as important as knowing the capabilities. Effective Copilot use requires both — the confidence to use it powerfully and the professional judgment to know where human oversight is mandatory.
:::

**What Copilot cannot do:**

**It cannot access other workbooks automatically.** Copilot in Excel works with the data in the open workbook. If your analysis requires the payroll actuals, the project expenditures, and the contractor invoices, you need to consolidate that data manually (or via Excel's Power Query) before Copilot-in-Excel can work with it. This is precisely the gap Cowork fills — Cowork *can* work across many files — but the in-app Copilot pane cannot.

**It cannot supply your rates, fees, or contracted amounts.** Worth stating twice. Copilot has never seen your adopted budget, your signed contracts, your approved fee schedules, or your grant award documents. Any rate it produces is fabricated. Supply rates; do not request them.

**It cannot guarantee formula correctness.** Copilot generates formulas based on its understanding of your description and your table structure. If your description is ambiguous, or if your table structure is unusual, the formula may be wrong. There is no substitute for spot-checking.

**It does not know your operational or policy context.** Copilot cannot know that a capital project was scope-reduced by council action, that a grant program was paused pending a state agency decision, that a contractor rate increase was approved mid-year, or that last fiscal year's figures were restated after an audit finding. It works with the numbers in front of it. You provide the context that makes those numbers meaningful.

**It cannot settle a billing dispute or audit finding.** Any analysis that feeds a contractor invoice adjustment, a grant reimbursement request, or a budget transfer recommendation requires human validation, documented methodology, and professional sign-off against source documents. Copilot can help build the analysis. It cannot substitute for the reconciliation.

**It cannot write Python code in Excel reliably.** Python in Excel is a real Microsoft feature — it allows Python code to run inside Excel cells. However, Copilot's ability to *write* Python code in Excel (as opposed to formula code) is not a confirmed, generally available feature as of this writing. Do not build workflows around this capability until you have confirmed it works in your specific Microsoft 365 tenant.

**It does not work without a table.** If you have not formatted your data as an Excel table, Copilot cannot read it. Full stop.

**It cannot work offline.** Copilot requires an internet connection and your Microsoft 365 credentials. It is a cloud-connected service. Plan your analysis for a networked environment.

---

## 10. What's Coming — Announced Features to Watch

Microsoft regularly announces new Copilot capabilities before they reach general availability. As a City of Bowie employee, it is useful to know what is on the roadmap — with the clear understanding that announced features are not the same as available features, and the timing of releases frequently shifts.

:::{figure} ../images/ch07-roadmap.png
:label: fig-ch07-roadmap
:alt: Roadmap infographic showing the trajectory of Copilot in Excel capability development — a horizontal timeline from 2023 through 2026 and beyond, with confirmed released features on a solid line and announced upcoming features on a dotted line. Key milestones labeled with brief descriptions. Blue and orange color scheme, clean modern style.
:width: 80%
:align: center

The Copilot in Excel capability trajectory — from its 2023 introduction through confirmed 2025–2026 features and announced capabilities that are in preview or rolling out. The dotted line represents announced but not yet generally available features.
:::

**Advanced Analysis Planning (Preview):**

Microsoft has announced a capability — sometimes referred to in preview communications as "Plan Mode" or "Advanced Analysis" — in which Copilot will outline its analytical approach *before* executing it, giving users the ability to review and adjust the methodology prior to any changes being made to the workbook. This is a meaningful capability for city staff who need to understand and document the methodology behind a budget analysis before it becomes the basis of a council presentation or an audit response.

As of this writing, this feature is in preview for select users and environments — it is not yet confirmed as generally available. If you are interested in whether it has reached your City of Bowie Microsoft 365 tenant, check with your IT administrator or look for updates in Microsoft's M365 admin center.

The underlying goal — giving professionals visibility into Copilot's analytical methodology before it is applied — aligns directly with the documentation expectations of budget reconciliation and grant compliance reporting. When it reaches general availability, it will be an important addition to the professional workflow described in this chapter.

**Python integration:**

Microsoft has announced deeper integration between Copilot and Python in Excel, which would allow natural-language prompts to generate Python analytical scripts running inside Excel cells. This would extend Copilot's analytical reach to statistical modeling and custom data processing that goes beyond Excel's native formula capabilities — forecasting seasonal staffing demand from historical program participation data, for instance, or modeling infrastructure maintenance cost trajectories against capital replacement schedules. This feature is in active development and preview; watch for Microsoft announcements on its general availability.

**Cowork model evolution:**

At general availability Cowork runs on Anthropic's Opus 4.8 and Sonnet 4.6 models, with **Cowork 1** — Microsoft's own secure, fine-tuned, substantially lower-cost model — releasing shortly after. The multi-model design means capability and economics should both improve over time without a change in how you write assignments. Custom skills (up to 50) and App Store plugins are also available to extend what Cowork knows how to do — a natural future home for City of Bowie-specific analytical patterns.

**For the most current feature status:**

- Microsoft 365 Admin Center → Message Center (for your IT administrator)
- [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) — the official source for what is released, in preview, and planned
- Your City IT team — who receive Microsoft communications about tenant-level feature availability

---

## 🧪 Try This — A Complete Copilot-in-Excel Analysis Session

This exercise takes you through the complete workflow — from properly set-up data to analyzed insight — using only confirmed Copilot capabilities. It is designed to be done with real or realistic data in your City of Bowie Microsoft 365 environment.

:::{figure} ../images/ch07-try-this-workflow.png
:label: fig-ch07-try-this
:alt: Step-by-step workflow diagram for the Try This exercise — six numbered steps in a left-to-right horizontal flow: Set up your table, Ask for a formula, Explore with a question, Request a chart, Ask for outliers, Verify everything — each step has a small illustration of the Excel interface at that stage and a 2–3 minute time estimate
:width: 80%
:align: center

The six-step Copilot-in-Excel workflow — from raw data to verified analytical insight. First run: approximately 20 minutes. Repeated use: under 5 minutes once the workflow is familiar and your data is consistently structured.
:::

::::{admonition} 🧪 Try This: A Complete Copilot Analysis Session
:class: tip

**Time required:** 20–25 minutes

**What you need:**
A sample city department performance file. If you do not have one readily available, create a simple table in Excel with these columns:

- Department | Program Name | Facility | Fiscal Quarter | Fiscal Year | Budgeted Cost (USD) | Actual Expenditure (USD) | Scheduled Staff Hours | Actual Staff Hours | Overtime Hours | Residents Served | Programs Active | Total Fee Revenue (USD)

Add 36–60 rows covering 4–6 departments and programs across 3–5 facilities over 12–18 months. The data does not have to be real — round numbers work fine for the exercise. Save the file to your OneDrive for Business.

---

**Step 1 — Set up your table correctly:**
Click anywhere in your data. Press **Ctrl + T**. Confirm "My table has headers" is checked. Click OK. Your Copilot button should now be active in the Home tab ribbon.

**Step 2 — Generate a formula:**
Open the Copilot pane (Home → Copilot). Type:
> *"Add a column that calculates the budget variance percentage — actual expenditure versus budgeted cost — for each program."*

Review the explanation Copilot provides. Before clicking "Insert Column," check: Does the formula reference the correct columns? Does the explanation match what you asked for? If yes, insert it. Then spot-check the result on three rows manually.

**Step 3 — Generate a second, harder formula:**
Type:
> *"Add a column showing the cost per resident served — total actual expenditure divided by residents served — as a dollar amount. Then add a column showing the staffing efficiency rate — residents served per actual staff hour."*

This one has a trap in it: cost per resident could reasonably be divided by residents *in the service area* or residents *actively served*, and those are very different metrics. Check which one Copilot chose. If it guessed differently than you intended, that is the lesson — ambiguity in your prompt becomes ambiguity in your data.

**Step 4 — Ask a business question:**
Type:
> *"Which department has the highest average cost per resident served across all programs in this data? Show me the answer as a chart."*

Review what Copilot produces. Is the chart type appropriate? Do the axes make sense? Does the visual align with what you see when you scan the raw data?

**Step 5 — Request a Pivot Table:**
Type:
> *"Create a Pivot Table summarizing average budgeted cost, average actual expenditure, and overtime hours as a percentage of total staff hours, grouped by department."*

Review the Pivot Table. Verify the aggregation method (average, not sum or count). Confirm that every department appears and the numbers look consistent with the source data.

**Step 6 — Ask for outlier detection:**
Type:
> *"Are there any programs in this table that look statistically unusual — in any column?"*

Review what Copilot identifies. For each flagged item: Can you explain why it might have occurred operationally? A high expenditure in a major capital quarter is normal. A high overtime share during summer recreation programming is normal. If you cannot explain it, is it worth investigating? This step practices the investigative discipline — distinguishing statistical flags from actual anomalies.

**Step 7 — The verification debrief:**
Before you close the workbook, answer these questions in writing (a Teams chat to yourself, a OneNote page, anything):

1. Did I verify the generated formulas against known values?
2. Did any calculation depend on a rate or contracted amount — and if so, did that rate come from the source data or from Copilot?
3. Do I understand the methodology behind each chart and Pivot Table?
4. Is there anything in Copilot's output that I accepted without checking?
5. If this analysis went to a department director or a council member tomorrow, am I confident enough to put my name on it?

**If you answered "no" to question 5** — go back and do the checking before you close. The habit of verifying before sign-off is the professional skill this exercise is building — not the mechanical steps above it.

---

**Bonus (if Cowork is enabled in your tenant):**
Write a Cowork assignment using the five-part structure — outcome, inputs, definition of done, constraints, approval scope — that would produce a multi-tab workbook comparing two of your departments' budget performance year over year. Do not run it yet. Just write it, and notice how different it feels from writing a prompt. You are describing a deliverable to a colleague, not issuing an instruction to a tool.
::::

---

## The Bigger Picture — What Excel Becomes for City of Bowie

Before we close, let's step back and look at what Copilot in Excel actually represents — not feature by feature, but as a shift in professional capability.

Excel has been the world's most widely used data tool for four decades. Through that entire history, its fundamental interaction model remained constant: you, the professional, expressed your analytical intent by constructing formulas, building Pivot Tables, creating charts, and writing macros. The computer executed exactly what you told it to, in the language you had learned. The analytical floor — the minimum you had to know to get useful output — was relatively high.

Copilot lowers that floor dramatically. The professional knowledge required to ask a question of your data is now English fluency, not Formula fluency. The ceiling of what non-programming professionals can analyze without a data science team rises significantly. And the time between "I have this question" and "I have this answer" compresses in ways that change which questions get asked at all.

This is not a replacement of analytical professionals. It is a reallocation of their time. The same professional who was spending 60% of analytical time on mechanical execution — formula construction, table building, chart formatting — can now spend that time on interpretation, judgment, and decision-making. Which is, not coincidentally, what they were hired to do.

:::{figure} ../images/ch07-time-reallocation.png
:label: fig-ch07-time
:alt: Two pie charts side by side showing before and after time allocation for a city budget and program analyst — left chart labeled 'Before Copilot' shows 60% mechanical data work in gray and 40% judgment and insight in blue — right chart labeled 'With Copilot' shows 20% mechanical work in gray and 80% judgment and insight in blue — the insight segment on the right is labeled 'where the value lives' in orange
:width: 80%
:align: center

The fundamental reallocation that Copilot in Excel enables — not from humans to AI, but from mechanical execution to professional judgment. Same professional. Same hours. Dramatically different ratio of valuable work to mechanical work.
:::

**For the City of Bowie specifically:**

Every analytical professional across City departments — every Parks & Recreation coordinator tracking staffing against program budgets, every Public Works project manager reconciling contractor costs to capital budgets, every Finance analyst closing a departmental P&L, every grants coordinator watching expenditure rates against reimbursement deadlines, every Planning analyst preparing a land use cost-benefit summary, every HR analyst reviewing workforce data for council reporting, every Constituent Services manager reading resident engagement metrics — can do more, faster, with better documentation of how they got there.

And there is a standard worth naming. Bowie's **City Values — Accountability, Responsiveness, Stewardship, and Pride** — set the benchmark for how this work is done. Copilot does not change those values. It creates the time and capacity to live them more fully. When an analyst spends less time wrestling with formulas, they have more time to be accountable to the result, more capacity to be responsive to the department director's next question, more room to exercise stewardship over the city's resources, and more opportunity to take pride in work that is thorough and well-documented.

The City of Bowie serves more than 70,000 residents with a staff that is asked to do more with disciplined resources every year. Organizations that build genuine fluency in AI-assisted analytics will simply answer harder questions faster, with more consistent quality, and with more capacity left over for the human work that actually builds resident trust.

But the city-wide benefit starts with a single professional, on a single department file, asking a question they would not have had time to ask before. That is what this session has been building toward.

Start with one department file. Format it as a table. Open Copilot. Ask it something.

See what it shows you.

---

:::{note}
**Chapter 7 — Key Takeaways**

1. **Table format is mandatory.** Copilot in Excel only works with data formatted as an Excel table (Ctrl + T). This is the non-negotiable foundation for everything else in this chapter — and most operational exports from finance, HR, and project management systems do not arrive as tables.

2. **OneDrive or SharePoint is required.** Copilot works with files in your Microsoft 365 cloud storage. A department file on your laptop desktop is invisible to Copilot. Save to the department's SharePoint library.

3. **Column headers are your interface.** Spell out city government abbreviations — FTE, CIP, OT, P&R, FY, PO, RFP — into descriptive headers with units. Copilot has no institutional memory, and neither does the next person who inherits the file.

4. **Formula generation** eliminates the syntax search loop — describe what you want in plain English, receive the formula with a plain-English explanation. Always spot-check against known values before accepting.

5. **Formula explanation** works on any formula, including ones you inherited. Invaluable for the budget models that have been passed between three department analysts.

6. **Never trust a generated rate or contracted amount.** Copilot can compute; it cannot know your adopted budget, contracted rates, or approved fee schedules. You supply the rate from the approved source. Copilot does the arithmetic. You verify against a real finance system entry.

7. **Natural-language data exploration** lets you ask operational questions — staffing cost per participant, project cost variance, overtime share by department, grant expenditure rate, contractor billing against contract ceiling — and receive charts, Pivot Tables, or text summaries as answers.

8. **Trend identification and outlier detection** surface patterns that previously required dedicated analyst time. Treat Copilot's findings as candidates for investigation, not conclusions — a statistical outlier in a major capital quarter is often just an approved change order.

9. **Cowork extends Excel work across files.** Copilot in Excel works inside one workbook; Cowork can create workbooks from scratch with labeled tabs and run multi-file analysis across many projects and departments — and it keeps working while your laptop is off. Write assignments, not prompts: outcome, inputs, definition of done, constraints, approval scope.

10. **The verification discipline is non-negotiable.** Copilot accelerates mechanical execution. Professional accountability for the output remains entirely yours. Verify before you rely — especially on anything reaching a council presentation, a grant audit, or a signed budget transfer.

11. **Watch your fiscal periods.** City government operates on a July–June fiscal year. Label fiscal year and quarter clearly in all column headers. Never mix fiscal-year and calendar-year data in one table without explicit labeling.

12. **The City Values are the frame.** Accountability (be the colleague whose numbers can be trusted), Responsiveness (the four minutes saved is partly reinvested in verification), Stewardship (recovered time spent on decisions only a person can make), Pride (the same standard, arrived at faster, with room left over for the human work that serves residents).
:::

---

:::{seealso}
**Resources for Chapter 7**

- 🤖 Get Started with Copilot in Excel (Microsoft Support): [support.microsoft.com — Copilot in Excel](https://support.microsoft.com/en-us/topic/get-started-with-copilot-in-excel-d7110502-0334-4b4f-a175-a73abdfc118a)
- 📖 Copilot in Excel Help: [support.microsoft.com/excel-copilot](https://support.microsoft.com/en-us/office/how-to-use-copilot-in-excel-d6293023-4fa1-4af7-90a4-40a4dd52a36e)
- 🗺️ Microsoft 365 Roadmap (official feature status): [microsoft.com/microsoft-365/roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap)
- 🧰 Microsoft 365 Copilot Cowork overview: [microsoft.com/microsoft-365/copilot](https://www.microsoft.com/en-us/microsoft-365/copilot)
- 📊 Microsoft 365 Adoption Hub — Copilot: [adoption.microsoft.com/copilot](https://adoption.microsoft.com/en-us/copilot/)
- 🔒 Copilot Data Privacy and Security: [learn.microsoft.com — Copilot Privacy](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-privacy)
- 🏛️ City of Bowie Official Website (city values, departments, and public budget documents): [cityofbowie.org](https://www.cityofbowie.org)
:::

---

```{glossary}
Excel Table
  A structured data range in Microsoft Excel with defined headers, formatted via Insert → Table or Ctrl + T — the required data format for Copilot in Excel to read and analyze your data.

Formula Generation
  Copilot's ability to create syntactically correct Excel formulas from plain-English descriptions, including complex functions such as XLOOKUP, SUMIFS, nested IFs, and statistical calculations.

Formula Explanation
  Copilot's ability to read an existing Excel formula and explain what it does in plain English — useful for understanding inherited budget models or auditing complex calculations.

Natural-Language Data Exploration
  The Copilot capability that allows city staff to ask business questions of their Excel data in plain English and receive answers as charts, Pivot Tables, text summaries, or highlighted ranges.

Trend Identification
  Copilot's analytical capability to detect directional patterns across a temporal dataset — identifying which metrics are consistently rising, falling, or exhibiting change-of-direction signals across departments, programs, or fiscal periods.

Outlier Detection
  Copilot's statistical capability to surface data points that deviate significantly from the patterns in a dataset — candidates for human investigation, not automatic conclusions.

Verification Discipline
  The professional practice of checking every Copilot output — formulas, charts, Pivot Tables, analytical summaries — against known values, source documents, or approved budget and contract records before relying on it for decision-making or public reporting.

Rate and Fee Schedule Rule
  The City of Bowie discipline that Copilot may perform arithmetic on rates but must never be asked to supply them. Pay rates, contractor rates, fee schedules, and grant award amounts come from the adopted budget, signed contract, or approved fee schedule — never from a generated answer.

Copilot Cowork
  Microsoft 365 Copilot's delegated-work experience, generally available June 16, 2026. Executes long-running, multi-step, multi-file tasks in a hosted cloud environment and returns finished artifacts — including Excel workbooks with labeled tabs created from scratch — while your device is off.

Capital Improvement Project (CIP)
  A major infrastructure or facility investment funded through the city's capital budget. Tracked in Excel by project, phase, funding source, and expenditure rate — a primary subject of city budget analysis.

Grant Expenditure Rate
  The percentage of a grant award that has been spent, tracked against the grant period and reporting deadlines. A low expenditure rate near a deadline is a risk indicator requiring human investigation.

Overtime Hours
  Staff hours worked beyond the regular scheduled threshold, billed at a premium rate. Tracked as a share of total hours to evaluate staffing efficiency and manage labor cost within department budgets.

Fiscal Year
  The City of Bowie's budget year, running July 1 through June 30. Must be clearly labeled in all Excel column headers to prevent Copilot from confusing fiscal-year and calendar-year aggregations.

Budget Variance
  The difference between a budgeted amount and the actual expenditure, expressed as a dollar amount or percentage. A positive variance means spending exceeded budget; a negative variance means spending came in under budget.

Post-Project Reconciliation
  The process of closing a capital or operating project financially — matching all expenditures, contractor invoices, and grant reimbursements to produce a final cost summary and confirm compliance with funding terms.

Fee Collection Rate
  The percentage of projected fee revenue that is actually collected in a given period. A core fiscal performance metric tracked by the Finance department.

Constituent Services
  The City of Bowie department responsible for responding to resident inquiries, service requests, and concerns — a source of resident engagement data that can be tracked and analyzed in Excel.

Microsoft 365 Roadmap
  Microsoft's official public tracker of Microsoft 365 feature releases — showing what is available, what is in preview, and what is planned. The authoritative source for feature status questions.

OneDrive for Business
  Microsoft's cloud file storage service integrated with Microsoft 365 — the required storage location (along with SharePoint) for Excel files to be accessible by Copilot in Excel.

Hallucination (in Excel context)
  The risk that Copilot generates a formula, a rate, or an analytical conclusion that appears correct but is wrong — a known AI limitation that makes the verification discipline mandatory rather than optional.
```
