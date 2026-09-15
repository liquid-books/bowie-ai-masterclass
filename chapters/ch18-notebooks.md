---
title: "Chapter 18: Copilot Notebooks — Your Persistent AI Workspace"
subtitle: "The Document Collection That Never Forgets"
short_title: "Copilot Notebooks"
description: "Learn how Microsoft Copilot Notebooks creates a persistent, document-grounded AI workspace that stays context-aware across sessions — and how City of Bowie employees use it to analyze complex multi-document projects without losing their place."
label: ch-18-notebooks
tags: [Copilot Notebooks, BizChat, persistent workspace, document grounding, multi-document analysis, City of Bowie, Accountability, Responsiveness, Stewardship, Pride, budget analysis, grant comparison, context persistence, M365 Copilot]
---

```{admonition} Download this Chapter as PDF
:class: tip

```

:::{figure} ../images/ch18-notebooks-infographic.png
:label: fig-ch18-hero
:alt: Illustrated hub-and-spoke infographic with a blue notebook icon at the center labeled "Copilot Notebooks" and five spokes radiating outward to icons representing Multiple Files, Persistent Context, Multi-Turn Analysis, Returnable Workspace, and Grounded Answers. Clean flat design with City of Bowie blue and green color scheme, textbook illustration quality. No people, no text garbling, no screens with readable content.
:width: 80%
:align: center

Copilot Notebooks sits at the center of five capabilities that standard chat lacks: pinned file collections, persistent context, multi-turn analysis chains, a returnable workspace, and answers grounded in your actual documents.
:::

> *"The most expensive thing in knowledge work is re-establishing context you already had."*
> — Overheard at a City budget debrief

---

There is a moment familiar to anyone who has managed a complex multi-document analysis in local government. You open a new Copilot chat. You upload the capital project status report. You ask your first question, get a useful answer, and feel productive. Then you need the current budget variance. You upload that too. Then the grant application documents. Then a comparison to last fiscal year's expenditures. By the fourth document and the seventh question, you realize you are not having a conversation. You are repeatedly re-explaining the same situation to an assistant who forgets everything the moment you close the tab.

That is not a workflow. That is a tax on your time.

Marcus, a City of Bowie Finance analyst, ran into this wall three times in a single week. He was building a budget variance analysis for three concurrent capital improvement projects — a park renovation, a road resurfacing program, and a stormwater infrastructure upgrade. Each project had its own budget report, contractor status summary, and expenditure log. Every time he opened a new Copilot chat, he re-uploaded files, re-explained context, and re-issued prompts he had already written. When he finally got the cross-project comparison he needed, he had no record of how he got there.

Copilot Notebooks exists precisely to solve that problem.

---

## 1. What Notebooks Is (and What It Isn't)

Copilot Notebooks is a feature inside Microsoft 365 Copilot — accessible at **microsoft365.com/copilot** via the Notebooks link in the left navigation rail, or directly at **copilot.microsoft.com** under the Notebooks tab. It looks simple: give it a name, add a description, attach files, start a conversation. What it delivers is something that standard Copilot chat cannot: a persistent workspace where your documents stay pinned and your conversation keeps building.

That single distinction — persistence — changes what you can do.

:::{figure} ../images/ch18-vs-copilot-chat.png
:label: fig-ch18-vs-chat
:alt: Side-by-side comparison diagram with two columns. Left column labeled "Standard Copilot Chat" shows icons for a single chat bubble, files that disappear after each session, and a reset arrow. Right column labeled "Copilot Notebooks" shows icons for a pinned file stack, a persistent conversation thread, and a return arrow. City of Bowie blue and green color scheme, clean flat design, no text garbling.
:width: 80%
:align: center

Standard Copilot Chat is stateless — each session starts fresh. Copilot Notebooks maintains document context and conversation history across every return visit.
:::

**What Notebooks is:**

- A named, saveable AI workspace you create once and return to repeatedly
- A place to pin up to approximately 20 files (Word documents, PDFs, Excel spreadsheets, PowerPoint presentations) as permanent grounding sources
- A multi-turn conversation environment where every question you ask has access to all pinned files simultaneously
- A context-preserving record — Copilot can reference earlier turns in the same notebook when answering new questions

**What Notebooks is not:**

- It is not **Copilot Chat** (the standard interface). Chat is stateless. Each session is isolated. You re-attach files, re-establish context, and lose the conversational thread when you close the window.
- It is not **Microsoft OneNote** (covered in Chapter 10). OneNote is a note-taking and organization application. Copilot Notebooks is an AI analysis workspace. OneNote stores your notes; Notebooks analyzes your documents. They share a name, not a purpose.
- It is not **Cowork** (covered in Chapters 14–17). Cowork agents execute tasks autonomously — they draft, research, send, and deliver. Notebooks is a workspace for your own analysis sessions. You are still doing the intellectual work; Notebooks just ensures your documents and conversation stay organized and available.
- It is not a document storage system. The files you add to a Notebook are grounding sources for Copilot, not a replacement for SharePoint, Teams, or OneDrive.

The simplest mental model: **a Notebook is a project folder with an AI analyst permanently inside it.**

---

## 2. The Persistent Workspace Advantage

Consider what you actually lose when context resets.

