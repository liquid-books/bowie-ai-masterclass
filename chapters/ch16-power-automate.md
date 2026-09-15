---
title: "Chapter 16: Microsoft Power Automate — From Assistance to Automation"
subtitle: "The Third Gear: Work That Happens Without You"
short_title: "Power Automate"
description: "The capstone chapter. Copilot answers questions. Cowork completes projects. Power Automate runs processes forever — without a human in the loop — every time a trigger fires. This chapter teaches the progression from asking to delegating to automating, the critical difference between cloud flows and desktop RPA, AI Builder for document extraction, governance risks unique to automation, and ten fully worked City of Bowie scenarios from permit application intake to constituent request routing to city event setup coordination."
label: ch-16-power-automate
tags: [Power Automate, automation, RPA, desktop flows, cloud flows, AI Builder, triggers, Copilot, Cowork, City of Bowie, governance, constituent services, permit workflows, parks and recreation, city administration, T.R.U.E., flow ownership]
---

```{admonition} Download this Chapter as PDF
:class: tip

```

# Chapter 16: Microsoft Power Automate — From Assistance to Automation

:::{figure} ../images/ch16-power-automate-infographic.png
:label: fig-ch16-infographic
:alt: Illustrated explainer infographic showing the progression from Copilot (conversational, one answer) to Cowork (delegated multi-step project) to Power Automate (permanent automation, trigger fires forever). Three interconnected gears in blue and green, with City of Bowie municipal service scenarios illustrated beneath each gear.
:width: 80%
:align: center

The three gears of Microsoft 365 AI: ask, delegate, automate. Each one changes how you work — and the last one changes whether you need to be there at all.
:::

> *"The first rule of any technology used in a business is that automation applied to an efficient operation will magnify the efficiency. The second is that automation applied to an inefficient operation will magnify the inefficiency."*
> — Bill Gates

There is a moment, usually around the third or fourth time you delegate the same task to Cowork, when a different question surfaces. Not *can I delegate this?* — you have already answered that. The new question is: *why am I delegating this at all?*

It is 8:45 a.m. on a Tuesday in the Constituent Services office. A city staff member opens Copilot and types the same prompt they have typed for six months running: pull all permit applications submitted this week, check whether the applicant's contact information is complete, flag any missing fields, and route complete applications to the appropriate department for review. The staff member waits, reviews the output, approves the routing.

That staff member just spent fifteen minutes on work that is identical every week. Not *similar* — identical. Same prompt. Same libraries. Same output location. Same approval scope.

Here is the question this chapter answers: *why is a human involved at all?*

---

## 1. The Three Gears — Ask, Delegate, Automate

Every chapter before this one taught you to work with AI. Chapter 14 taught you to delegate to it. This chapter teaches you to **remove yourself entirely**.

:::{figure} ../images/ch16-three-gears.png
:label: fig-ch16-three-gears
:alt: Three interconnected gears diagram showing Copilot Chat (Ask — human in the loop every turn), Copilot Cowork (Delegate — human approves at checkpoints), and Power Automate (Automate — trigger fires, work happens, no human required until review). Visual progression from left to right showing decreasing human involvement.
:width: 80%
:align: center

The three gears of Microsoft 365 AI work. As you move from left to right, human involvement decreases — and so does the tolerance for an unverified process.
:::

**Copilot Chat** is a conversation. You ask, Copilot answers, you evaluate, you refine. You are the loop. Every step passes through you. This is the right model for drafting, ideation, and one-off questions where you want to see the answer before deciding what to do with it.

**Copilot Cowork** is delegation. You describe an outcome, Cowork plans and executes the steps, and you review and approve at checkpoints. You are no longer the loop — you are the manager. The work keeps running while your computer is off. This is the right model for multi-step, multi-file projects you need done rather than watched.

**Power Automate** is automation. You build a flow once. A trigger fires — a permit application arrives, a form is submitted, a scheduled time passes — and work happens. No prompt. No approval request. No human at all, unless you designed a checkpoint into the flow. This is the right model for the work that is *exactly the same every time*.

The decision rule is simple enough to memorize: **how much human judgment is required at execution time?**

- A lot → Chat
- Some, at checkpoints → Cowork
- None → Power Automate

:::{important}
**The insight that makes this chapter land**

Cowork is how you discover what is worth automating.

Delegate a task three or four times. Watch how it behaves. See where it succeeds reliably and where it needs correction. Notice the constraints you add because last week's run surfaced an edge case you had not thought of.

That iterated Cowork prompt — tight, tested, edge-case-aware — is your automation prototype. Power Automate is how you promote it to production so it never needs a human again.

Skip the prototype phase and you automate an unverified process. Do that and you learn the hardest lesson in this chapter the hard way.
:::

---

## 2. Why Power Automate Exists at the City of Bowie

The City of Bowie serves more than **70,000 residents** across a range of municipal services — Parks & Recreation, Public Works, Finance, Planning, HR, Public Safety Communications, and Constituent Services. The volume of repetitive administrative work involved in delivering those services consistently is significant.

Consider just one task: the weekly permit application status check. It takes a Constituent Services staff member twenty minutes to verify submission completeness, route to the correct department, and send a confirmation to the applicant. It runs every time a permit comes in. During busy permit seasons, that can be dozens of applications per week — and every check is *identical every time*.

Now multiply that across every repetitive process in city operations: resident inquiry routing, scheduled park maintenance notifications, HR onboarding document checklists, finance payment reminders, and Public Works work order follow-ups. The math is not subtle.

Power Automate exists because some work does not need a human present. Not because the human adds no value — they designed the process, they verified it, they built the constraints that make it safe to run on behalf of residents. But once that design work is done, the execution work is pure overhead that delays service to the community.

**Automation is how you convert repetitive execution into design work.** Instead of routing permit applications manually each week, you build the routing logic once, verify it carefully, set the trigger, and let it run. Your time goes to the complex cases that require judgment, not the routine ones the system can handle.

---

## 3. Cloud Flows vs. Desktop Flows — and Why RPA Exists

Power Automate offers two fundamentally different types of automation. Understanding the difference is not optional; it determines which tool you reach for and what risks you accept.

:::{figure} ../images/ch16-cloud-vs-desktop-flows.png
:label: fig-ch16-cloud-vs-desktop
:alt: Side-by-side comparison of cloud flows (left) and desktop flows (right). Cloud flows show API connections between cloud services — Outlook, SharePoint, Teams, Dataverse — running on Microsoft servers. Desktop flows show UI automation on a local Windows machine — clicking buttons, typing into fields, reading screens — running on the user's device or a hosted machine.
:width: 80%
:align: center