Every time Marcus re-uploaded his budget variance report to a new Copilot chat, he was not just uploading a file. He was also spending tokens re-establishing the frame: what project this was, what the variance categories were, which line items were over budget and why, what cross-project comparison he had been building toward. He had built that frame over six conversation turns in the previous session. It was gone.

Context is expensive to rebuild. It takes time. It takes accurate recall of what you had already established. And it introduces error — when you summarize a prior session from memory rather than building on it directly, you sometimes omit the nuance that made the prior analysis useful.

Notebooks eliminates that tax. When you return to a Notebook you created last Tuesday, Copilot has access to exactly what it had last Tuesday: the same files, the same conversation history, the same analytical frame. You pick up where you left off. You ask the next question — not the same questions again.

For City of Bowie staff, this matters at a specific scale. A capital project budget review involves project status reports, contractor invoices, grant reimbursement records, prior-year comparison data, and sometimes Council-approved budget amendments. That is not two files. That is a document ecosystem. Standard Copilot chat handles one or two files adequately. Notebooks handles the ecosystem.

The compounding effect is also significant. Because the conversation persists, your analysis gets more precise over time. Your third session in a Notebook builds on your second, which built on your first. You develop a shared shorthand with the workspace — "the variance we identified in Session 1" becomes a reference point, not a re-explanation.

---

## 3. How to Create a Notebook

Creating a Notebook takes under two minutes. The friction is low by design — Microsoft wants you to reach for Notebooks the way you reach for a new folder.

:::{figure} ../images/ch18-create-notebook-flow.png
:label: fig-ch18-create-flow
:alt: Illustrated step-by-step flowchart showing four sequential steps: Step 1 shows a browser navigating to copilot.microsoft.com with a "Notebooks" tab highlighted in orange; Step 2 shows a "New Notebook" button being clicked; Step 3 shows a form with fields for notebook name and description; Step 4 shows a file upload panel with document icons being dragged in. City of Bowie blue and green color scheme, flat design, no readable screen text.
:width: 80%
:align: center

Creating a Notebook follows four steps: navigate, name, describe, and attach files. The entire setup takes under two minutes.
:::

**Step 1: Navigate to Notebooks**

Go to **copilot.microsoft.com** and click the **Notebooks** tab in the top navigation, or go to **microsoft365.com/copilot** and select **Notebooks** from the left rail. You need an active Microsoft 365 Copilot license — the same license that powers BizChat.

**Step 2: Create a new notebook**

Click **New Notebook** (or the **+** button, depending on your tenant configuration). A creation panel opens.

**Step 3: Name and describe your notebook**

Give it a specific name. Not "Analysis" — that ages badly when you have twelve notebooks. Use names like:
- *FY2026 CIP — Parks Renovation Budget Review*
- *Stormwater Infrastructure — Grant Application Comparison Q2 2026*
- *Comprehensive Plan Update — Community Input Analysis*

Add a description that captures the purpose and time scope. The description helps future-you understand the notebook's context before re-reading every file.

**Step 4: Add your files**

Click **Add files** and upload the documents you want as grounding sources. Files upload from your device, OneDrive, or SharePoint. Supported formats include Word (.docx), PDF, Excel (.xlsx), and PowerPoint (.pptx).

**Step 5: Start your first conversation**

Type your opening prompt in the chat input. Copilot will analyze across all pinned files simultaneously. The conversation begins.

Your Notebook is saved automatically. It appears in your Notebooks list when you return. The files stay attached. The conversation stays intact.

---

## 4. Choosing Your Files Wisely

The files you add to a Notebook determine the quality of every answer Copilot gives. This is not a metaphor. Copilot cannot analyze what is not in the Notebook. Garbage in, garbage out — but the more nuanced version is: incomplete context in, incomplete analysis out.

:::{figure} ../images/ch18-file-selection-strategy.png
:label: fig-ch18-file-selection
:alt: Illustrated decision framework diagram showing a central question "Which files belong in this notebook?" with branching paths. Left branch labeled "Include" with green checkmarks next to icons for source documents, reference contracts, historical reports. Right branch labeled "Exclude" with red X marks next to icons for duplicates, low-quality scans, unrelated files. Small callout boxes note the 20-file limit and "Quality over Quantity" principle. City of Bowie blue and green, flat design.
:width: 80%
:align: center

File selection strategy: include the documents that directly ground your analysis; exclude duplicates, poor-quality scans, and files unrelated to the notebook's specific purpose.
:::

**The ~20-file limit**

Copilot Notebooks supports approximately 20 files per notebook. The exact limit can vary based on file size and your tenant configuration, but treat 20 as the practical ceiling. This is not a bug — it is a design constraint that encourages focus. A Notebook with 20 tightly relevant files outperforms a Notebook with 18 relevant files and two tangential ones.

**File type considerations**

- **Word documents (.docx):** Copilot reads these well. Text is extracted cleanly, structure is preserved.
- **PDFs:** Generally reliable, but PDFs generated from scanned documents (image-based, not text-based) may not extract accurately. If your older municipal records were scanned rather than generated digitally, verify answers against the source.
- **Excel spreadsheets (.xlsx):** Copilot reads tabular data but performs better with well-labeled columns and consistent formatting. A spreadsheet with merged cells, hidden rows, or multiple calculation tabs may produce unreliable extractions.
- **PowerPoint (.pptx):** Text in standard slide layouts extracts well. Text embedded in images, SmartArt, or complex graphics may not be read.

**Quality over quantity**

The instinct when building a Notebook is to add everything that might be relevant. Resist it. Every file you add is part of the context Copilot has to navigate. A Notebook with 6 precisely relevant files yields sharper, more grounded answers than one with 20 files where 14 are marginally related.

Before adding a file, ask: *Does this directly ground the question I am trying to answer?* If the answer is maybe, leave it out until you need it.

**Name your files before uploading**

A file named `FinalFinal_v3_USE THIS ONE.xlsx` tells Copilot nothing useful. A file named `FY2026-ParksRenovation-BudgetVariance-March.xlsx` tells Copilot the fiscal year, the project, the document type, and the period. Copilot uses file names as metadata when citing sources. Descriptive names produce cleaner citations and help you audit answers.

:::{admonition} Stewardship Check — Excellence in Information Management
:class: important

A well-organized Notebook with clearly labeled source documents outperforms a cluttered one. Rename your files descriptively before uploading — not just for your own clarity, but because Copilot uses file names when citing sources and constructing answers. A file called `FY26-CIP-ParkRenovation-StatusRpt.xlsx` produces a more traceable answer than one called `Report(2).xlsx`. Invest two minutes in naming. It pays back on every question you ask.
:::

---

## 5. The Art of Notebook Prompting

Prompting inside a Notebook is different from prompting in standard Copilot Chat. The difference is not in syntax — it is in strategy. You have more information available, more conversation history to reference, and a context that accumulates across sessions. Use all of it.

:::{figure} ../images/ch18-prompt-anatomy.png
:label: fig-ch18-prompt-anatomy
:alt: Illustrated diagram showing a single prompt broken into labeled components. A text bubble contains a sample prompt, with colored annotation arrows pointing to different sections: "Scope" (which documents to focus on), "Task" (what to do), "Format" (how to structure output), and "Build-on" (reference to a prior turn). City of Bowie blue and green, flat infographic style, no readable text in the sample prompt.
:width: 80%
:align: center

A well-constructed Notebook prompt identifies scope, task, desired format, and builds on prior conversation turns rather than starting from scratch.
:::

**Open with scope**

In standard chat, you establish scope by uploading a file. In a Notebook, files are already pinned — but Copilot still benefits from knowing which subset you want to focus on. Open with a scope statement:

*"Using only the budget reports for the Parks renovation and the road resurfacing projects (not the stormwater project), identify the top three cost overrun categories."*

That constraint helps Copilot deliver a precise answer rather than averaging across all three projects when you only want two.

**Build on prior turns explicitly**

Because your conversation persists, you can — and should — reference earlier turns. Copilot can use them as context. Examples:

- *"In our last session, you identified contractor labor costs as the primary budget variance driver. Looking at the grant reimbursement records now, are any of those cost overruns eligible for grant reimbursement?"*
- *"Earlier you gave me the top three grant applications by total funding requested. Now rank those same three by matching fund requirements."*

These prompts work because the earlier context is still in the conversation. You are not re-explaining — you are building.

**Specify output format for every analytical ask**

Copilot can produce answers in paragraph form, bullet lists, tables, or structured reports. In a Notebook context — where you are likely doing serious analysis — be explicit:

- *"Summarize in a table: columns for project name, budget variance amount, variance percentage, primary cause."*
- *"Give me a two-paragraph executive summary I can paste into the Council briefing document."*
- *"List the five most significant discrepancies as numbered bullet points, citing which document each comes from."*

**Ask Copilot to cite its sources**

In multi-document Notebooks, source attribution matters. You need to know whether that budget figure came from the Parks renovation report or the road resurfacing report. Add a citation instruction to your prompts:

*"For each finding, cite the document and section it comes from."*

Copilot will reference the file name in its answer. You can then spot-check against the source.

**Use progressive refinement**

Do not try to get the complete answer in a single prompt. Start broad, then narrow. Session one: establish the landscape. Session two: dig into anomalies. Session three: build the output document. This mirrors how a skilled analyst actually works — and it matches how Notebooks accumulates value over time.

---

## 6. Ten City of Bowie Notebook Use Cases

:::{figure} ../images/ch18-ges-use-case-grid.png
:label: fig-ch18-use-case-grid
:alt: Illustrated 2x5 grid of icon cards, each representing one of ten City of Bowie use cases for Copilot Notebooks. Each card has a simple icon (budget chart, road blueprint, safety shield, grant document, onboarding checklist, etc.) and a number 1-10. City of Bowie blue and green color scheme, flat design, consistent card layout, no readable text on cards.
:width: 80%
:align: center

Ten proven City of Bowie Notebook configurations — each represents a real workflow where persistence and multi-document grounding deliver analysis that standard chat cannot.
:::

### Use Case 1: Capital Project Budget Review

**The situation:** You are tracking three concurrent capital improvement projects. Each has a budget status report, a contractor progress summary, and an expenditure log.

**What to pin:** Budget status report (Project A), Budget status report (Project B), Budget status report (Project C), contractor summaries for all three, expenditure logs for all three. That is nine files — well within the limit.

**Opening prompt:** *"Across all three projects, identify the top five cost overrun categories by total dollar impact. Cite which project(s) each category appears in."*