Cloud flows talk to APIs. Desktop flows talk to screens. The difference determines reliability, maintenance burden, and when each is the right choice.
:::

### Cloud flows

Cloud flows run on Microsoft's servers. They connect applications through **connectors** — standardized API integrations. When a permit form is submitted, a cloud flow can read it, extract values, send a confirmation email to the applicant, route the application to the correct department, and update a tracking list in SharePoint — all through documented, versioned APIs.

**Microsoft offers over 1,000 connectors.** The Microsoft 365 suite is fully covered: Outlook, SharePoint, Teams, OneDrive, Planner, Forms, Excel. So are major external services: Salesforce, ServiceNow, DocuSign, and hundreds more.

Cloud flows are **stable** because APIs are versioned and documented. When SharePoint changes its interface, the API remains backward-compatible, and your flow keeps working. Cloud flows are **scalable** because they run in Microsoft's cloud — you do not need a machine running somewhere for the flow to execute.

### Desktop flows (RPA)

Desktop flows run on a Windows machine. They automate applications by **clicking buttons, typing into fields, reading text from screens** — the same actions a human would take. This is Robotic Process Automation (RPA), and Power Automate Desktop is Microsoft's RPA tool.

**Why does RPA exist?** Because not everything has an API.

The City of Bowie, like most government organizations with years of operational history, uses applications and web portals that were built before APIs became standard. A county permitting database accessible only through a web form. A state reporting system that accepts data only through a specific browser-based interface. A legacy work order system that does not expose an API. A vendor portal that requires manual data entry through their web form.

None of these have connectors. None of them expose APIs. The only way to automate them is to simulate what a human does: open the application, navigate to the right screen, paste data, click submit.

That works. It is also **fragile**.

:::{warning}
**RPA is brittle — design for it**

Desktop flows break when the user interface changes. A button moves. A field is renamed. A dialog box appears that was not there before. The flow keeps clicking where the button *used to be*, and either fails or does something unintended.

RPA is maintenance-intensive. Every application update is a potential flow-breaking event. Every vendor UI refresh is a debugging session.

Use cloud flows whenever a connector exists. Use desktop flows only when there is no other path — and budget for maintenance when you do.
:::

### The decision rule

**If every application in your workflow has a connector, use a cloud flow.** It will be more reliable, easier to maintain, and cheaper to run.

**If any application requires UI interaction — clicking, typing, reading from screens — you need a desktop flow.** Understand that you are accepting a maintenance burden for the capability.

For many city workflows, the answer is both: a cloud flow that triggers on a SharePoint form submission, calls a desktop flow to enter data into a legacy system, and returns to cloud actions for the downstream notification steps. Hybrid patterns are normal, and they concentrate the fragility in the desktop portion where it can be monitored and maintained.

---

## 4. Triggers — What Starts the Work

Every flow has a trigger. The trigger is what makes automation *automated* — work that starts itself rather than waiting for a human to initiate it.

:::{figure} ../images/ch16-trigger-types.png
:label: fig-ch16-trigger-types
:alt: Four-panel diagram showing the four trigger types in Power Automate. Panel 1: Scheduled (clock icon) — runs at a set time or interval. Panel 2: Event-driven (lightning bolt) — runs when something happens in a connected system. Panel 3: Manual (hand icon) — runs when a user clicks a button. Panel 4: Approval-based (checkmark icon) — runs when an approval is granted or denied. Each panel includes a City of Bowie example.
:width: 80%
:align: center

The four trigger types determine *when* your flow runs. The trigger you choose defines what automation means for that workflow.
:::

### Scheduled triggers

The flow runs at a set time or on a recurring schedule. Every Monday at 8 a.m. Every day at midnight. The first business day of each month.

**City of Bowie examples:** The weekly permit application status summary. The monthly constituent inquiry volume report. The daily open work order count for Public Works during storm season.

### Event-driven triggers

The flow runs when something happens in a connected system. A form is submitted. A file is created in a SharePoint library. An email arrives in a shared department mailbox. A row is added to a tracking list.

**City of Bowie examples:** When a resident submits a permit application through the city's online form, route it to the appropriate department and send a confirmation email. When a Public Works work order is filed in SharePoint, notify the assigned crew supervisor. When an email arrives in the Constituent Services shared mailbox, create a service request ticket.

### Manual triggers

The flow runs when a user clicks a button — in Power Automate, in Teams, or embedded in a SharePoint page. It is not truly "automated" in the fire-and-forget sense; it is a standardized, repeatable action that a human initiates on demand.

**City of Bowie examples:** A button in Teams that generates the weekly open permit status report for the department director. A button that sends the standard applicant update email for a specific permit record.

### Approval-based triggers

A special case of event-driven: the flow runs (or branches) based on the outcome of an approval. This is how you build human checkpoints into otherwise automated processes.

**City of Bowie examples:** When a resident requests a fee waiver on a permit, the flow routes the request to the department director. If approved, the flow updates the permit record and sends the approval notice to the applicant. If denied, it sends a different response with next steps. The human judgment is the trigger; the downstream work is automated.

---

## 5. Copilot Inside Power Automate — Describing Flows in Plain English

Microsoft has embedded Copilot directly into the Power Automate designer. You can describe what you want in natural language, and Copilot will generate the flow structure for you.

:::{figure} ../images/ch16-copilot-builds-flow.png
:label: fig-ch16-copilot-builds-flow
:alt: Screenshot-style diagram showing the Power Automate designer with a Copilot chat panel. The user has typed "When a new permit application is submitted through the SharePoint form, extract the applicant name and permit type, and email the appropriate department a summary." Copilot has generated a three-step flow: SharePoint trigger, Parse JSON action, Send Email action.
:width: 80%
:align: center

Copilot in Power Automate lets you describe what you want in plain English. It generates the flow structure — you review, refine, and deploy.
:::

**What Copilot can do in Power Automate:**

- Generate a complete flow from a natural-language description
- Suggest actions based on what you are trying to accomplish
- Explain what an existing flow does
- Help troubleshoot errors
- Generate expressions and formulas for conditions and data transformation

**What Copilot cannot do:**

- Verify that the flow does what your department's process actually requires
- Know which SharePoint list is the right one for this workflow
- Understand that "Permit Type" in your form maps to "Application Category" in your tracking system
- Test the flow against edge cases you have not mentioned
- Accept responsibility for a flow that routes constituent communications incorrectly

The pattern should be familiar by now: **Copilot accelerates construction. Verification is yours.**

A flow built in five minutes with Copilot's help still needs the same testing and validation as a flow built in two hours by hand. In fact, it needs *more* careful review — because speed of construction creates the temptation to skip the review, and an untested flow running on a schedule is exactly how the City of Bowie ends up sending incorrect permit notifications to residents or routing applications to the wrong department.

---

## 6. AI Builder — Teaching Automation to Read Documents

AI Builder is Microsoft's low-code AI capability integrated into the Power Platform. For City of Bowie operations, its most relevant feature is **document processing** — the ability to extract structured data from unstructured documents like PDFs, scanned forms, and submitted images.

:::{figure} ../images/ch16-ai-builder-extraction.png
:label: fig-ch16-ai-builder-extraction
:alt: Diagram showing AI Builder document processing. A permit application form (PDF) enters on the left. AI Builder extracts fields: Applicant Name, Property Address, Permit Type, Requested Date. The extracted data flows into Power Automate, which routes it to the appropriate department and sends a confirmation email to the applicant.
:width: 80%
:align: center

AI Builder turns unstructured documents into structured data. For City of Bowie departments, this means permit applications, constituent request forms, and service requests can flow directly into automated workflows without manual data entry.
:::

### Pre-built models

AI Builder includes pre-built models for common document types:

- **Invoice processing** — extracts vendor, amounts, line items, dates (useful for Finance and Accounts Payable)
- **Receipt processing** — extracts merchant, total, date, payment method
- **Identity document processing** — extracts name, date of birth, document number
- **Business card processing** — extracts name, organization, contact information

### Custom models

For documents specific to city operations — like the City of Bowie's permit application forms, constituent service request forms, or park reservation requests — you can train a **custom document processing model**. You upload sample documents, tag the fields you want to extract, and AI Builder learns to recognize and extract those fields from new documents.

**City of Bowie applications:**

- **Permit applications:** Extract applicant name, property address, permit type, requested start date, and contact information — then route to the appropriate department automatically
- **Constituent service requests:** Extract issue type, location description, and contact details — then create a service ticket and send an acknowledgment
- **Park reservation requests:** Extract group name, event type, requested date and space, and estimated attendance — then check availability and respond
- **Vendor invoices submitted to Finance:** Extract line items and match against approved purchase orders for reconciliation

### The trade-off

Custom models require training data — typically 5-15 sample documents per document type, with fields manually tagged. The model improves as it processes more documents. But the initial investment is real, and the model needs retraining when document formats change.

For documents that arrive in high volume and consistent format — standard permit applications, recurring service request forms — the investment pays off quickly. For one-off or highly variable documents, manual processing may still be the better path.

---

## 7. The Handoff Pattern — Cowork to Power Automate

Here is the workflow that makes automation safe:

:::{figure} ../images/ch16-cowork-to-flow-progression.png
:label: fig-ch16-cowork-to-flow-progression
:alt: Three-stage progression diagram. Stage 1 (Prototype): Cowork prompt run manually 3-4 times, edge cases discovered, constraints refined. Stage 2 (Validation): Final Cowork prompt tested against known good outputs, verified by a second person. Stage 3 (Production): Cowork prompt converted to Power Automate flow, trigger set, monitoring configured.
:width: 80%
:align: center

The prototype-to-production pathway. Cowork is your testbed; Power Automate is your deployment platform. Skip the prototype phase at your peril.
:::

**Stage 1 — Prototype with Cowork**

Run the task as a Cowork prompt three or four times. Each time, note:

- Where did it work exactly as expected?
- Where did it need correction mid-task?
- What edge case surfaced that you had not anticipated?
- What constraint did you add after the second run that you should have included from the start?

After several runs, your Cowork prompt is tight, tested, and edge-case-aware. It has constraints that emerged from real execution, not assumptions.

**Stage 2 — Validate against known outputs**

Before you automate anything, run the Cowork version against a batch of requests whose correct output you already know. Does it route applications correctly? Does it send the right confirmation messages? If yes, the logic is verified. If no, you have found a bug before it processed hundreds of constituent interactions.

Have a second person review the prompt, the logic, and the test results. The person who built it is the worst reviewer — they know what it *should* do and miss what it *actually* does.

**Stage 3 — Convert to Power Automate**

Take the tested Cowork prompt and implement it as a flow:

- Define the trigger (scheduled, event-driven, manual)
- Build the action sequence that mirrors what Cowork did
- Add error handling for cases that could not occur in Cowork but can occur in automation (forms not submitted correctly, attachments missing, permissions denied, timeouts)
- Set up monitoring and alerting so you know when the flow fails

The flow is now in production. It runs without you. It also fails without you — which is why error handling and monitoring are not optional.

::::{admonition} 🧭 Values Check — Accountability
:class: note

**We are accountable for our decisions and how we serve our community.**

A Cowork prompt you ran four times is a prototype. A Power Automate flow running on a trigger is a commitment — one that directly affects residents. When your name is on a flow, you are promising every colleague who depends on its output, and every resident who receives its notifications, that you did the verification work.

Accountability is built by verification, not by confidence in the tool.
::::

---

## 8. Ten City of Bowie Automation Scenarios

This is the practical heart of the chapter. Each scenario names the trigger, the flow logic, the output, and the governance considerations.

:::{figure} ../images/ch16-ges-automation-map.png
:label: fig-ch16-ges-automation-map
:alt: Visual map showing ten City of Bowie automation scenarios arranged by function: Constituent Services (permit intake, constituent inquiry routing), Public Works (work order notification, maintenance scheduling), Parks & Recreation (park reservation intake, event setup checklist), Finance (invoice matching, payment reminders), HR (onboarding checklist), and Governance (access review). Each scenario shows the trigger type and key output.
:width: 80%
:align: center

Ten automation scenarios across City of Bowie departments. Each one saves hours of repetitive work — and each one carries governance responsibilities.
:::

### Scenario 1: Permit Application Intake and Routing

**Trigger:** When a permit application is submitted through the city's online form  
**Flow logic:**
1. AI Builder extracts applicant name, property address, permit type, contact email, and requested start date
2. Validate extracted data against required fields (all required fields present, address format valid)
3. If complete: create permit record in tracking system, route to the appropriate department based on permit type, send confirmation email to applicant with tracking number and estimated review timeline
4. If incomplete: send a notification to the applicant listing missing information; create a pending record flagged for follow-up