**Follow-up turns:**
- *"Which project has the highest contractor labor overrun as a percentage of the approved budget?"*
- *"Cross-reference the labor overruns with the expenditure logs. Are any overruns tied to scope changes or approved amendments?"*
- *"Draft a one-page executive summary of budget variance findings across all three projects."*

**The payoff:** A complete cross-project financial analysis that would take a skilled analyst half a day to assemble manually — built in a single Notebook session, with citations you can audit before briefing the City Manager.

### Use Case 2: Grant Application Comparison

**The situation:** You are evaluating four grant opportunities for a community parks improvement initiative. Each grant program sent a detailed application guide covering eligibility, matching requirements, allowable costs, and reporting obligations.

**What to pin:** The four grant application guides. That is it. Keep the Notebook focused.

**Opening prompt:** *"Compare all four grants on matching fund requirements: percentage match, allowable match sources, and timeline for match documentation. Present as a table."*

**Follow-up turns:**
- *"Now compare allowable costs: which grants cover design and engineering? Which cover construction only?"*
- *"Which grants have the most restrictive reporting requirements?"*
- *"Based on everything we have analyzed, which two grants best match a $500,000 neighborhood park renovation project with a 20% local match available?"*

:::{figure} ../images/ch18-rfp-comparison.png
:label: fig-ch18-rfp
:alt: Illustrated infographic showing four grant document icons feeding into a central "Notebooks" analysis hub, with output arrows pointing to comparison categories: Match Requirements, Allowable Costs, Reporting, Eligibility. Clean hub-and-spoke diagram in City of Bowie blue and green. Flat design, no readable text, no screens.
:width: 80%
:align: center

The grant application comparison Notebook pins all four program guides and uses progressive prompting to build a structured comparison — matching requirements first, then allowable costs, then reporting obligations, then a synthesis recommendation.
:::

**The payoff:** A structured grant comparison that consolidates hundreds of pages of program documents into actionable decision criteria — ready to brief the department director.

### Use Case 3: Comprehensive Plan Update — Community Input Analysis

**The situation:** The City is updating its Comprehensive Plan. Your team collected written comments from three community engagement sessions. You need to synthesize themes before the Planning Commission hearing.

**What to pin:** Transcript or summary from Community Session 1, Session 2, Session 3, plus the existing Comprehensive Plan goals chapter and the Planning Commission's prior direction memo.

**How this Notebook is different:** This is a qualitative synthesis Notebook — not a financial analysis. The team uses it to identify recurring resident priorities, map them against existing Plan goals, and identify gaps.

**Sample prompts:**
- *"What are the three most frequently mentioned resident priorities across all three community sessions?"*
- *"Which existing Comprehensive Plan goals have the most community support based on the session comments?"*
- *"Identify any resident concerns raised in the sessions that are not addressed in the current Plan goals."*

**The payoff:** A community input synthesis that respects the full breadth of resident voices — not just the loudest room.

### Use Case 4: Resident Dispute or Complaint Resolution

**The situation:** A resident is disputing a $2,400 Public Works service charge. They claim the work was performed without their authorization. You need to reconstruct the full picture quickly.

**What to pin:** The resident's original service request, all email and written communications with the resident (exported to Word or PDF), the applicable fee schedule, your internal work order notes, and the final invoice.

**Opening prompt:** *"The resident is disputing the service charge on the final invoice. Based on the service request and fee schedule, calculate what their charge should have been. Then identify any line items on the final invoice that are not supported by the original service request."*

**Follow-up turns:**
- *"Review the communications. Did the resident authorize any additional work verbally or in writing?"*
- *"Draft a dispute response letter that acknowledges their concern, presents the documented justification for each charge, and references the specific communications that support the City's position."*

**The payoff:** A dispute response built on the actual documentary record — not from memory or summary — reducing both resident frustration and the City's liability exposure.

### Use Case 5: Annual Department Performance Review

**The situation:** Parks & Recreation is preparing for the annual City Manager performance review. You need to present a comprehensive summary of program outcomes, budget performance, and resident satisfaction for the fiscal year.

**What to pin:** Quarterly program reports (all four quarters), the annual budget variance summary, and the resident satisfaction survey results.

**Opening prompt:** *"Across all four quarters, what was the average program participation rate, the budget adherence rate, and the number of new programs launched?"*

**Follow-up turns:**
- *"Which quarter had the most resident complaints? What were the primary complaint categories?"*
- *"Identify three areas where department performance improved year-over-year and two areas where we fell short of targets."*
- *"Draft the performance summary section of the annual department review presentation — use the data we have discussed, in a professional tone appropriate for a City Manager briefing."*

**The payoff:** An annual review grounded in a full year of actual performance data, not the two programs you remember most clearly.

### Use Case 6: Ordinance or Policy Development

**The situation:** The City is developing a new short-term rental ordinance. You have the draft ordinance, written public comments, legal counsel's review memo, and adopted ordinances from three comparable Maryland jurisdictions.

**What to pin:** Draft ordinance, public comment summary, legal review memo, comparable ordinances (three jurisdictions).

**Opening prompt:** *"Based on the public comments and legal review, what are the three most significant issues raised that may require revisions to the draft ordinance? Cite specific sections."*

**Follow-up turns:**
- *"How do the three comparable jurisdictions handle the enforcement mechanism? Summarize each in one paragraph."*
- *"Generate five options for addressing the most-cited public concern, with a brief note on legal risk for each."*

**The payoff:** Policy development grounded in public input, legal analysis, and peer jurisdiction research — synthesized in one workspace rather than across a dozen separate documents.

### Use Case 7: Safety Incident Pattern Analysis

**The situation:** You are preparing the semi-annual safety review for Public Works and need to identify patterns across incident reports from the past six months.

**What to pin:** All incident reports from the review period (or as many as fit within the file limit).

**Opening prompt:** *"Catalog all incidents by type: near-miss, first aid, recordable injury, and property damage. Present as a table with department, incident type, date, and brief description."*

**Follow-up turns:**
- *"Are any incident types recurring across multiple crews or work units? Identify patterns."*
- *"Which type of work activity — road work, facility maintenance, parks operations, or utilities — accounts for the most incidents?"*
- *"Draft three specific corrective action recommendations based on the patterns you have identified."*

:::{admonition} Accountability Check
:class: important

Copilot Notebooks retrieves its answers from the files you add. But it can miss content buried in complex tables, nested columns, or deep within large PDFs — particularly if those documents were scanned rather than digitally generated. For safety incident analysis, this is not a theoretical risk. If an incident was documented in a table with merged cells on page 47 of a 90-page report, Copilot may not surface it. Always verify critical safety findings — especially counts, severity classifications, and corrective action statuses — by checking the source document directly.
:::

**The payoff:** A pattern analysis that would require manually reading and cross-referencing six months of reports now takes one Notebook session.

### Use Case 8: Annual Budget Development

**The situation:** You are assembling the Finance department's analysis of department budget requests for the upcoming fiscal year. You have eight department submissions to review against prior-year actuals and the City Manager's policy guidance.

**What to pin:** Budget request from each department (up to eight), the prior-year actuals summary, and the City Manager's budget policy guidance memo.

**Opening prompt:** *"For each department, calculate the percentage increase requested over prior-year appropriations. Rank departments from highest to lowest increase."*

**Follow-up turns:**
- *"Which departments' requests align with the City Manager's stated priority areas? Which are outside those priorities?"*
- *"Which cost category — personnel, capital outlay, or operating expenses — accounts for the largest total increase across all departments?"*
- *"Draft a one-page budget analysis summary memo I can include in the City Manager's budget kickoff briefing."*

**The payoff:** A cross-department budget picture assembled from individual submissions — without a single manual spreadsheet calculation.

### Use Case 9: New Employee Onboarding Reference

**The situation:** A new Constituent Services coordinator joins your team. They need to understand City service delivery standards, escalation protocols, the resident request management system workflow, and departmental contacts.

**What to pin:** Standard onboarding guide, Constituent Services SOP, departmental directory, escalation protocol document, and the City's service delivery standards policy.

**How this Notebook is different:** This Notebook belongs to the new employee. They use it as a personal reference — asking questions as they arise rather than scheduling time with their supervisor for every procedural question.

**Sample prompts:**
- *"What is the process for escalating a resident request that has not been resolved within the standard response window?"*
- *"Who do I contact in Public Works if a resident reports a streetlight outage that hasn't been addressed?"*
- *"What is the City's policy on response time for constituent email inquiries?"*

**The payoff:** A new employee who can self-serve answers to procedural questions in their first 90 days — and a supervisor who spends less time answering the same questions repeatedly.

### Use Case 10: Contract Negotiation Preparation

**The situation:** You are entering renewal negotiations with a key contractor for parks maintenance services. You have the current contract, two years of performance reports, your internal cost benchmarks, and the most recent invoice history.

**What to pin:** Current maintenance contract, performance report (Year 1), performance report (Year 2), cost benchmark analysis, key invoice history (exported to Word).

**Opening prompt:** *"Review the current contract. What are the three terms most favorable to the contractor that we should look to renegotiate in the City's favor?"*

**Follow-up turns:**
- *"Based on the performance reports, what evidence do we have of service deficiencies that support a request for rate concessions or service credits?"*
- *"What is our current contracted rate for turf maintenance compared to the benchmark analysis?"*
- *"Draft a negotiation preparation brief: our top five asks, the evidence supporting each, and our walk-away position on each."*

**The payoff:** You walk into the negotiation with a brief built from the actual documentary record — not from what you remember from the last contract cycle.

---

## 7. Notebook Discipline

A Notebook is only as useful as its focus. This is the lesson that most users learn after creating their first five Notebooks.

:::{figure} ../images/ch18-notebook-discipline.png
:label: fig-ch18-discipline
:alt: Illustrated split diagram showing two contrasting examples. Left side labeled "Focused Notebook" shows a neatly organized notebook icon with a clear label and a small stack of relevant files. Right side labeled "Sprawling Notebook" shows a cluttered notebook icon with many overlapping file icons and a confused question mark. City of Bowie blue and green, flat design, no readable text.
:width: 80%
:align: center

Focused Notebooks — one project, one purpose, clearly named — outperform sprawling ones. When a notebook starts covering multiple projects, create a new one.
:::

**Naming conventions that hold up over time**

Use this structure: **[Project/Program Name] — [Purpose] — [Fiscal Year or Date]**