**Output:** Permit record created, department notified, applicant confirmation sent, or incomplete application flagged with applicant notification  
**Governance note:** The confirmation email commits the city to a stated review timeline. Make sure the timeline in the template reflects current department capacity and is approved by the department director.

### Scenario 2: Constituent Service Request Acknowledgment

**Trigger:** When an email arrives in the Constituent Services shared mailbox  
**Flow logic:**
1. Parse email for issue type keywords (pothole, streetlight, noise complaint, code enforcement, trash pickup)
2. Classify request by department responsibility based on issue type
3. Create a service request record in the tracking SharePoint list
4. Send acknowledgment email to the resident: "Thank you for contacting the City of Bowie. Your service request has been received and assigned tracking number [X]. Our team will respond within [standard SLA] business days."
5. Send internal notification to the responsible department's shared mailbox

**Output:** Service request tracked, resident acknowledged, department notified  
**Governance note:** The SLA in the acknowledgment email is a public commitment. Ensure it reflects the realistic capacity of each department and is reviewed annually. A missed SLA is a service failure — and residents will reference the email.

### Scenario 3: Open Work Order Status Report (Public Works)

**Trigger:** Scheduled — every Monday at 7 a.m.  
**Flow logic:**
1. Pull all open work orders from the Public Works SharePoint tracking list
2. Filter by status (Open, In Progress, Overdue)
3. Calculate days open for each work order
4. Flag any work order open more than 10 business days as overdue
5. Generate a summary and post to the Public Works Teams channel
6. If any overdue work orders exist: send alert to the Public Works Director

**Output:** Weekly open work order summary in Teams, alert when overdue items exist  
**Governance note:** The 10-business-day threshold is a policy decision, not a technical one. Document it in the flow description and review it with department leadership annually. This threshold may differ by work order type.

### Scenario 4: Park Reservation Request Processing

**Trigger:** When a park reservation request form is submitted  
**Flow logic:**
1. Extract group name, contact information, requested park/facility, requested date and time, event type, and estimated attendance
2. Check the Parks & Recreation facility availability calendar in SharePoint
3. If available: create a tentative reservation record, send acknowledgment to applicant with next steps (insurance certificate requirement, deposit information, permit fee schedule)
4. If unavailable: send a response indicating the conflict with alternative dates if applicable

**Output:** Reservation record created or conflict notification sent  
**Governance note:** This flow creates a tentative record only — final reservation confirmation requires human review of the insurance certificate and fee payment. Build a clear status distinction in the system so staff can distinguish tentative from confirmed reservations.

### Scenario 5: Allen Pond Park Event Setup Checklist Distribution

**Trigger:** Scheduled — 5 days before each permitted city event at Allen Pond Park  
**Flow logic:**
1. Check the city events calendar in SharePoint for events occurring in the next 5 days
2. For each event: pull the event coordinator, assigned Public Works crew, and any special setup requirements from the event record
3. Generate a setup checklist for the event (standard template plus event-specific additions)
4. Send the checklist to the event coordinator, assigned Public Works supervisor, and Parks & Recreation manager
5. Create a task in Microsoft Planner for each checklist item with the assigned responsible party

**Output:** Setup checklists distributed, Planner tasks created for accountability  
**Governance note:** Public events involve safety considerations. This flow distributes the checklist but does not replace the on-site setup inspection. Build a clear note in every checklist that it must be completed and returned to Parks & Recreation before the event opens to the public.

### Scenario 6: Finance — Vendor Invoice Matching

**Trigger:** When a vendor invoice is received in the Finance department's invoice shared mailbox  
**Flow logic:**
1. AI Builder extracts vendor name, invoice number, amount, line items, and dates
2. Cross-reference against the approved purchase order list in SharePoint
3. If match found and amount within tolerance: create an invoice record, route to the appropriate department budget manager for review and approval
4. If no matching purchase order: flag as unmatched, notify the Finance Director, and send an acknowledgment to the vendor that the invoice is under review

**Output:** Invoice matched and routed for approval, or unmatched invoice escalated  
**Governance note:** This flow initiates the review process — it does not approve payments. Final payment approval remains a human action. Ensure the flow's routing correctly maps invoice types to the appropriate budget authorities in line with the city's financial authorization policy.

### Scenario 7: HR New Employee Onboarding Checklist

**Trigger:** When a new employee record is created in the HR SharePoint list  
**Flow logic:**
1. Extract employee name, department, start date, and supervisor from the new record
2. Generate an onboarding checklist based on the department template
3. Send the checklist to the new employee's supervisor with task due dates relative to the start date
4. Create tasks in Microsoft Planner for IT (account setup, equipment), Facilities (access card, parking), HR (benefits enrollment reminder), and the department supervisor (buddy assignment, first-week schedule)
5. Schedule automated reminder emails at day 3 and day 7 for any incomplete onboarding tasks

**Output:** Onboarding checklist distributed, department tasks created, automated reminders set  
**Governance note:** Employee start information is sensitive HR data. Ensure this flow's SharePoint list has appropriate access restrictions — not all city staff should have access to new hire records.

### Scenario 8: Safety Inspection Escalation (City Facilities)

**Trigger:** When a facility safety inspection form is submitted via Microsoft Forms with any item marked "Failed"  
**Flow logic:**
1. Extract the failed items, their locations, and severity ratings from the form
2. Determine urgency based on item category (structural or life safety vs. general maintenance)
3. If life safety: immediate notification to the City Manager's office, Department Director, and Facilities Manager; create urgent work order in the tracking system
4. If general maintenance: notification to Facilities Manager; create standard work order
5. Log the submission with timestamp and form data for audit trail

**Output:** Escalation notifications, work orders created, audit record logged  
**Governance note:** Safety inspection documentation has legal implications for the city's liability. Retention policies apply. Ensure the flow creates an auditable, timestamped record that cannot be deleted or modified. Review with the City Attorney's office before deployment.

### Scenario 9: SharePoint Site Access Review at Project Close

**Trigger:** When a project status is changed to "Complete" in the city projects tracking list  
**Flow logic:**
1. Pull the current access list for the project's SharePoint site
2. Compare against the core project team (those who should retain access for records purposes)
3. Generate a report of access to be removed
4. Send to IT and the project manager for review
5. After approval: remove access for non-core members

**Output:** Access review report, access cleanup after approval  
**Governance note:** This directly addresses the risk of staff or contractors retaining access to sensitive project materials after project completion. Government records have specific retention and access requirements under Maryland Public Information Act requirements. Consult with the City Clerk's office on appropriate retention access for different project types.

### Scenario 10: Monthly Constituent Service Request Volume Report

**Trigger:** Scheduled — first business day of each month at 8 a.m.  
**Flow logic:**
1. Pull all service requests logged in the prior calendar month from the Constituent Services SharePoint tracking list
2. Group by request type, department assigned, and resolution status
3. Calculate average resolution time by request type and department
4. Flag any request type where average resolution time exceeded the published SLA
5. Generate a summary workbook with charts by department and request type
6. Post the summary to the City Administration Teams channel
7. Email the department directors with their department's metrics

**Output:** Monthly volume analysis, department scorecards, Teams post  
**Governance note:** This report contains service performance data that department directors will use for staffing and process decisions. Ensure the data definitions are consistent and documented — "resolution date" should mean the same thing in every department's records before this data is used for management decisions.

---

## 9. Governance — The Automation Multiplier

:::{figure} ../images/ch16-approval-checkpoint.png
:label: fig-ch16-approval-checkpoint
:alt: Flow diagram showing an approval checkpoint in a Power Automate flow. The flow pauses at an approval step, sends a request to the designated approver, and branches based on the response: Approved continues the flow, Rejected stops it and sends a notification.
:width: 80%
:align: center

Approval steps are designed control points. They insert human judgment exactly where the process requires it — and nowhere else.
:::

Automation multiplies whatever you built. That is the promise and the peril.

**If you automated an efficient, verified process**, you have just scaled that efficiency to every instance where the trigger fires. Every permit application. Every constituent request. Every month's reporting cycle. Forever.

**If you automated an unverified process**, you have just scaled that error to the same degree. An incorrect routing rule, a wrong SLA in the confirmation email, a missing validation step — now running for every resident interaction at machine speed with no human to notice.

::::{admonition} ⚠️ Never Automate an Unverified Process
:class: danger

The single most expensive automation mistake is not a failed flow. It is a *successful* flow running an incorrect process.

A failed flow produces an error message. Someone investigates. The problem is found and fixed.

A flow running an incorrect process produces outputs that look correct. Nobody investigates because nothing failed. The incorrect output — wrong department routing, incorrect SLA commitments, missing escalations — becomes the basis for decisions, resident communications, and department operations.

By the time someone notices, the damage is distributed across weeks or months of resident interactions.

**Before any flow goes to production:**
1. Run the equivalent process manually at least twice with verified outputs
2. Run the flow against test submissions where you know the correct response
3. Have a second person review the logic — ideally someone from the affected department
4. Run in production with monitoring and a brief manual parallel-check period before trusting it silently
::::

### Flow Ownership and Orphaned Flows

A flow runs with the permissions of its **owner** — the person who created it or to whom ownership was transferred. When that person leaves the city or changes departments, their flows do not stop. They become **orphaned**: still running, still accessing data, but owned by an account that may be disabled or reassigned.

:::{figure} ../images/ch16-flow-ownership-risk.png
:label: fig-ch16-flow-ownership-risk
:alt: Risk diagram showing orphaned flow scenario. Original creator leaves city employment, flow continues running with their stale permissions, accesses data they should no longer see, or fails silently when their account is disabled. Arrows show the cascading failure modes.
:width: 80%
:align: center

Orphaned flows are automation liabilities. When the owner leaves city employment or transfers departments, the flow's permissions become stale — and its failures become invisible.
:::

**The risk**: A flow created by a Constituent Services staff member who had access to resident service request records continues running after that person transfers to a different department — or leaves city employment entirely. The flow still reads resident data. If the account is disabled, the flow fails silently. Nobody finds out until residents stop receiving acknowledgments or supervisors notice that the routing has stopped.

**The mitigation**: Flow ownership must be part of offboarding and department transfer procedures. When someone leaves a role, their flows transfer to their successor — explicitly, with documentation, on their last day. IT should maintain an inventory of flows by owner and audit it quarterly.

::::{admonition} ⚠️ A Flow Runs as Its Owner
:class: danger

The permission model from earlier chapters applies to flows exactly as it applies to Cowork: **a flow can access anything its owner can access**.

If you have broad access across multiple department SharePoint sites and you create a flow that reads from "all constituent service records," that flow inherits your broad access. It can read data that your role can access but that should not be combined into a single automated output visible to others.

Cross-department data access in government is not just a privacy concern — it may have legal implications under Maryland's Public Information Act and federal privacy regulations.

Before creating a flow that touches resident data, ask: **if this flow's output were seen by someone outside the department, what would be in it?** Then scope the flow so the answer is "only what they should see."
::::

### Error Handling and Silent Failure

:::{figure} ../images/ch16-error-handling.png
:label: fig-ch16-error-handling
:alt: Comparison diagram showing two flows. Left: flow with no error handling — an action fails, the whole flow fails, no notification, nobody knows. Right: flow with error handling — an action fails, the flow catches the error, logs it, sends notification to the owner, continues with remaining actions or fails gracefully.
:width: 80%
:align: center

The difference between error handling and hope. The flow on the left fails invisibly. The flow on the right fails loudly — which is the only kind of failure you can fix.
:::

A flow that fails silently is worse than a flow that fails loudly.

**Silent failure modes in city operations:**
- A constituent submitted a permit application but the form attachment was missing; the flow logged nothing and the resident never heard back
- An approval request was sent to a supervisor who is on leave; the flow is waiting forever while a resident waits for a response
- A SharePoint list column was renamed during a site update; the flow is reading the wrong field and routing applications incorrectly
- The flow succeeded but produced the wrong routing because a new permit type was added to the form without updating the flow's classification logic

**Error handling is not optional:**

1. **Try-catch scopes** — wrap actions that might fail and define what happens when they do
2. **Notifications on failure** — send an email or Teams message to the flow owner when something breaks
3. **Logging** — write to a run history that someone can review
4. **Timeouts with escalation** — if an approval does not come within a set period, escalate or fail explicitly so residents are not left without a response

The goal is not to prevent all failures — some failures are legitimate (a form submission really was incomplete). The goal is to make failures *visible* so someone can act on them and residents can be served appropriately.

### Approval Steps as Control Points

Not every flow should run without human oversight. Approval steps are how you insert human judgment where the process requires it.