Examples:
- *FY2026 CIP — Parks Renovation Budget Review — Q2*
- *Comprehensive Plan Update — Community Input Synthesis — Spring 2026*
- *Safety Incidents — Pattern Review — H1 FY2026*
- *Parks Maintenance Contract — Renewal Negotiation Prep — FY2027*

Avoid generic names. The name you give a Notebook in the moment of creation is the name you will be searching for in six months when you need to find it.

**One purpose per Notebook**

The temptation is to repurpose an existing Notebook for a related project — to add this year's parks renovation files to last year's parks renovation Notebook because it feels like the same project. Do not. Each annual cycle is a new project with new files and new questions. Create a new Notebook. The old one becomes an archive.

**Know when to start fresh**

If you find yourself adding files that are only partially relevant, removing old files to make room for new ones, or losing track of what questions you have already asked, those are signals to start a new Notebook. Fresh start, focused purpose, clean files.

**Archive, do not delete**

Your completed Notebooks are a record of analysis. An investigation you completed in January may be relevant to a dispute that surfaces in August — or to a MPIA request that arrives in November. Keep completed Notebooks. They do not cost you storage — they cost nothing to maintain, and they may be the institutional memory that resolves a future problem.

:::{admonition} Responsiveness Check
:class: important

The conversation history in a Notebook gives Copilot useful context — but very long notebooks can cause early context to be deprioritized. If your Notebook has accumulated dozens of conversation turns across months of use, Copilot may weight recent exchanges more heavily than older ones. This is not failure; it reflects how large language models manage context windows. The practical implication: if you start a genuinely new project — even one related to a prior project — create a new Notebook rather than extending an old one. A fresh Notebook with the right files will outperform a sprawling one — and will respond more accurately to your current questions.
:::

---

## 8. Limits and Honest Gotchas

Notebooks is genuinely useful. It is also genuinely limited. Both of these things are true, and understanding the limits prevents the frustration of expecting something the tool cannot deliver.

:::{figure} ../images/ch18-limits-honest.png
:label: fig-ch18-limits
:alt: Illustrated warning-sign style infographic listing four limitations of Copilot Notebooks as icon-and-label pairs: a clock icon for "Stale Files," a file-size gauge for "Size Limits," a table grid with an X for "Complex Tables May Misread," and a share icon with a lock for "Shared Notebooks Share Everything." City of Bowie blue and green color scheme, flat design, no garbled text.
:width: 80%
:align: center

Four honest limitations of Copilot Notebooks: files can become stale, file size affects extraction quality, complex tables may not parse correctly, and shared notebooks expose all content to all collaborators.
:::

**File size and extraction quality**

There is no published single-file size limit, but very large files — particularly large PDFs with complex layouts — may not extract completely. If a 200-page contract only surfaces results from the first 80 pages, that is likely an extraction limit, not a Copilot error. Mitigation: split large documents into logical sections before uploading, or extract the most relevant pages into a focused document.

**Complex tables and structured data**

Copilot handles narrative text better than it handles complex structured data. A budget spreadsheet with 400 line items in a tightly formatted Excel sheet may yield less reliable extraction than a Word document describing the same information in prose. If your analysis depends on exact figures from complex tables, verify Copilot's extractions against the source.

**Real-time data is not available**

A Notebook is grounded in the files you have added. It has no access to live systems — not your permitting platform, your finance system, or your work order management tool. If you need current project status, live budget balances, or real-time service request counts, Notebooks is not the tool. It analyzes documents you have exported or downloaded. Think of it as an analyst who has read your printed reports — not one who is logged into your systems.

**Copilot can be confidently wrong**

This is the consistent limitation across all Copilot surfaces, and Notebooks is not exempt. Copilot will sometimes synthesize an answer that is plausible but incorrect — combining figures from different documents, misciting a source, or generating a number that was nowhere in the files. The frequency is lower in a well-structured Notebook with clean files than in open-ended chat, but it is not zero. Treat Copilot's output as a first draft that requires verification for any figures that matter — particularly before presenting to elected officials or including in official reports.

:::{admonition} Warning — Stale Files Produce Stale Analysis
:class: warning

If you add a Q1 budget report to a Notebook and then work through the end of the fiscal year, that Notebook is still grounded in Q1 data. Copilot does not know the file is outdated — it will answer from what is there. When a new reporting period closes, update your Notebook: remove the outdated file and add the current one. Treat your Notebook's file collection the same way you would treat a printed report package handed to a staff analyst — if the report is six months old, the analysis will be six months stale.
:::

:::{admonition} Warning — Shared Notebooks Share Everything
:class: warning

If you share a Copilot Notebook with a colleague, they see everything: every file you have added and every conversation turn in the history. This is not like sharing a folder where you control which files they can access. It is full notebook access. Before sharing, review the complete conversation history and the complete file list. If any file contains confidential personnel information, pre-decisional budget materials, attorney-client communications, or information that would not be appropriate to share with that colleague directly, either remove it before sharing or create a new, sharing-appropriate Notebook with only the relevant content.
:::

:::{admonition} Stewardship Check — Data Responsibility
:class: important