**Use approval steps for:**
- Any communication to residents that contains a commitment or decision (permit approval, waiver decision, variance grant)
- Fee exceptions or adjustments outside standard rates
- Safety-related escalations that require management awareness
- Any output that will be used as the basis for a legal record or formal city action

**Do not use approval steps for:**
- Every action in the flow (that defeats the purpose of automation)
- Routine acknowledgment emails that contain no commitments beyond "we received your submission"
- Internal logging and filing actions
- Informational summaries sent to department leadership

The design principle: **automate the work that does not require judgment; pause for judgment where it does**.

---

## 10. Honest Limitations

This section exists because the vendors will not write it.

**Desktop RPA is brittle.** It breaks when UIs change. It requires a machine to be running (or a hosted RPA bot, which costs money). It is maintenance-intensive. Use it only when there is no connector and no API — and budget for the maintenance.

**Premium connectors cost money.** The Power Automate Premium license is approximately $15 per user per month. Some connectors require additional licensing. Hosted RPA bots are approximately $215 per bot per month. Government technology budgets are constrained — plan accordingly and get approvals before building on premium features.

**Not everything should be automated.** If the process requires nuanced judgment at every step, automation does not help — it just creates a flow that pauses for approval constantly. If the process is a one-off or rare event, the automation investment may exceed the time it saves. If the process is not yet well-understood or is under active policy revision, automating it locks in whatever you think it is — which may not match the policy when it changes.

**Maintenance burden is real and under-estimated.** Flows break when connectors are updated, when SharePoint lists are restructured, when form fields are renamed, when personnel change, when policies change. Every flow is a small piece of infrastructure that requires occasional attention. Ten flows in production require attention ten times as often as one.

**Automation can mask problems.** A manual process forces someone to look at the data every time. An automated process runs whether the data is right or wrong. If the upstream data quality is poor — inconsistently formatted addresses, missing required fields, incorrect permit type selections — automation hides those problems until the downstream outputs are obviously wrong.

**Government context adds additional constraints.** City automation interacts with resident data, triggers official communications, and initiates formal administrative processes. The legal and accountability implications of an incorrect automated output are different in city government than in a private company. When in doubt, add an approval step rather than remove it.

The right mindset: automation is a trade-off, not a gift. It trades ongoing execution time for upfront design and ongoing maintenance. That trade is usually favorable for high-frequency, stable, well-understood processes. It is often unfavorable for infrequent, changing, or judgment-intensive ones.

---

## 11. Build Your First Flow — A Walkthrough

This walkthrough builds a simple, practical flow that a City of Bowie employee without technical background can complete in 30 minutes. It demonstrates the core concepts without requiring premium connectors or complex logic.

**The scenario:** Every week, you want to receive an email summarizing how many constituent service requests were logged in the team's SharePoint tracking list in the past 7 days.

**Step 1 — Open Power Automate**