City data in a Copilot Notebook stays within the City of Bowie Microsoft 365 tenant — it does not leave the City's environment. That is a genuine protection and a meaningful difference from uploading files to consumer AI tools. However, tenant-level protection is not the only data risk. Think carefully before adding confidential personnel files, pre-decisional budget materials, attorney-client communications, or MPIA-exempt records to a Notebook you intend to share with team members who are not authorized to see that information. Access controls in Notebooks are coarse — share a Notebook, and you share all of it. Apply the same judgment you would use before forwarding an email chain containing sensitive government records.
:::

---

## 9. Try This — Build Your First City of Bowie Notebook

This exercise builds a working Notebook from real (or realistic) City documents. It takes approximately 30 minutes.

**Setup (10 minutes):**

1. Identify one project or program where you have at least three documents: a status or progress report, a financial summary or budget variance, and either a resident communication log or a contractor correspondence export.
2. If you do not have real documents available, use the sample documents provided in the course resource portal: *Sample-ProjectStatusReport.pdf*, *Sample-BudgetVariance.xlsx*, and *Sample-ResidentCorrespondence.docx*.
3. Rename the files descriptively before uploading (e.g., *FY26-ParksRenovation-StatusReport-March.pdf*).

**Build the Notebook (5 minutes):**

4. Go to copilot.microsoft.com → Notebooks → New Notebook.
5. Name it: *[Your Project Name] — Practice Analysis — [Today's Date]*
6. Add a description: *Practice Notebook for Chapter 18 exercise — project analysis with three documents.*
7. Upload your three files.

**First conversation (15 minutes):**

8. Start with a scope-setting prompt: *"I have attached three documents from [project name]. The status report covers project progress and milestones. The budget variance covers spending against the approved appropriation. The correspondence log covers resident and contractor communications. Before I ask specific questions, give me a brief summary of each document's key contents."*
9. After Copilot summarizes, ask a cross-document question: *"Based on the budget variance and the correspondence log, is there a connection between our largest cost overruns and the nature of the resident or contractor communications?"*
10. Ask for a specific output: *"Draft three bullet points summarizing the financial and operational risk profile of this project, in language I could include in a department director briefing."*

**Close and return (the real test):**

11. Close the Notebook entirely. Log out if you want.
12. Return tomorrow (or in an hour). Open the Notebook. Confirm that your files are still attached and your conversation is still visible.
13. Add one follow-up question: *"In our last session, we identified [topic]. What additional information from the attached documents would strengthen that analysis?"*

You have now experienced the core Notebooks value proposition firsthand.

---

## 10. Productive Struggle Problem

This challenge is designed for teams rather than individuals. It requires judgment as well as Notebooks skill.

**The scenario:**

The City of Bowie is conducting a comprehensive post-project analysis of a major multi-year capital improvement project — the renovation of a community center and adjacent park. Five stakeholders have contributed documents:

- The Public Works team submitted a project timeline variance report
- The Parks & Recreation team submitted a service quality assessment and resident feedback log
- The Finance team submitted a project P&L with a $180,000 unfavorable contractor labor variance
- The project manager submitted a contractor performance evaluation
- The Constituent Services team submitted resident survey results from post-project outreach, which partially contradict the Parks & Recreation team's internal quality assessment

**The challenge:**

1. Design the Notebook: which files do you include, in what order, and how do you name them?
2. Write a five-prompt sequence that moves from document orientation → cross-document pattern identification → contradiction analysis → root cause hypothesis → executive brief draft.
3. The resident survey and the Parks & Recreation internal assessment disagree on satisfaction ratings in two program categories. How do you prompt Copilot to surface and analyze that contradiction — rather than averaging it away?
4. The $180,000 contractor labor variance appears in the Finance P&L but is not discussed in any other document. What are three possible explanations, and how would you construct Notebook prompts to test each hypothesis against the available documents?
5. After completing the analysis, write the notebook naming convention and file list you would archive — and explain what you would include in the Notebook description for the next staff member who needs to reference this analysis in a future budget cycle, grant application, or audit inquiry.

There is no single correct answer. The value is in the reasoning about document selection, prompt sequencing, and how to handle contradictions in source material.

---

## Glossary

**BizChat**
Microsoft's name for the web-based Microsoft 365 Copilot interface, accessible at microsoft365.com/copilot or copilot.microsoft.com. Notebooks is a feature within BizChat.

**Context window**
The amount of information (text, conversation history, document content) that an AI model can hold in active memory for a given interaction. Copilot Notebooks manages context across a conversation; very long conversations may cause early content to be deprioritized.

**Document grounding**
The practice of providing specific source documents to an AI model so that its answers are based on those documents rather than its general training data. Notebooks is a document-grounded AI workspace.

**Extraction**
The process by which Copilot reads and parses the content of an uploaded file. Extraction quality varies by file type and document complexity; clean, text-based documents extract more reliably than scanned PDFs or complex spreadsheets.

**File limit**
The maximum number of files that can be pinned to a single Copilot Notebook at one time — approximately 20, depending on file size and tenant configuration.

**Grounding source**
A document added to a Notebook that Copilot uses as the basis for its answers. Copilot answers are only as accurate as the grounding sources are complete and current.

**M365 Copilot**
Microsoft 365 Copilot — the enterprise AI license that provides access to Copilot across Microsoft 365 applications (Teams, Outlook, Word, Excel, PowerPoint) and BizChat/Notebooks.

**Multi-turn conversation**
An AI conversation in which each exchange builds on the prior ones, allowing for progressive refinement, follow-up questions, and reference to earlier analysis. Notebooks preserves multi-turn conversations across sessions.

**Persistent workspace**
A workspace that retains its contents — files, conversation history, settings — between sessions. Copilot Notebooks is a persistent workspace; standard Copilot Chat is not.

**Prompt sequencing**
A prompting strategy in which a series of prompts moves progressively from orientation → analysis → synthesis → output, rather than asking for everything in a single prompt.

**Returnable workspace**
A workspace you can leave and come back to in the same state. Notebooks saves automatically and resumes exactly where you left off.

**Stale grounding**
The condition of a Notebook whose source files are outdated — for example, a Q1 budget report still pinned after Q3 has closed. Stale grounding produces stale analysis.

**Tenant**
An organization's isolated Microsoft 365 environment. Files and conversations in Copilot Notebooks remain within the City of Bowie's Microsoft 365 tenant and are not shared with Microsoft or third parties.

---

## Discussion Questions

*Use these questions to deepen team understanding. Guidelines for productive discussion follow each question.*

**1. Where does your team currently lose the most context in multi-document analysis work?**

*Discussion guideline:* Focus on specific City workflows — capital project budget reviews, grant application comparisons, policy development, annual performance reviews. Identify the exact moment where context resets or is lost. This is where a Notebook would pay back immediately.

**2. What is the difference between a Notebook and a well-organized SharePoint folder?**

*Discussion guideline:* Both organize documents. The difference is that a Notebook enables ongoing AI-assisted analysis of those documents, with persistent conversation history. A SharePoint folder stores files. A Notebook creates an analytical relationship with them.

**3. If you were building a Notebook for a project that might be subject to a Maryland MPIA request or a future audit, what files would you include — and what files would you deliberately exclude?**

*Discussion guideline:* This question surfaces the judgment required for responsible government use. Pre-decisional materials, attorney notes, and personnel records should generally not be in a Notebook that could be shared beyond the immediate user. Consider both MPIA implications and audit trail implications.

**4. How would you decide whether to continue an existing Notebook or start a new one for this fiscal year's version of an annual program?**

*Discussion guideline:* Prior year analysis is useful context; stale files are a liability. One practical answer: start a fresh Notebook with this year's files, but note the prior year Notebook in the description for reference.

**5. A colleague proposes using a single Notebook for all of the City's FY2026 capital projects — one workspace, all the files. What are the risks of this approach?**

*Discussion guideline:* File limit constraints, loss of focus, context confusion between projects, stale file accumulation, and the risk of a wrong cross-project citation in an analysis presented to the Council. The right answer is purpose-specific Notebooks, not one mega-Notebook.

---

## Leader's Takeaway

The value of Copilot Notebooks is not in any single answer Copilot gives you. It is in the accumulation of analytical work over time — the capital project review that gets sharper because you can build on the prior session, the grant comparison that goes three rounds deep because you do not have to re-establish context, the annual department review that actually covers the full fiscal year because all four quarters are pinned and ready.

For the City of Bowie, the operational implication is specific: the workflows that most benefit from Notebooks are those that currently suffer from context loss — where your team re-uploads files, re-explains situations, or loses analytical threads between sessions. Capital project budget reviews. Multi-grant application evaluations. Safety incident pattern analysis. Annual department performance reviews. Community input syntheses for the Comprehensive Plan. These are not hypothetical Notebooks use cases. They are the ones your team should build this week.

The discipline required is simple: one purpose per Notebook, descriptive file names, regular file updates when source documents change, and careful judgment before sharing — particularly given the City's MPIA obligations and data classification requirements. The reward is an analytical workspace that compounds in value with every session you invest in it.

The Notebook you build today for the FY2026 Parks renovation project will still be useful when a resident raises a billing dispute in November — or when Finance needs the analysis for the annual audit in February. That is not a trivial capability. That is the difference between institutional memory and institutional amnesia. For a city government that serves 70,000+ residents, the difference matters.

:::{figure} ../images/ch18-postshow-notebook.png
:label: fig-ch18-postshow
:alt: Illustrated diagram showing three project document stacks (labeled Project A, Project B, Project C) on the left, connected by arrows to a central Notebooks workspace icon, which then connects on the right to three output icons: a comparison table, an executive summary document, and a budget analysis report. City of Bowie blue and green color scheme, flat design, no readable text.
:width: 80%
:align: center

The capital project budget review Notebook consolidates reports from three projects into a single persistent workspace — enabling cross-project variance analysis, pattern identification, and output drafting in one connected session.
:::

:::{figure} ../images/ch18-notebook-discipline.png
:label: fig-ch18-discipline-2
:alt: Illustrated checklist-style infographic showing five Notebook discipline rules as numbered items with icons: 1) Descriptive name with project, purpose, and fiscal year; 2) One purpose per notebook; 3) Fewer, better files over many marginal ones; 4) Update files when source data changes; 5) Archive completed notebooks, do not delete. City of Bowie blue and green, flat design, no readable text.
:width: 80%
:align: center

Five Notebook discipline rules that determine whether your workspace compounds in value or accumulates confusion over time.
:::

---

*Chapter 18 complete. Chapter 19 covers Microsoft Copilot in Excel — turning City of Bowie budget data and program metrics into analyzed, presentation-ready intelligence without manual formula construction.*