Go to [make.powerautomate.com](https://make.powerautomate.com) and sign in with your City of Bowie Microsoft 365 account.

**Step 2 — Create a new flow**

Click **+ Create** in the left navigation, then select **Scheduled cloud flow**. Name it "Weekly Service Request Summary" and set the schedule: every Monday at 8 a.m.

**Step 3 — Add the first action**

Click **+ New step** and search for "SharePoint." Select **Get items** from the SharePoint connector.

- **Site Address:** Select your department's SharePoint site
- **List Name:** Select the service request tracking list

**Step 4 — Filter to recent submissions**

Click **+ New step** and search for "Filter array." This is a Data Operations action.

- **From:** Select the "value" output from the previous SharePoint step
- **Condition:** Select the "Created" field, choose "is greater than," and enter an expression: `addDays(utcNow(), -7)`

This filters to only records created in the last 7 days.

**Step 5 — Count the records**

Click **+ New step** and search for "Compose" (Data Operations). In the **Inputs** field, enter the expression: `length(body('Filter_array'))`

This gives you the count of recent service requests.

**Step 6 — Send the email**

Click **+ New step** and search for "Outlook." Select **Send an email (V2)**.

- **To:** Your email address (or your supervisor's)
- **Subject:** Weekly Constituent Service Request Summary
- **Body:** Compose a message like: "In the past 7 days, [output of Compose] new constituent service requests were logged in the [department] tracking list."

**Step 7 — Save and test**

Click **Save** in the top right. Then click **Test**, select **Manually**, and click **Test** again. The flow will run immediately. Check your email.

**Step 8 — Review and refine**

Look at the test results. Did it count correctly? If not, check your filter expression. Once it works, the flow will run automatically every Monday at 8 a.m.

---

## 12. The Compounding ROI of Automation

:::{figure} ../images/ch16-automation-roi-compounding.png
:label: fig-ch16-automation-roi
:alt: Graph showing automation ROI over time. X-axis is time in months, Y-axis is cumulative hours saved. The curve shows initial investment (negative), break-even point, and then accelerating returns as the flow runs repeatedly. A callout shows the compounding effect: 15 minutes saved × 200 applications per month = 50 hours per month.
:width: 80%
:align: center

Automation ROI compounds over time. The initial investment is repaid, and then the savings accelerate — because the flow keeps running while you do other work.
:::

The math of automation in city operations is tangible.

A 15-minute task — routing a permit application, acknowledging a constituent service request, generating a weekly status report — automated and running consistently at volume can save significant staff time every month. That time goes back to the work that requires judgment: complex constituent inquiries, policy questions, exceptions that need human review.

But the compounding effect is larger than the raw time savings:

**Consistency improves.** The 500th permit application routed by the flow is handled identically to the first. Human execution drifts — shortcuts, variations, forgotten steps. Residents who submitted applications months apart receive the same experience. That consistency is itself a form of equitable service delivery.

**Speed improves.** The flow runs in seconds. A staff member handling a high-volume day takes much longer. For time-sensitive processes — acknowledgment emails, safety escalations — that speed difference directly affects the resident experience.

**Availability improves.** The flow runs on weekends, holidays, and evenings. Residents who submit applications outside business hours still receive timely acknowledgments. That responsiveness builds trust.

**Staff attention shifts.** Instead of routing routine applications, staff review the exceptions the flow flags. That is higher-value work — judgment, context, human connection with residents who have complex situations.

The cost is real: design time, testing time, maintenance time, and the organizational discipline to verify before deploying. But for high-frequency, stable city processes, the trade-off almost always favors the residents who receive better, faster, more consistent service.

::::{admonition} 🧭 Values Check — Pride
:class: note

**We take pride in serving Bowie with professionalism and excellence.**

Pride is not heroic effort on behalf of one resident at a time. It is consistent, excellent service delivered to every resident who interacts with the city. Automation is how that consistency scales — the same quality of response at 8 a.m. on a Tuesday and 11 p.m. on a Saturday, for the tenth application of the day and the hundredth.
::::

---

## 13. Try This: Convert a Cowork Task to a Flow

Pick a Cowork task you have run at least three times and that produces the same output structure each time.

**Step 1 — Document the Cowork prompt**

Write out the current five-part prompt: Outcome, Inputs, Definition of done, Constraints, Approval scope.

**Step 2 — Identify the trigger**

What event would naturally start this task without you? A form submission? A date arriving? An email arriving in a shared mailbox?

**Step 3 — Map the actions**

List every step Cowork takes. For each step, identify the Power Automate connector or action that would accomplish the same thing.

**Step 4 — Identify the human checkpoints**

Where in the Cowork version do you stop and review before approving? Those become approval actions in the flow. Remember: for any action that sends a formal commitment to a resident, a human checkpoint is almost certainly appropriate.

**Step 5 — Build it (or spec it)**

If you have Power Automate access, build the flow. If not, write a specification document that someone could build from — detailed enough that they would not need to ask clarifying questions.

**Step 6 — Test against known output**

Run the flow against test submissions where you already know the correct response. Does it match?

---

## 14. Productive Struggle Problem

You are the Constituent Services manager for the City of Bowie. Over the past six months, you have noticed that resident complaints about response time vary significantly depending on the type of request — some issues are resolved in 2 days, others take 3 weeks, and residents rarely know where their request stands.

You have three data sources:
1. Constituent service request intake records (SharePoint list, updated when requests are received)
2. Department work order or ticket systems (varies by department — some use SharePoint, some use legacy tools accessible only through a web portal)
3. Resident communication records (email threads in the Constituent Services shared mailbox)

**The challenge:** Design an automated constituent status communication system.

1. **Define the trigger.** What event or schedule would initiate status updates to residents? Should it be time-based, status-based, or event-driven? Justify your choice.

2. **Map the flow.** List the actions in sequence. Identify which use cloud connectors and which might require desktop flows (RPA) to access legacy department systems. For each RPA action, describe why it is necessary and what maintenance burden it creates.

3. **Design the output.** What does the resident-facing status update look like? What information should it include — and what should it not include for privacy reasons? Where is it delivered (email, text, city portal)?

4. **Add governance.** What approval steps belong in this flow? What error handling is required? How do you ensure that the automated message accurately reflects the actual status — and does not create legal commitments the city cannot keep?

5. **Estimate ROI.** If manually sending status updates takes 30 minutes per day across the department, and the flow takes 40 hours to build and test and 3 hours per month to maintain, how many months until break-even?

6. **Identify what you would not automate.** What part of the constituent experience still requires direct human contact, and why?

---

## 15. Closing the Arc — From Asking to Automating

This is the final chapter of the book.

Look back at where you started. In Chapter 1, you learned what AI can and cannot do. In Chapter 4, you learned to prompt well. In Chapters 7-11, you learned to use Copilot in Word, Excel, PowerPoint, Outlook, and Teams. In Chapter 12, you learned why SharePoint governance is AI governance. In Chapter 13, you learned to build analytical systems. In Chapter 14, you learned to delegate to Cowork. In Chapter 15, you learned to use AI for creative ideation.

Now you have learned to automate.

The arc is not technological. It is professional.

**Asking** teaches you what AI can do and builds trust through verification. You see every output. You approve every action.

**Delegating** teaches you to scope work precisely and review like a manager. You define outcomes and constraints; AI handles execution. You step back from the middle of the work and focus on the ends.

**Automating** teaches you to remove yourself entirely — for the work that does not need you. You design once, verify carefully, and let the process run for every resident who interacts with the city.

That progression describes a career, not a curriculum. The city employee who started this book asking Copilot to rewrite an email ends it designing automation that acknowledges resident permit applications, routes constituent service requests, and generates department performance reports — without requiring a person to be there at 11 p.m. on a Saturday night.

What does that mean for a career at the City of Bowie?

It means **more time on judgment and less time on execution**. The permit routing flow runs itself; you handle the complex applications that require interpretation. The acknowledgment email goes out automatically; you respond to the resident who calls with a follow-up question. The monthly report assembles itself; you present the patterns and recommendations to the department director.

It means **higher leverage**. A single Constituent Services staff member with well-designed automation can handle resident interactions at a volume that previously required a larger team for routine tasks — freeing that team for the work that requires human judgment and genuine connection with residents.

It means **new skills matter**. The ability to design a good process, verify it rigorously, scope automation appropriately, and maintain it responsibly is as valuable as the ability to execute the process manually — more valuable, because the design scales and the execution does not.

The City of Bowie's mission is to serve its residents — more than 70,000 people who depend on their local government to be responsive, accountable, and professional. That mission does not change with AI. What changes is the city's capacity to live up to it — consistently, at scale, and with the human attention directed where residents need it most: the complex, the urgent, and the moments that require a real person.

That is the work. And now you know how to do it.

::::{admonition} 🧭 Values Check — Responsiveness
:class: note

**We respond to our community's needs with care and accuracy.**

Automation is how responsiveness scales. Every resident who submits a permit application at 10 p.m. and receives an acknowledgment at 10:01 p.m. experiences city government that takes their time seriously. Every constituent whose service request is routed correctly and followed up on schedule experiences a city that does what it said it would do.

Automation built responsibly — verified, governed, monitored — is responsiveness at city scale.
::::

---

## 16. Leader's Takeaway

Automation changes what your team does. That requires changing how you lead them.

**First: the prototype discipline is non-negotiable.** No flow goes to production without being tested as a Cowork prompt first, validated against known outputs, and reviewed by a second person — ideally someone in the affected department. The cost of an unverified automated process that sends incorrect information to residents is not just operational; it is a trust issue with the community the city serves.

**Second: flow ownership is a governance issue.** Every flow must have a named owner. When people leave city employment or transfer departments, their flows transfer — explicitly, documented, on their last day. IT should maintain an inventory and audit it quarterly. Orphaned flows that send communications to residents or route applications incorrectly are a liability for both the city and the residents they affect.

**Third: error handling is not optional.** A flow that fails silently leaves residents without responses. Every flow must log its runs, catch its errors, and notify someone when something breaks. If you cannot answer "who gets notified when this flow fails, and how quickly?", the flow is not ready for production.

**Fourth: automation does not reduce headcount — it changes work.** The staff member who used to route permit applications now handles the complex cases the flow escalated. The coordinator who used to send acknowledgment emails now focuses on residents who called with questions the email could not answer. Automation shifts people from execution to service — and that is a higher-value role that requires deliberate training and management.

**Fifth: start with the high-frequency, stable, well-understood processes.** The permit application acknowledgment that goes out dozens of times per week is a better automation target than the occasional variance request that requires policy interpretation. The routine work order notification is a better target than the one-off emergency escalation. Prioritize by frequency × stability × clarity of rules.

**Sixth: government context matters.** City automation touches resident lives and triggers official city actions. The accountability standard is higher than in a private organization. When in doubt about whether to include a human approval step, include it. A slightly slower process that residents trust is better than a faster one that occasionally fails in ways that damage the city's credibility.

The organizations that extract the most from automation are not the ones that automate the most. They are the ones that automate *carefully* — choosing the right processes, verifying rigorously, governing deliberately, and maintaining responsibly.

For the City of Bowie, serving more than 70,000 residents with a team that is always smaller than the demand on it, the opportunity is real. So is the responsibility.

Lead accordingly.

---

## Glossary

```{glossary}
Power Automate
  Microsoft's automation platform for building workflows (flows) that run on triggers. Part of the Microsoft Power Platform alongside Power Apps, Power BI, and Copilot Studio.

Cloud flow
  A Power Automate flow that runs on Microsoft's servers, connecting applications through API-based connectors. More reliable and easier to maintain than desktop flows.

Desktop flow
  A Power Automate flow that runs on a Windows machine, automating applications through UI interaction (clicking, typing, reading screens). Required when applications lack API connectors. Also called RPA.

Robotic Process Automation (RPA)
  Automation that mimics human interaction with software — clicking buttons, typing into fields, reading text from screens. Necessary for legacy applications without APIs; brittle and maintenance-intensive.

Trigger
  The event that starts a Power Automate flow. Types include scheduled (runs at a set time), event-driven (runs when something happens), manual (runs when a user clicks a button), and approval-based (runs based on approval outcome).

Connector
  A standardized API integration in Power Automate that enables flows to interact with a specific service (SharePoint, Outlook, Teams, and others). Microsoft offers 1,000+ connectors.

AI Builder
  Microsoft's low-code AI capability for document processing, object detection, text classification, and prediction. Integrated into Power Platform; enables extraction of structured data from unstructured documents such as permit applications and service request forms.

Document processing model
  An AI Builder model that extracts specific fields from documents. Pre-built models exist for invoices, receipts, and identity documents; custom models can be trained for organization-specific documents like City of Bowie permit application forms.

Flow owner
  The person responsible for a Power Automate flow. Flows run with the owner's permissions — a flow can access anything its owner can access. Ownership must transfer when people leave city employment or change departments.

Orphaned flow
  A flow whose owner has left city employment or transferred departments without transferring ownership. Continues running with stale permissions; may fail silently when the owner's account is disabled.

Approval action
  A Power Automate action that pauses the flow, sends an approval request to designated approvers, and branches based on the response. Used to insert human judgment at control points — especially important in government workflows that generate official communications to residents.

Error handling
  Flow logic that catches failures, logs them, and notifies appropriate people rather than failing silently. Includes try-catch scopes, failure notifications, and timeout escalations.

Premium connector
  A Power Automate connector that requires a Premium license ($15/user/month) to use. Includes many third-party services and advanced Microsoft capabilities. Requires budget approval for government use.

Hosted RPA bot
  A virtual machine running Power Automate Desktop, hosted in Microsoft's cloud, that executes desktop flows without requiring the user's local machine to be running. Approximately $215/bot/month.

Cowork-to-flow progression
  The recommended pattern for building automation: prototype as a Cowork task, refine through iteration, validate against known outputs, then convert to a Power Automate flow for production deployment.

Silent failure
  A flow failure that produces no notification — the flow stops running but nobody is alerted. In city operations, silent failure means residents stop receiving responses without staff knowing. The most dangerous failure mode because problems compound before discovery.

SLA (Service Level Agreement)
  A committed timeframe for responding to or resolving a constituent service request or permit application. Automated acknowledgment emails that cite an SLA create a public commitment — ensure it reflects actual department capacity before deploying.

Constituent notification
  An automated communication sent to a Bowie resident triggered by an event in city systems — permit approval, payment due reminder, service request status update. Constituent notifications carry the city's name and must be accurate, professional, and compliant with city communication standards.
```

---

## Discussion

The progression from asking to delegating to automating is not just a technology adoption curve. It is a professional development arc — and in city government, it carries a particular kind of weight.

Consider your current role at the City of Bowie. Which of your regular tasks belong at each level — Chat, Cowork, or Power Automate? What would need to be true — in terms of process clarity, verification, and governance — before you could move a task from one level to the next?

Then consider the harder question: if the routine execution work you do were automated, what would you do with the time? And what would your residents experience differently?

::::{admonition} 📝 Discussion Guidelines
:class: note

Post your reflection in the course discussion forum before the session closes. Your response should:

- Identify one process in your role that is currently manual, describe how it would be automated, and specify which trigger type you would use
- Identify one process you would **refuse** to automate, and explain why — referencing governance, judgment requirements, resident impact, or risk considerations from this chapter
- Address the verification question: what testing would you require before deploying a flow that sends automated communications to Bowie residents?
- Respond to at least **two peers** with substantive engagement — challenge an automation choice, identify a governance gap they missed, or build on their ideas
- Reference at least one credible source — Microsoft Power Automate documentation, this chapter's governance framework, or the City of Bowie's values of Accountability, Responsiveness, Stewardship, and Pride

Minimum 300 words for your main post.
::::

---

::::{admonition} 🧭 Values Check — Stewardship
:class: note

**We are stewards of the public trust and the resources our community entrusts to us.**

Stewardship in automation means two things.

First: stewardship of resources. Automation built thoughtfully multiplies the city's capacity to serve residents without multiplying costs. That is responsible use of the public resources entrusted to city government.

Second: stewardship of trust. Every automated communication that goes to a Bowie resident carries the city's credibility. Stewardship means verifying before deploying, monitoring after deploying, and correcting immediately when something goes wrong — because residents trust the city to get it right.

AI does not change that obligation. It changes the scale at which the city can live up to it.
::::
