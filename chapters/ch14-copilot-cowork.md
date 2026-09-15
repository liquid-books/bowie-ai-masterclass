---
title: "Chapter 14: Copilot Cowork — Delegating Real Work"
subtitle: "From Answering Questions to Finishing Work — The Third Gear of Microsoft 365 Copilot"
short_title: "Copilot Cowork"
description: "Microsoft Copilot Cowork went generally available on June 16, 2026. It does not answer questions — it executes long-running, multi-step, multi-app work and returns finished artifacts. This chapter teaches the Chat vs. Cowork vs. Agents decision rule, Microsoft's five-part Cowork prompting structure, the approval and governance model, the Copilot Credits economics, and nine fully worked City of Bowie scenarios spanning project management, constituent services, Public Works, Finance, Planning, HR, grant applications, and sustainability reporting."
label: ch14-copilot-cowork
tags: [Copilot Cowork, delegation, Work IQ, Microsoft 365, approvals, governance, Copilot Credits, Anthropic, Opus 4.8, Sonnet 4.6, city government, project management, constituent services, Public Works, Finance, Planning, HR, grant applications, sustainability, City of Bowie, Accountability, Responsiveness, Stewardship, Pride]
---

```{admonition} Download this Chapter as PDF
:class: tip

```

# Chapter 14: Copilot Cowork — Delegating Real Work

> *"It is easy to have a dozen tasks in flight at once, each one moving forward while you focus on what only you can do."*

It is 4:40 p.m. on the last day of a major road rehabilitation project in Bowie. A city project manager is standing at the site, watching the final lane striping go down, holding a radio in one hand and a phone in the other. The subcontractor is running thirty minutes behind on final inspection paperwork. Two contractor invoices are still unreconciled. The Public Works Director wants a preliminary closeout summary "sometime tomorrow, ideally before the City Council briefing."

That closeout package is real work. It means pulling the workforce hours from the on-site logs, comparing them to the forecast, reconciling contractor invoice amounts against the project budget targets, cross-referencing the change orders that were approved in the field against what was actually delivered, and writing a narrative that a department director can read in six minutes and understand.

It is four hours of work, minimum. It requires SharePoint, Excel, Outlook, Teams, and a document library. And the person who has to do it is currently standing on a job site with a dying phone battery and an 8:00 a.m. Council briefing.

Here is the change this chapter is about. That project manager can open Copilot on their phone, describe the *outcome* they want, attach the project's document library, and walk away. The task keeps running when the phone goes into airplane mode. By the time they get back to City Hall, there is a draft closeout workbook in the project folder, a narrative summary in Word, and a proposed email to the department director waiting for approval — not sent, waiting.

That is Copilot Cowork. And the skill it demands is not a new kind of prompting. It is a new kind of *management*.

---

## 1. The Shift: Copilot Now Has Three Gears

Every chapter before this one taught you to work *with* Copilot. This chapter teaches you to delegate *to* it.

The distinction matters more than it sounds. Up to now, the pattern has been consistent: you prompt, Copilot responds, you evaluate, you refine. You are the loop. Every step passes through you. That is a genuinely powerful way to work, and for a large share of daily tasks it remains the right one.

Cowork breaks that pattern. You describe an outcome. Cowork plans the steps, opens the apps, retrieves the files, does the analysis, produces the documents, and pauses only when it needs a decision from you. You are no longer the loop. You are the reviewer.

Microsoft frames the Copilot family in three modes, and this table is the single most important thing in the chapter. Learn it well enough to explain it to a colleague in thirty seconds.

```{list-table} The three modes of Microsoft 365 Copilot
:header-rows: 1
:name: table-ch14-three-modes

* - 
  - **Chat**
  - **Cowork**
  - **Agents**
* - **Best for**
  - Conversational AI for drafting, Q&A, and ideation
  - Delegating and executing long-running, multi-step work across your apps
  - Ready-made assistants for specialized or repeatable tasks
* - **How you interact**
  - A conversation — you steer each step from prompt to response
  - An assignment — you describe the goal and check in at key milestones
  - A workflow — you pick an agent built for a specific job
* - **Typical work pattern**
  - **You're in the loop.** One prompt, one result, then you choose what's next
  - **You step away.** Cowork plans, manages files and tasks across apps, and delivers completed work
  - **You run it on demand.** The agent handles the same scoped task each time
* - **City of Bowie example**
  - "Rewrite this constituent notice so it's clearer about the permit deadline."
  - "Produce the project closeout package for the Route 197 rehabilitation and draft the director summary email."
  - The constituent inquiry triage agent that classifies inbound service requests every morning
```

:::{important}
**The decision rule — memorize this**

Ask yourself one question before you open anything: **how many steps and how many apps?**

- **One step, one app, and I want to see the answer right now** → **Chat**
- **Many steps, several apps, and I want a finished artifact I can review and ship** → **Cowork**
- **The same narrow task, over and over, on demand or on a trigger** → **an agent**

If you can describe the work as a *question*, it's Chat. If you can only describe it as a *deliverable*, it's Cowork. If you find yourself describing the same deliverable every week, it's time to build an agent — or schedule the Cowork task.
:::

The professional behavior underneath this is worth naming plainly, because it is the actual skill.

The prompt-craft skill of Copilot Chat is **describing a task**. The skill of Cowork is **describing an outcome and then reviewing like a manager.**

Anyone at the City of Bowie who has ever managed a public works crew or a community program knows exactly what that means. You do not tell a field supervisor which tool to pick up. You tell them what the finished project looks like, what the constraints are (traffic control requirements, weather window, Council deadline, budget authorization), what you want to be consulted on, and then you let them work — and you inspect the result before the public or City Council sees it. That is precisely the relationship Cowork asks for.

:::{note}
**Why this feels uncomfortable at first — and why that's normal**

Delegation is a learned skill for humans, and it is uncomfortable for the same reason with software: the first few times, you will want to watch every step, and watching every step defeats the purpose.

The mental model that helps most people over the hump is this: you are not giving up control. You are moving your control from the *middle* of the work to the *ends* of it — a tight brief at the front, a rigorous review at the back. That is more control over what matters and less over what doesn't.
:::

---

## 2. What Copilot Cowork Actually Is

### 2.1 The one-sentence definition

**Copilot Cowork executes complex, long-running, multi-tool tasks end-to-end across Microsoft 365 and returns finished artifacts — a report, a presentation, an email, an updated workbook — not a draft suggestion or a recommendation.**

### 2.2 The timeline

Cowork did not appear overnight, and its history tells you something about how carefully it was built.

```{list-table} How Cowork reached general availability
:header-rows: 1
:name: table-ch14-timeline

* - Stage
  - When
  - What it meant
* - Research Preview
  - Early 2026
  - A limited set of customers testing the concept of delegated, multi-step work
* - Frontier program
  - Late March 2026 (announced March 9)
  - Broad early access inside Microsoft's Frontier program. Became the **fastest-growing feature in the history of that program** and recorded the **highest user satisfaction of any Copilot or agent experience Microsoft has shipped**
* - General Availability
  - **June 16, 2026** — worldwide
  - Available to any organization with the Microsoft 365 Copilot license, subject to admin enablement
```

At GA, **more than half of the Fortune 500** were already using it, including Accenture, Avanade, Advance Local, Capital Group, Koch, LTM, Ooredoo Qatar, and Zurich Insurance. That adoption curve is unusual, and it's the strongest available evidence that this is not a novelty feature — and that municipal governments are well-positioned to capture the same gains.

### 2.3 The models — and the Anthropic relationship

Cowork's underlying intelligence is worth understanding, because it explains both its capability and its cost model.

Microsoft worked **closely with Anthropic** and **integrated the technology behind Claude Cowork into Microsoft 365 Copilot**. At general availability, Cowork runs on Anthropic's frontier models — **Opus 4.8** and **Sonnet 4.6**. Microsoft's own fine-tuned model, **Cowork 1**, was post-trained for substantially lower cost and is releasing shortly after GA.

Microsoft's positioning here is deliberate and, frankly, sensible: *your work is not limited by one brand of models.* Copilot hosts the best innovation from across the industry and chooses the right model for the job regardless of who built it. A lightweight formatting task does not need a frontier reasoning model. A 40-source deep research synthesis does. Multi-model design means the platform can match the model to the task — which is a capability story and a cost story at the same time.

### 2.4 The five things that make Cowork structurally different

```{list-table} Microsoft's five differentiators for Cowork
:header-rows: 1
:name: table-ch14-differentiators

* - Differentiator
  - What it actually means
  - Why it matters at the City of Bowie
* - **Cloud hosting**
  - Runs in a protected, sandboxed cloud environment. Files aren't stored locally. **Tasks keep running even when your laptop is off.**
  - City employees work in the field, at public meetings, and across multiple facilities. Work that requires a running laptop is work that stops at the site gate.
* - **Native Work IQ support**
  - Grounds every task in the systems your organization already runs on — email, files, meetings, chats, SharePoint
  - A project closeout task that can actually see the project's document library is a different animal from one that can't
* - **Enterprise-grade security and compliance**
  - Operates inside your Microsoft 365 trust boundary. Identity, permissions, and compliance policies apply by default; actions and outputs are auditable
  - The City holds sensitive resident data, attorney-client communications, and pre-decisional budget documents. The trust boundary is not optional
* - **Multi-model design**
  - Run the model a task needs; capability scales as more models become available
  - Heavy analytical work and light formatting work don't have to cost the same
* - **Lower cost**
  - Efficient runtime, model choice matched to task, billing only for what you use
  - Matters for a municipal organization operating under a fixed adopted budget
```

:::{note}
**"Protected, sandboxed cloud environment" — in plain language**

Cowork does not run on your machine. It runs in an isolated environment inside Microsoft's cloud, within your organization's tenant boundary. Two practical consequences follow:

1. **Continuity.** You can close your laptop, switch from desktop to phone, attend a public meeting, or walk a job site. The task keeps progressing.
2. **Containment.** The work happens in a controlled space with your identity, your permissions, and your organization's compliance policies applied by default. Nothing is quietly copied to a local drive.
:::

---

## 3. What Cowork Can Actually Do

Cowork's capability surface breaks into five areas. Read this section with your own week in mind — the goal is for at least three of these to trigger a "wait, I do that every project cycle" reaction.

### 3.1 Communication

Cowork can draft and send email through Outlook — new messages, replies, forwards. It can post updates in Teams channels and send direct messages in 1:1 or group chats. It can build and send HTML newsletters. It can manage an inbox: sorting into folders, deleting, responding inline. And it can prepare full stakeholder communication sets — status updates, announcements, follow-ups.

**At the City of Bowie:** the pre-project constituent notice that goes to affected residents along a road corridor; the daily status post to the project team's Teams channel; the "your permit application has been received" confirmation wave; the City Council weekly update during a major capital project.

### 3.2 Documents and files

Cowork can create Word documents, Excel workbooks, PowerPoint decks, and PDFs from scratch. It can edit and refine documents shared into the session. It can browse your entire Work IQ to pull in the content it needs. It can create SharePoint and OneDrive folders and reorganize existing files into them.

**At the City of Bowie:** the project operations manual; the constituent service guide refresh; a post-project recap deck; the workforce cost forecast workbook; a planning department spec document; the project folder structure itself, built and populated at kickoff.

### 3.3 Calendar and meetings

Cowork can schedule meetings from natural language, manage a calendar (adding, moving, resolving conflicts, declining with a reason message to the organizer), surface meeting intelligence and prep insights, and deliver a daily briefing of what's ahead.

**At the City of Bowie:** the week of a Council briefing, when a single department director has a site walkthrough, three constituent escalations, a contractor coordination meeting, and a budget review all colliding on the same afternoon.

### 3.4 Research and search

Cowork can search across the organization for documents, messages, and information; run deep research that synthesizes many sources into a comprehensive report; and browse SharePoint and OneDrive folders to select files.

**At the City of Bowie:** "What did we learn from the last time we did this type of project at this location?" — a question whose answer is currently distributed across three people's memories, a OneNote site assessment, and an email thread nobody can find.

### 3.5 Automation

Two forms, and they're the ones most people miss:

- **Scheduled prompts** — run a prompt on a schedule so recurring tasks happen automatically. *Every Monday at 6 a.m., produce the project status summary for all active capital projects in the Public Works portfolio.*
- **Event-driven tasks** — run when something happens. *When a constituent inquiry email arrives in the Constituent Services shared inbox, extract the request, classify it, and post it to the appropriate department channel.*

:::{tip}
**The scheduled-prompt discipline**

The single highest-return Cowork habit is this: any time you finish a Cowork task and think *"I'll need this again next project cycle,"* stop and convert it into a scheduled prompt or save the prompt text into your department's SharePoint prompt library. The prompt you spent twenty minutes perfecting is an asset. Treat it like one.
:::

---

## 4. The Session Experience — What It's Actually Like to Use

A Cowork session has a rhythm, and knowing it removes most of the first-week friction.

**Step 1 — Describe your task.** You type or dictate the outcome you want. The input field accepts up to **250,000 characters**, so you are not constrained to a one-liner — paste the whole project brief if that's what's useful. You can drag files directly into the chat, use **Add work context** to attach specific files, people, emails, Teams chats, channels, or meetings, upload from your device, or attach cloud files from OneDrive, SharePoint, or Teams.

There is a **microphone button** for voice input. This is not a gimmick for City of Bowie employees. Dictating a task while walking a job site or attending a community meeting, hands full, is a materially different experience from typing it.

The home page offers suggested prompts — *Catch me up, Organize my inbox, Organize my week, Prep for a meeting, Plan an event, Prepare for my 1:1, Research a topic* — and lists your recent tasks so you can resume any previous session.

**Step 2 — Watch Cowork work.** Cowork breaks the request into steps and works through them one at a time, visibly. You see a thinking indicator, step-by-step status updates ("Searching OneDrive," "Composing your email"), responses streaming word by word, and interactive cards. Active skills appear in the side panel as they load. A connection status indicator shows Connecting / Connected / Reconnecting / Failed, with a Retry option.

**Step 3 — Steer, interrupt, or queue.** You can send another message while Cowork is busy. Queued messages are processed in order, and Cowork adjusts direction if what you send changes the plan. You can pause at any point to add context or correct a wrong assumption. Cowork will also ask you clarifying questions — often with multiple-choice options — and you can **Skip** them if the answer doesn't matter to you.

**Step 4 — Approve actions when asked.** Cowork pauses before consequential actions. This is important enough to have its own section (§7).

**Step 5 — Review the results.** Download the documents, check what was sent, and request changes in the same session.

:::{tip}
**Queued messages are the delegation superpower**

Most people discover this late. You do not have to wait for Cowork to finish before adding context. If you're two minutes into a closeout task and remember that the labor logs for Phase 2 were filed under the wrong project code, just say so. Cowork picks it up in order and adapts.

This is exactly how you'd correct a field supervisor mid-project. The interaction model is the same because the relationship is the same.
:::

---

## 5. Skills and Plugins — How Cowork Gets Specialized

Cowork loads specialized **skills** as it works. You don't invoke them by name; Cowork selects them based on what the task needs, and the active ones appear in the side panel so you can see what it's using.

```{list-table} Built-in Cowork skills
:header-rows: 1
:name: table-ch14-skills

* - Skill
  - What it handles
  - A City of Bowie use
* - **Word**
  - Creating and editing documents
  - Project operations plan, site assessment writeup, grant narrative
* - **Excel**
  - Building and analyzing workbooks
  - Workforce cost forecast vs. actual, contractor cost analysis, grant compliance tracking
* - **PowerPoint**
  - Building decks
  - City Council briefing, department quarterly review, community meeting presentation
* - **PDF**
  - Reading and producing PDFs
  - Constituent service guides, permit documentation, regulatory rule sets
* - **Email**
  - Drafting, replying, forwarding, inbox management
  - Constituent notices, department updates, escalation responses
* - **Scheduling**
  - Setting up meetings
  - Pre-project kickoff calls, site walkthroughs, Council briefings
* - **Calendar Management**
  - Moving, declining, resolving conflicts, adding focus time
  - Budget deadline calendar triage
* - **Meetings**
  - Meeting intelligence and prep
  - Council pre-briefing prep packets
* - **Daily Briefing**
  - What's ahead today
  - Morning briefing for a department director on a project deadline day
* - **Enterprise Search**
  - Finding content across the organization
  - "What did we do at this project site before?"
* - **Communications**
  - Structured stakeholder comms
  - Multi-audience project announcements
* - **Deep Research**
  - Multi-source synthesis into comprehensive reports
  - Competitive analysis for a grant application or procurement RFP
* - **Adaptive Cards**
  - Interactive cards in Teams
  - Approval and status cards in a project channel
```

**Custom skills.** You can create up to **50**. Cowork discovers them automatically at the start of each session. For the City of Bowie, the obvious candidates are the things that are specific to how *this* city works: the standard project closeout format, the expenditure target compliance calculation, the constituent service guide house style, the grant application narrative template, the sustainability metrics data schema.

:::{note}
**The 50-custom-skill budget is a governance decision, not a technical one**

Fifty is more than enough — if the skills are chosen deliberately. It is not nearly enough if every department builds their own slightly different version of "project closeout summary." Somebody at the City should own that list the way somebody owns the standard project document template library. The skills that deserve a slot are the ones that encode *how Bowie does it*, not the ones that encode how one person prefers it.
:::

---

## 6. The Five-Part Cowork Prompt — The Core Skill of This Chapter

Here is the honest truth about Cowork: **most disappointing results are scoping failures, not capability failures.**

"Clean up my calendar" leaves almost everything open to interpretation. Cowork has to guess what you value, and guessing shapes the result. The same request, scoped properly, produces something you'd actually ship.

Microsoft's official guidance gives a five-part structure. Learn it, use it every time, and your success rate with Cowork changes immediately.

```{list-table} The five-part Cowork prompt structure
:header-rows: 1
:name: table-ch14-five-part

* - Part
  - What it answers
  - What it looks like
* - **1. Outcome**
  - What does *done* look like, in one sentence?
  - "A project closeout package for the Route 197 Rehabilitation that the Public Works Director can present before the Council briefing."
* - **2. Inputs**
  - Which specific people, files, sites, or time ranges should this use?
  - "The Route 197 project SharePoint library, the on-site workforce logs, the contractor invoice workbook, and my email thread with the department director since March 1."
* - **3. Definition of done**
  - What is the concrete deliverable, and where does it live?
  - "An Excel workbook and a two-page Word summary saved to the Route 197 library, plus a draft email to the director."
* - **4. Constraints**
  - What must be avoided or honored?
  - "Use the FY27 project closeout template. Do not contact contractors directly. Keep the summary under two pages. Flag variances over 8% rather than explaining them."
* - **5. Approval scope**
  - Which actions do you want to review explicitly, beyond the default checkpoints?
  - "Ask me before sending anything external. You can create and save files without asking."
```

**The before-and-after that makes this click:**

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Help me prep for the department offsite next week.
```

Cowork will do *something*. It will probably be generic, probably include content you didn't want, and probably miss the one thing that mattered. You'll conclude Cowork "isn't that good."
::::
::::{tab-item} ✅ Properly scoped
```
Outcome: A briefing pack and a draft agenda for the department 
offsite on June 12.

Inputs: The offsite calendar invite, the three pre-reads I've 
attached, and the notes from our last two leadership syncs.

Definition of done: One Word briefing document and one draft 
agenda, both saved to the Department Leadership folder in SharePoint.

Constraints: Keep the briefing to four pages. Use our standard 
agenda format. Do not include budget figures — those come from 
Finance separately.

Approval scope: Don't send anything to attendees. Just save 
the files and tell me when they're ready.
```
::::
:::::

:::{important}
**Why "Approval scope" is the part people skip — and shouldn't**

Parts 1 through 4 are about getting good output. Part 5 is about not being surprised.

Approval scope is where you tell Cowork the difference between actions you're comfortable with (creating a file, building a workbook, scheduling internal prep time) and actions that carry consequence (emailing a constituent, posting in a public-facing Teams channel, declining a Council meeting on someone's behalf).

Set it explicitly at the front of every task and you will almost never find yourself hitting Cancel in a hurry. Skip it and you're relying entirely on Cowork's defaults to match your judgment about what's sensitive at a public agency. They usually will. "Usually" is not a standard we apply to constituent-facing communication.
:::

:::{tip}
**A pocket version you can actually remember in the field**

**O-I-D-C-A.** Outcome. Inputs. Done. Constraints. Approvals.

Say it out loud into the microphone button in that order and you've written a good Cowork prompt without typing a word.
:::

---

## 7. Approvals and Control — The Governance Heart of Cowork

If you read only one section of this chapter twice, make it this one.

Cowork can send email. It can post in Teams. It can update records and move files and decline meetings. That capability is the whole point — and it is also the reason the approval model exists and the reason you need to understand it properly rather than click through it.

### 7.1 The approval dialog

Before a sensitive action, Cowork pauses and shows you what it intends to do. For many actions you get a **rich preview** — the actual draft email, the actual Teams message, the actual meeting invite. For others you get a summary. Medium and high risk actions carry a **risk level indicator**.

You then have four choices.

```{list-table} Your four options at an approval prompt
:header-rows: 1
:name: table-ch14-approvals

* - Option
  - What it does
  - When to use it at the City of Bowie
* - **Action button** (Send / Post / Create)
  - Proceeds with this one action, this one time
  - Your default. Every external communication. Anything a resident or Council member will see.
* - **More options** dropdown
  - Approves and skips prompts for *similar* actions for the rest of the session. For email and Teams you can scope it: **Only to** a specific recipient, **Only to** recipients at a domain, or **Always allow** for the session. Other action types get a single "Approve & don't ask again."
  - The scoped versions are genuinely useful — "only to @cityofbowie.org" during an internal-only task means you stop being interrupted for internal posts while still being stopped cold before anything leaves the organization.
* - **Approve All**
  - Approves all pending approvals at once. The button shows the count, e.g. **Approve All (3)**
  - Only when you have actually read all three. See the warning below.
* - **Cancel**
  - Stops that action. Cowork skips it and continues with the rest of the request.
  - Use freely. Cancelling one action does not kill the task — this is a lower-cost button than people assume.
```

### 7.2 The permission model — the part that should give you confidence

**Every Cowork task runs with your permissions and sees only what you can see.**

That sentence deserves to be read slowly. Cowork does not have a privileged view of city data. It is not an administrator. If you cannot open a SharePoint site, Cowork cannot open it on your behalf. If an attorney-client privileged document folder is restricted to the City Attorney's team, Cowork working for someone outside that team cannot read it.

Data stays in your tenant. Existing user and admin permissions are respected. Identity and compliance policies apply by default. And **Cowork actions are auditable** — there is a record of what was done, when, and on whose behalf.

This is architecture, not policy language. It's the same principle that governs Microsoft 365 Copilot generally, extended to a tool that can now *act* rather than only *answer*.

### 7.3 Where this meets the City's values

The City of Bowie's values are not decoration in this chapter. All four map directly onto the approval model and the idea of responsible delegation.

```{list-table} The approval model through the City of Bowie values lens
:header-rows: 1
:name: table-ch14-values

* - Value
  - What it means here
* - **Accountability** — *we are answerable for our decisions and actions*
  - Accountability is earned through verification, not assumed through convenience. **Verify before you approve.** Read the recipient list. Read the actual draft, not the summary of the draft. Accountability in a tool means trusting it to do what you told it to — which requires checking that you told it the right thing.
* - **Responsiveness** — *we listen and act on the needs of our community*
  - **You own every output that carries your name.** If Cowork drafts a constituent communication and you approve it, that communication is yours. It is not "the AI's" letter. There is no version of this where the tool absorbs the accountability. A resident who receives wrong information does not care which software produced it.
* - **Stewardship** — *we responsibly manage the resources entrusted to us*
  - Cowork can decline a meeting on your behalf with a reason message. It cannot read the room. Some declines need a human phone call, and knowing which ones is your job, not the model's. Public funds and public trust are managed by people, not software.
* - **Pride** — *we take pride in our city and in the quality of our work*
  - Cowork raises the floor — nothing you ship should be rougher than it used to be. Humans raise the ceiling. The closeout package Cowork produces in twenty minutes should free you to think about the *pattern* across the last six projects, which is where the real value to the City sits.
```

:::{warning}
**The Approve All trap — read this before your first session**

**Approve All (3)** is a convenience button. It is also the single most likely place for a City of Bowie employee to cause real damage with Cowork.

Here is the failure mode, and it is not hypothetical. You are running a task that drafts constituent notices. Cowork queues three approvals. Two are internal Teams posts. The third is an email to 500 residents containing a project timeline that changed yesterday. You hit **Approve All** because you skimmed the first two and assumed the third was the same kind of thing.

That email cannot be recalled from 500 inboxes. The Council will hear about it before you do.

**The rule for the City of Bowie: never use Approve All on a batch that contains any externally-facing action.** If the queue has an email to a resident, a contractor, a Council member, or a regional agency in it, approve items one at a time and read each preview in full. Approve All is for batches of internal, low-consequence, obviously-identical actions — and even then, glance at the count and make sure it matches what you expect.

Reflexive approval is not delegation. It is abdication.
:::

:::{note}
**Microsoft's own guidance, verbatim in spirit**

*Always review details before approving — check recipients, content, and other details.*

Note the word order. Recipients first. At a city agency where you may communicate with residents, contractors, partner agencies, and elected officials in the same task, the recipient list is the highest-risk field on the screen.
:::

### 7.4 Auditability as an operational asset

It's easy to read "actions are auditable" as a compliance checkbox. At the City of Bowie it's more useful than that.

An audit trail means that when a resident asks "when did you notify us about the construction schedule change?", the answer is retrievable. It means that when a project team hands off from pre-construction to active construction crew, the record of what was communicated and when is intact. It means a post-project dispute about what a contractor was told has evidence behind it rather than three conflicting recollections.

Delegation without a record is risk. Delegation with a record is process.

---

## 8. Economics and Governance — What Cowork Costs and How to Think About It

Cowork is not free, and pretending otherwise makes it harder to adopt well.

### 8.1 The licensing structure

- The **Microsoft 365 Copilot User Subscription License (USL)** is a **prerequisite**. Cowork sits on top of it.
- Cowork itself is billed on **usage**, denominated in **Copilot Credits**.

The USL separately includes Copilot Chat; Copilot in Word, Excel, PowerPoint, Outlook, and Teams; the Work IQ context engine; multi-model frontier intelligence; the pre-built agents (Researcher, Analyst); and custom agents via Agent Builder. Cowork is the delegation layer added on top of all of that.

### 8.2 The four cost inputs

The price of a Cowork task is calculated from four things:

```{list-table} What drives the cost of a Cowork task
:header-rows: 1
:name: table-ch14-cost-inputs

* - Input
  - What increases it
  - How to control it
* - **Model use**
  - Deeper reasoning, more complex synthesis
  - Don't send a formatting job to a frontier model. Multi-model design exists so you can match the model to the job
* - **Context retrieval**
  - The more sources Cowork has to search, the more it costs
  - Point at specific libraries and date ranges instead of "search everything." This is the *Inputs* line of your five-part prompt earning its keep
* - **Tool calls**
  - Every app action — creating a file, sending an email, reading a workbook
  - Ask for the deliverables you need, not every deliverable you can imagine
* - **Runtime**
  - How long the task runs
  - Tighter scope, fewer clarification loops, fewer mid-task corrections
```

Notice that three of the four are directly controlled by prompt quality. **A well-scoped prompt is a cost-control mechanism**, not just a quality mechanism. That is not a coincidence and it's worth saying to anyone at the City who has to justify the technology budget.

### 8.3 Light, medium, heavy

Microsoft observes three task patterns in practice:

```{list-table} Cowork task patterns
:header-rows: 1
:name: table-ch14-task-patterns

* - Pattern
  - Profile
  - City of Bowie example
* - **Light**
  - Small number of knowledge sources, limited reasoning, one output or fewer
  - "Organize my inbox into project folders for the three active capital projects I'm managing this month."
* - **Medium**
  - Multiple sources, structured reasoning, two or more outputs
  - "Build the project schedule and the contractor coordination document for the Millstream Road project from the engineering plan and our workforce forecast."
* - **Heavy**
  - Aggregates broadly, deep reasoning, many outputs
  - "Analyze contractor and workforce cost variance across all 14 Public Works projects in the last 18 months and produce the workbook, the narrative analysis, and the Council-ready deck."
```

Microsoft also identified **four user personas** with distinct usage patterns, and publishes a customer estimator spreadsheet at **aka.ms/CustomerCoworkEstimator** (its figures assume Anthropic Opus 4.8). The underlying cost model is straightforward:

> (users per segment) × (expected prompt volume across light / medium / heavy) × (cost per prompt type), summed across segments.

Microsoft's own testing reports that Copilot Cowork averaged **30–40% cheaper per prompt** than Claude Cowork operating through its Microsoft 365 connector — a consequence of efficient runtime and matched model selection.

### 8.4 What this means for municipal budget planning

If everyone at the City ran three heavy tasks a day because heavy tasks are fun to watch, the bill would be real. If nobody used Cowork because they were unsure about credits, the opportunity cost — in staff hours spent on mechanical assembly work — would be larger. Neither extreme is the answer.

Here is a practical rule of thumb for the City of Bowie.

:::{tip}
**When is a Cowork task worth the credits?**

Ask two questions:

1. **How long would this take me?** If the honest answer is under fifteen minutes and it's one app, use **Chat**. Cowork's overhead — planning, retrieval, tool calls — isn't worth it for a task you can finish in a Word window.
2. **Does it produce something I'd otherwise not do at all?** This is the important one. The post-project cross-department pattern analysis that nobody has time for. The project history summary that lives in three people's heads. The grant compliance review that gets skipped during a busy construction season. These are the highest-value Cowork tasks precisely *because* they currently don't happen.

The worst use of credits is asking Cowork to do a five-minute job. The best use is asking Cowork to do the four-hour job you keep postponing.
:::

Governance guidance for City of Bowie managers deploying this:

- **Give teams a monthly credit budget and visibility into it.** People manage what they can see.
- **Build a shared prompt library.** A well-scoped prompt costs less and produces more. Reusing a good one is free efficiency.
- **Convert the repeated heavy tasks into scheduled prompts.** A weekly scheduled task with a tight scope costs less than six people improvising the same analysis.
- **Watch for the "just re-run it" habit.** Re-running a whole heavy task because one number was wrong is expensive. Steering mid-task, or asking for a targeted correction in the same session, is cheaper.

---

## 9. Microsoft's Four Flagship Scenarios, Translated to City of Bowie

Microsoft leads with four demonstration scenarios. Each has a direct City of Bowie analogue, and walking the translation is a fast way to see the shape of what Cowork does.

### 9.1 "Clean up your calendar" → Project deadline calendar triage

**What Microsoft shows:** Cowork reviews your Outlook schedule, asks what you're prioritizing, flags conflicts and low-value meetings, and proposes changes. On approval it accepts, declines, or reschedules meetings and adds focus blocks. It can also send a prep document for a meeting.

**The City of Bowie analogue:** It is the Tuesday before a grant deadline. A project manager has a site walkthrough, two internal coordination syncs, a contractor meeting, and a Council committee hearing — three of which overlap with time they physically need for grant document assembly.

> **Outcome:** A project-deadline week calendar that protects Wednesday 7 a.m.–1 p.m. and Thursday 7 a.m.–noon for focused grant submission work.
> **Inputs:** My Outlook calendar for June 8–12; the project milestone schedule for the Whitemarsh Park renovation.
> **Definition of done:** Conflicts resolved, focus blocks added, declines sent with a reason.
> **Constraints:** Never move or decline anything with the Council member or department director on it — flag those for me instead. Internal coordination meetings can be moved freely.
> **Approval scope:** Ask before any decline that goes to someone outside the City.

### 9.2 "Build the meeting packet and align the team" → The Council briefing prep packet

**What Microsoft shows:** Cowork pulls inputs from email, meetings, and files; schedules prep time; and produces a connected set of deliverables — a briefing document, supporting analysis, and a presentation, all saved in Microsoft 365 — plus a draft summary email with the latest files attached.

**The City of Bowie analogue:** The quarterly project status briefing for City Council, ninety days into the capital project cycle. Currently assembled by three people across a week from project reports, a budget workbook, the prior quarter's post-project report, and an email thread.

The Cowork version produces the briefing doc, the supporting analysis workbook, the Council-ready deck, a scheduled internal prep session the day before, and a draft email to the City Clerk with the deck attached — waiting for approval.

### 9.3 "Research a company fast" → Grant opportunity and regulatory intelligence

**What Microsoft shows:** Cowork gathers source documents, organizes findings with citations, and returns an executive summary, a structured research memo, and an Excel workbook with labeled tabs.

**The City of Bowie analogue:** The Grants Coordinator needs to evaluate a new federal infrastructure grant program. They need to know the program's eligibility requirements, funding history, application timeline, what Prince George's County or comparable municipalities have received before, and what the City's competitive positioning looks like.

Same three artifacts: an email-ready executive summary, a cited research memo with assumptions stated plainly, and a workbook with tabs for program eligibility, funding history, comparable applicant profiles, and required match ratios.

### 9.4 "Create the launch plan" → New city program or service rollout

**What Microsoft shows:** Cowork builds a competitive comparison in Excel, distills differentiation into a value proposition document, generates a pitch deck, and outlines milestones, owners, and next steps.

**The City of Bowie analogue:** Launching a new constituent services digital submission portal — the comparison against how comparable Prince George's County cities handle permits, the value proposition document that department heads can use to build internal buy-in, the resident-facing introduction materials, and the rollout milestone plan with owners across IT, Finance, and Constituent Services.

---

## 10. Nine City of Bowie Scenarios, Worked in Full

This is the practical heart of the chapter. Each scenario names the persona, the trigger, the badly-scoped prompt most people would write first, the properly structured five-part version, what Cowork does step by step, where it pauses, and what comes back.

Read the ones closest to your role carefully. Skim the rest — the patterns transfer.

---

### Scenario 1 — Project closeout reconciliation package

**Persona:** Project Manager, Public Works
**Trigger:** Construction wrapped up last night. The Public Works Director wants a preliminary closeout before their Council briefing in 36 hours. You have a site inspection in four hours.

:::::{tab-set}
::::{tab-item} ❌ What most people write first
```
Do the project closeout for the project that just finished.
```
Cowork doesn't know which project, which files, what format, what "closeout" includes at the City, or whether it may email the director. Best case it asks five clarifying questions you're not around to answer. Worst case it guesses.
::::
::::{tab-item} ✅ The five-part version
```
Outcome: A preliminary project closeout package for the Millstream 
Road Rehabilitation that the Public Works Director can present 
before the Council briefing on Thursday morning.

Inputs: The Millstream Road project SharePoint library — specifically 
the on-site workforce logs, the contractor invoice and budget workbook, 
the change order log, and the original project cost estimate. Also 
my email thread with the department director since March 1.

Definition of done: (1) An Excel workbook with tabs for workforce 
forecast vs. actual, contractor expenditure vs. budget targets, and 
change order variances. (2) A two-page Word summary written for the 
director, not for internal project accounting. (3) A draft email to 
the director with both files attached. Save all files to the 
Millstream Road library under /Project-Closeout.

Constraints: Use the FY27 project closeout template. Flag any 
variance over 8% in a callout list rather than explaining it — 
I'll add the narrative. Do not contact any contractors. Do not 
include internal margin or overhead allocation figures anywhere 
in the director-facing summary.

Approval scope: Create and save the files without asking. Ask 
me before sending anything to the director.
```
::::
:::::

**What Cowork does:** Locates the Millstream Road library → opens the workforce logs and forecast → builds the variance analysis → opens the contractor invoice workbook and computes expenditures against the agreed budget targets → reads the change order log and reconciles approved changes against actuals → builds the workbook on the FY27 template → writes the two-page summary in director-appropriate language → drafts the email.

**Where it pauses:** At the email to the director. You get a rich preview showing recipient, subject, body, and the two attachments.

**What comes back:** A closeout workbook, a two-page director-ready summary, and an email sitting in draft — reviewed on your phone at the job site, approved after you check the variance callouts and confirm no overhead figures leaked into the summary.

---

### Scenario 2 — Capital project planning

**Persona:** Public Works Operations Manager
**Trigger:** A 2.4-mile road corridor rehabilitation with tight contractor sequencing and grant-mandated milestones. Construction starts in eleven days.

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Plan the construction schedule for the big road project next month.
```
::::
::::{tab-item} ✅ Five-part
```
Outcome: A construction and inspection plan for the Route 197 
Corridor Rehabilitation that the field crew leads and the 
contractor superintendent can work from directly.

Inputs: The approved engineering plan, the contractor mobilization 
schedule, our workforce forecast workbook, the grant milestone 
deadlines, and last year's post-project report for the adjacent 
Collington Road project.

Definition of done: (1) A Word operations plan with a week-by-week 
construction sequence by project phase, crew assignments, and 
inspection milestones. (2) An Excel schedule showing contractor 
mobilization windows against City inspection capacity by week. 
(3) A one-page crew coordination brief for the field leads. All 
saved to the Route 197 project library.

Constraints: Respect the grant milestone deadlines — they are 
contractual requirements, not suggestions. Assume the contractor 
mobilization requires 5 days of advance notice. Flag any week 
where inspection demand exceeds City staff capacity rather than 
smoothing it silently.

Approval scope: Files only. Do not post anything to the project 
Teams channel or email the contractor — I'll circulate it myself.
```
::::
:::::

**What Cowork does:** Reads the engineering plan and phase breakdown → maps the contractor schedule against grant milestones → pulls the workforce forecast and allocates inspection staff by phase → models contractor mobilization windows against City inspection capacity week by week → surfaces documented problems from the adjacent project post-report and checks whether the new plan repeats them → produces the three artifacts.

**Where it pauses:** Nowhere externally — you scoped it to files only. It may ask one clarifying question about inspection crew shift scheduling.

**What comes back:** A plan, a capacity schedule with over-demand weeks flagged in red, and a crew brief. Your job is now the interesting part: deciding what to do about the three flagged weeks in months three and four.

---

### Scenario 3 — Facility and site assessment writeup

**Persona:** Parks & Recreation Project Lead
**Trigger:** You just walked a new park facility site for four hours. You have 60 photos, a OneNote page of scrawled notes, and a voice memo.

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Write up my site assessment.
```
::::
::::{tab-item} ✅ Five-part
```
Outcome: A facility site assessment document for [Facility Name] 
that a project manager who has never been there could plan a 
renovation from.

Inputs: My OneNote site assessment page from yesterday, the 
photos in my OneDrive /Site Assessments/[Facility] folder, and 
the facility's maintenance history PDF I've attached.

Definition of done: A Word document saved to the Parks & 
Recreation Project Library in SharePoint, following our standard 
assessment structure: access and parking, building systems and 
utilities, ADA compliance observations, safety and code notes, 
landscaping and grounds, known constraints, and open questions 
requiring follow-up.

Constraints: Keep every observed fact separate from every 
inference — put anything you inferred rather than observed under 
a clearly labeled "To verify" heading. Do not fill gaps with 
assumptions from other facilities.

Approval scope: Files only.
```
::::
:::::

**Where it pauses:** File creation in a shared library may prompt for confirmation depending on your admin's configuration.

**What comes back:** A structured assessment document — and, critically, an explicit "To verify" list that tells you exactly what you failed to capture while you were there. That list is worth more than the document.

---

### Scenario 4 — Design brief to spec document to Council presentation deck

**Persona:** Planning and Parks Coordinator
**Trigger:** A community stakeholder group has approved a concept direction for a new community recreation space. You need a spec document for the engineer and a presentation deck for the City Council, and the Council meeting is Friday.

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Turn my design brief into a deck for the Council.
```
Cowork produces a deck. It will look fine. It will also not know the site's actual grading constraints, the engineering team's spec format, or that this project involves a federally funded parkland conversion requiring a public notice period.
::::
::::{tab-item} ✅ Five-part
```
Outcome: An engineering-ready spec document and a Council-ready 
presentation deck for the Whitemarsh Community Park Phase 2 
expansion, both consistent with the approved concept brief.

Inputs: The approved community concept brief, my stakeholder 
meeting notes in OneNote, the site survey and grading plan, 
the ADA and accessibility requirements from the Parks standards 
document, and our standard project spec template.

Definition of done: (1) A Word spec document following the 
City spec template — site layout, utilities, landscaping, 
accessibility features, lighting, phasing, construction 
assumptions, and open engineering questions. (2) A PowerPoint 
Council presentation of 10–12 slides using our Council 
presentation template: project background, community input 
summary, proposed design highlights, phasing and timeline, 
budget overview, and requested action. Both saved to the 
Whitemarsh Phase 2 project folder.

Constraints: The design must comply with ADA accessibility 
requirements and the Parks Department facility standards. Do 
not include any cost estimates that haven't been reviewed by 
Finance — use "[Pending Finance Review]" as a placeholder. Do 
not include design elements the community explicitly rejected 
in the engagement process.

Approval scope: Files only. Nothing goes to Council from 
Cowork — the director reviews before anything is submitted.
```
::::
:::::

**What Cowork does:** Reads the brief and stakeholder notes → extracts design intent → checks it against the site survey constraints and ADA requirements → produces the spec document flagging where the brief is silent (which is exactly where engineering will push back) → builds the Council deck on the City template → saves both.

**What comes back:** A spec doc with an explicit list of unresolved engineering questions, and a Council deck at roughly the 80% mark — which is the right handoff point. The design judgment, the community story, and the moment that makes Council say yes are still yours.

---

### Scenario 5 — Grant application preparation

**Persona:** Grants Coordinator, City Administration
**Trigger:** A federal infrastructure grant program has issued a Notice of Funding Availability. Application due in nine days. It's a 40-page application package with detailed requirements.

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Write our response to this grant application.
```
::::
::::{tab-item} ✅ Five-part
```
Outcome: A complete first-draft grant application for the 
[Program Name] federal infrastructure grant that our grants 
team can edit rather than write.

Inputs: The NOFA PDF I've attached; our three most recent 
successful grant applications in the Grants library; the City 
project capability statement; the relevant project data from 
the Capital Improvement Program; and the community needs 
documentation from the last Comprehensive Plan update.

Definition of done: (1) A Word application document structured 
section by section in the NOFA's own order, with every 
requirement addressed and cross-referenced to the NOFA 
section number. (2) An Excel compliance matrix listing every 
stated requirement, our response status, and the staff member 
who needs to confirm it. (3) A short internal memo listing 
the five weakest sections and what evidence we'd need to 
strengthen them. All saved to the [Program Name] Grant folder.

Constraints: Do not invent any metric, prior grant award, or 
case study — if the source material doesn't support a claim, 
write "[EVIDENCE NEEDED]" and move on. Do not commit to any 
match funding amounts without Finance sign-off. Use the 
federal program's own terminology from the NOFA, not our 
internal project names.

Approval scope: Files only. Nothing external.
```
::::
:::::

**What Cowork does:** Parses the NOFA into a structured requirement list → searches the grants library for the strongest matching narrative language → drafts each section in NOFA order → builds the compliance matrix → runs a self-critique pass to identify weak sections → produces the internal memo.

**What comes back:** Nine days of application work reduced to about two, plus a compliance matrix that stops the classic failure mode of a grant application that reads well and misses requirement 4.7.3.

---

### Scenario 6 — Stalled budget memo and follow-up pipeline

**Persona:** Budget Analyst, Finance Department
**Trigger:** Fiscal year-end is three weeks out. Several interdepartmental budget requests and approval memos have gone quiet. You don't know which ones or why.

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Which of my budget memos are stalled?
```
::::
::::{tab-item} ✅ Five-part
```
Outcome: A ranked view of my at-risk budget memos and 
interdepartmental requests with the specific follow-up that 
went cold on each, plus a fiscal year-end readiness summary.

Inputs: My Outlook mail and calendar for the last 90 days; 
the budget request files in my Budget SharePoint folder; 
the budget tracking workbook; and the Finance deadline 
calendar.

Definition of done: (1) An Excel workbook ranking open 
budget requests by risk, with columns for last meaningful 
response, days since, the specific commitment or follow-up 
that lapsed, and the recommended next action. (2) A 
fiscal year-end readiness summary on our standard format 
covering completion status, at-risk items, and the 
resolution plan. (3) Draft follow-up emails for the top 
five at-risk requests — drafts only, in my Drafts folder.

Constraints: "Stalled" means no substantive two-way exchange 
in 14 days — an out-of-office auto-reply does not count as 
contact. Do not send anything. Do not include any item where 
the department has explicitly notified us of a withdrawal; 
list those separately.

Approval scope: Ask before creating anything in my Drafts 
folder. Never send.
```
::::
:::::

**What comes back:** A ranked list of at-risk budget requests with the exact follow-up that went cold on each — collapsing weeks of inbox archaeology into a single morning. The value is not the ranking. It is the "specific commitment that lapsed" column. *You told the Parks Department you would send the revised appropriation schedule on April 3. You never did.* No tracking spreadsheet captures that. Your email does.

---

### Scenario 7 — Infrastructure and contractor cost analysis across projects

**Persona:** Finance Analyst
**Trigger:** Three department directors have separately asked why infrastructure maintenance costs rose year over year. You suspect the answer differs by project type but you've never had time to prove it.

:::::{tab-set}
::::{tab-item} ❌ Under-scoped
```
Analyze our infrastructure costs.
```
::::
::::{tab-item} ✅ Five-part
```
Outcome: An analysis of contractor and maintenance cost variance 
across our Public Works projects at four project categories over 
the last 18 months, with the drivers identified.

Inputs: The contractor cost and budget workbooks in the Public 
Works SharePoint library for projects PW-4180 through PW-5210; 
the budget target agreements for each project; and the workforce 
time logs.

Definition of done: (1) An Excel workbook with a tab per project 
category plus a consolidated comparison — cost per deliverable 
unit, percentage of workforce hours in overtime vs. straight 
time, and budget target compliance rate. (2) A Word analysis 
of the top three cost drivers with evidence for each. (3) A 
six-slide deck I can use in a department director conversation.

Constraints: Normalize for project scale using total contracted 
scope units — absolute cost comparisons across projects of 
different sizes are meaningless. Exclude the two projects with 
incomplete documentation and note the exclusion. Do not include 
any department's budget figures in a deliverable that another 
department will see — build the deck with indexed figures, not 
absolute amounts.

Approval scope: Files only.
```
::::
:::::

**What Cowork does:** Opens each project's cost workbook → normalizes by contracted scope units → computes cost per deliverable unit and budget target compliance by project category → cross-references workforce logs to establish overtime share → identifies correlation between project timeline compression and cost overage → writes the analysis → builds the indexed deck.

**Where it pauses:** File creation. That confidentiality constraint — indexed figures rather than absolute amounts — is a City-specific instruction that Cowork would never infer on its own. This is exactly what the Constraints line exists for.

**What comes back:** The analysis nobody had time to run, with the answer to a question three directors asked. This is a heavy task. It is unambiguously worth the credits.

---

### Scenario 8 — Constituent service guide refresh and inquiry triage

**Persona:** Constituent Services Manager
**Trigger:** Two things at once. The resident services guide for permit and licensing season needs updating across 40 pages of deadlines, fees, and process steps. And the shared inquiry inbox is taking 200+ constituent questions a day during peak permit season.

**Task A — the service guide:**

```
Outcome: An updated resident services guide for permit season 
reflecting the new fee schedule, revised processing timelines, 
and updated submission requirements.

Inputs: Last year's resident services guide PDF; the FY27 fee 
schedule; the updated permit processing procedures document; 
and the current program calendar with all relevant deadlines.

Definition of done: An updated Word document saved to the 
Constituent Services library, plus a one-page change summary 
listing every change made and its source.

Constraints: Do not change any section where the source 
documents don't show a change — preserve existing wording 
exactly. Every deadline date must trace to the program 
calendar; flag any date you cannot verify rather than 
carrying it forward.

Approval scope: Files only.
```

The change summary is the whole point. It turns an unreviewable 40-page diff into a one-page review.

**Task B — the inquiry triage (an event-driven, scheduled pattern):**

```
Outcome: A daily triage of the Constituent Services shared 
inbox so my team starts each morning with a prioritized 
queue instead of an undifferentiated pile.

Inputs: The Constituent Services shared mailbox, 
previous 24 hours.

Definition of done: A Teams post to the Constituent Services 
channel each morning at 7:00 a.m., grouping inquiries into: 
(1) deadline-critical — anything about permit expiration, 
fee payment cutoffs, or hearing dates; (2) applications and 
fees; (3) process and eligibility; (4) answerable from the 
service guide — with the relevant section cited. Include a 
count per category and name the five most urgent.

Constraints: Do not reply to any constituent. Categorize only. 
Do not include constituent personal information in the Teams 
post.

Approval scope: Ask before the first post. Then only to 
the Constituent Services channel for the rest of the season.
```

Note the approval scoping in the last line — this is precisely what the **More options → Only to** feature is for. You approve once, scope it to one internal channel, and stop being interrupted, while everything external still stops for review.

---

### Scenario 9 — Program enrollment analysis and sustainability reporting

**Persona A:** Grants and Programs Coordinator
**Trigger:** A federally funded parks program enrollment is at 61% with six weeks to the grant compliance deadline. The Finance Director wants to know whether to request a deadline extension.

```
Outcome: A program enrollment analysis for [Program Name] 
with a recommendation on whether to request a compliance 
extension, in a format I can share with the Finance Director.

Inputs: The enrollment reports in the Programs library for 
this program for the last three grant years; the current 
grant compliance terms; and the current-year enrollment 
data by location and participant category.

Definition of done: (1) An Excel workbook comparing this 
year's enrollment curve against the prior three years at 
the equivalent weeks-to-deadline, by location and participant 
type. (2) A two-page Word recommendation with the compliance 
shortfall risk quantified. (3) A draft email to the Finance 
Director.

Constraints: Compare at equivalent weeks-to-deadline, not 
calendar dates — the program start shifted three weeks this 
year. Quantify compliance risk using the actual grant terms, 
not a blended assumption. Do not recommend requesting an 
extension if the grant terms make extension requests 
subject to additional restrictions.

Approval scope: Ask before the Finance Director email. 
Files freely.
```

**Persona B:** Sustainability Coordinator
**Trigger:** The annual sustainability report and the City's environmental commitment update need current-period metrics compiled from facilities, fleet, and program-level sources across all departments.

```
Outcome: A compiled sustainability metrics dataset and draft 
narrative section for the FY27 City Sustainability Report 
covering our reporting scope.

Inputs: The facility utility data workbooks for all city 
buildings; the fleet fuel and emissions data in the Public 
Works library; the program-level sustainability metrics from 
the Parks & Recreation library; and last year's published 
sustainability report for structure and methodology continuity.

Definition of done: (1) An Excel workbook with a tab per 
data source and a consolidated summary using last year's 
methodology and units. (2) A Word draft of the sustainability 
metrics narrative section. (3) A data quality memo listing 
every gap, inconsistency, and unit mismatch found.

Constraints: Use exactly the same methodology and boundary 
definitions as last year's published report — flag any place 
where this year's source data doesn't support that methodology 
rather than substituting an alternative. Never estimate a 
missing figure; mark it as a gap.

Approval scope: Files only. Nothing leaves this session.
```

:::{important}
**The data quality memo is the real deliverable**

In both of these — and in most analytical Cowork tasks at the City of Bowie — the artifact that changes your week is not the polished output. It's the honest list of what's missing, inconsistent, or unverifiable.

Always ask for it. A constraint like *"never estimate a missing figure; mark it as a gap"* is the difference between a report you can defend and a report that looks complete because the software filled in the holes.
:::

---

## 11. Microsoft's Customer Proof Points, in City of Bowie Terms

Three reported outcomes from Microsoft's own customers translate directly.

```{list-table} What other organizations did — and the City of Bowie equivalent
:header-rows: 1
:name: table-ch14-proof-points

* - What Microsoft reports
  - The City of Bowie analogue
* - A team compared nearly **4,000 files** across two product versions — work that would have taken weeks
  - Compare this year's resident service guides, permit requirements, and project specifications across the full City program portfolio to find every place a deadline, fee, or requirement changed. Nobody does this today because nobody has weeks. It is a single Cowork task.
* - A sales lead pointed Cowork at a **stalled pipeline** and got a ranked list of at-risk opportunities with the exact follow-up that had gone cold on each — a week of review collapsed into one morning
  - Scenario 6 above. Directly transferable to the Grants Coordinator managing a portfolio of pending applications and interdepartmental budget requests, where the lapsed commitment is usually buried in an email thread rather than a tracking spreadsheet.
* - An engineering team taught Cowork to safely **edit batch-job spreadsheets and generate dependency flow charts** after every change — automating work that previously required careful manual intervention
  - The budget workbooks and project schedules that get edited by five people across a project cycle. Teach Cowork the safe-edit rules and have it regenerate the dependency view — which project phases depend on which contractor deliverables arriving in which window — after every change. This is where a **custom skill** earns its slot.
```

---

## 12. Why Cowork Fits the City of Bowie Specifically

There is a reason this chapter exists in a City of Bowie book rather than being a generic Cowork overview.

Most software productivity features assume a knowledge worker at a desk with a laptop open. That describes a minority of City of Bowie employees.

The City serves **more than 70,000 residents** across departments operating in the field, at community facilities, in public meetings, on job sites, and at City Hall. The people who most need analytical and documentation work done are frequently the people least able to sit still and do it.

The property that makes Cowork disproportionately valuable here is the least glamorous one on the feature list: **tasks keep running when your laptop is off.**

Think about what that actually unlocks:

- A project manager delegates the closeout package at 5 p.m. during final inspection, reviews it on their phone during the commute home, and approves the director email from their driveway.
- A grants coordinator starts a deep research task on a new federal program at the end of the day; comes in the next morning to a finished research memo.
- A budget analyst kicks off a cross-department expenditure analysis before a community meeting and reads the result over lunch.
- A Parks planner sets a spec document running before a stakeholder call and comes back to a draft with the engineering questions already flagged.

The quote from the top of this chapter is the mindset in one line: *"It is easy to have a dozen tasks in flight at once, each one moving forward while you focus on what only you can do."*

For a city organization where the thing only you can do is often *physically be present at a community meeting and make a judgment call*, that sentence is not a productivity slogan. It is a description of how the job could work.

:::{note}
**The multi-department dividend**

City of Bowie employees coordinate across Public Works, Finance, Planning, Parks & Recreation, HR, Public Safety Communications, and Constituent Services — often on the same project. Cloud-hosted tasks that persist across devices and sessions turn cross-departmental coordination from a scheduling burden into a natural relay. Work started at the end of one department's review cycle is finished and reviewable at the start of another's — without anyone staying late.
:::

---

## 13. Cautions — What Cowork Does Not Change

Everything above is genuine capability. This section is the counterweight, and it is not optional reading.

### 13.1 Cowork does not transfer accountability

This is the most important sentence in the chapter.

If Cowork drafts a number and you approve the email, it is your number. If Cowork produces a project closeout and the director builds a Council slide on it, that closeout is your work product. If Cowork writes a grant narrative and the grant agency funds the City on it, the narrative is yours.

There is no arrangement in which "Copilot generated it" is an acceptable answer to a resident, a Council member, or a grant auditor. **Accountability** means we are answerable for our decisions and actions. A delegated action is still your action.

### 13.2 Review before approving — properly

Skimming a preview is not reviewing it. A real review checks, in this order:

1. **Recipients.** Who is on this? Is anyone on it who shouldn't be? Is this the resident's full contact list or just my point of contact?
2. **Numbers.** Spot-check at least two figures against the source. If they're right, the method is probably right. If either is wrong, stop and re-scope.
3. **Claims.** Does anything assert something the City has not verified? Any commitment on timing, cost, or service level that hasn't been approved?
4. **Confidentiality.** Is there anything in here that belongs to a different department, a different project, or a different audience — resident vs. internal vs. Council?
5. **Tone.** Does this sound like the City of Bowie — professional, clear, community-focused — or does it sound like software?

### 13.3 Oversharing risk

Cowork can search everything you have permission to see. That's the feature. It is also the risk.

If you have broad access — many department directors and project managers do — a loosely scoped research task can pull material from one project's files into a deliverable intended for another. Cowork is not doing anything wrong; it is doing what you asked, with the access you have.

The mitigation is entirely in your hands, and it's the **Inputs** and **Constraints** lines of the five-part prompt:

- Name the specific libraries, folders, and date ranges. Don't say "search our files."
- State confidentiality boundaries explicitly. *"Only use material from the Millstream Road project library."* *"Do not reference any other department's budget figures."*
- When in doubt, run the task with narrow inputs and widen it if the result is thin. Widening is cheap. Un-sending is impossible.

:::{warning}
**Public agency confidentiality is not an abstraction**

The City of Bowie routinely manages sensitive information: pre-decisional budget documents, attorney-client communications, personnel records, law enforcement coordination data, and resident personal information. Some of this is protected by Maryland public records law and federal privacy requirements.

Before you run any task that touches sensitive city data, ask one question: *if this output were forwarded to an unintended recipient, what would be in it?* Then scope so the answer is "nothing."
:::

### 13.4 Cowork is confident about things it should be uncertain about

Like every model-driven system, Cowork produces fluent output regardless of whether the underlying source material supported it. The countermeasure is structural, not vigilance-based — build it into the prompt:

- *"Flag anything you cannot verify rather than carrying it forward."*
- *"Write [EVIDENCE NEEDED] rather than inventing a figure."*
- *"Separate observed facts from inferences under a clearly labeled heading."*
- *"Never estimate a missing figure; mark it as a gap."*

Every one of those lines appeared in a scenario above. They are not decoration. They are the difference between a deliverable you can defend and one you can't.

### 13.5 Some things should not be delegated at all

A conversation with a resident whose property was affected by a city project. A discussion with an employee about a performance concern. A negotiation with a contractor over a disputed change order. The moment when a community member needs to hear a human voice take responsibility.

**Responsiveness** — we listen and act on the needs of our community — is the value that draws this line. Cowork can prepare you for those conversations. It should never have them for you.

---

## 14. Getting Started — Your First Week with Cowork

### 14.1 Where to find it

```{list-table} How to access Copilot Cowork
:header-rows: 1
:name: table-ch14-access

* - Surface
  - Where
* - **Browser**
  - **m365.cloud.microsoft** — the same front door as the rest of Microsoft 365 Copilot
* - **Desktop / Mobile**
  - The Microsoft 365 Copilot app. The mobile app matters more at the City of Bowie than at most organizations — it's how you delegate from a job site or a community meeting
* - **Outlook and Teams**
  - Via the **toggle next to Chat**. Some versions surface it in the left navigation rail or under "All agents"
```

### 14.2 Admin enablement

Cowork is enabled by administrators in the **Microsoft 365 admin center**. If you don't see the toggle next to Chat, that is the first thing to check — it is an enablement question, not a licensing mystery. Admins also control which **plugins** are deployed org-wide, which is the right control point for anything that connects to an external data source or a system of record.

Two prerequisites, in order: the **Microsoft 365 Copilot USL**, then Cowork enablement plus a **Copilot Credits** allocation.

### 14.3 Three starter tasks for your first week

Do these in order. They're deliberately sequenced from low stakes to real work.

::::{tab-set}
:::{tab-item} Day 1 — Organize your week
```
Outcome: My calendar for next week organized so I have two 
protected two-hour blocks for focused work.

Inputs: My Outlook calendar for next week.

Definition of done: Focus blocks added; conflicts flagged 
in a summary message to me.

Constraints: Do not decline or move anything — just propose 
changes and tell me. Never touch anything with an external 
attendee, a Council member, or a community meeting.

Approval scope: Ask before any calendar change at all.
```
**Why this one first:** zero external risk, immediate visible value, and you get to see the approval dialog in a situation where mistakes cost nothing. Pay attention to the previews — that's the real lesson.
:::
:::{tab-item} Day 2–3 — Catch up on a project
```
Outcome: A one-page catch-up on everything that's happened 
on Project [X] in the last two weeks.

Inputs: My email and Teams messages related to Project [X], 
and the Project [X] SharePoint library, last 14 days only.

Definition of done: A Word document saved to my OneDrive, 
organized by: decisions made, open issues, deadlines in the 
next 21 days, and anything waiting on me.

Constraints: Only the last 14 days. Cite the source message 
or file for every item so I can go check it.

Approval scope: Files only. Do not send or post anything.
```
**Why this one second:** it teaches you Work IQ grounding and the discipline of citing sources — and the "waiting on me" section is usually a genuinely uncomfortable surprise.
:::
:::{tab-item} Day 4–5 — Produce a real artifact
Pick the scenario from §10 closest to your role. Write the five-part prompt yourself. Run it. Review it properly using the five-step review in §13.2.

**Why this one last:** by now you understand approvals, grounding, and scoping. This is where you find out what Cowork is actually worth in your job — and the honest answer will be specific to you.

Then do the one thing that compounds: **save the prompt.** Put it in your department's SharePoint prompt library with a note on what you'd change next time.
:::
::::

:::{tip}
**The first-week habit that predicts success**

The people who get the most out of Cowork in month one are not the ones who run the most tasks. They're the ones who, after each task, spend two minutes writing down *what they'd change in the prompt*.

Cowork rewards scoping skill more than any Copilot surface before it. Scoping skill is built by iteration, and iteration only compounds if you write it down.
:::

---

## 15. Try This: Convert Your Worst Recurring Task

Pick the task you dread most in your project cycle. The one that always slips. The one you do at 10 p.m. the night before it's due.

Now write it as a five-part Cowork prompt. Be specific enough that a competent colleague who has never done your job could produce the right thing from your description alone.

Then answer three questions:

1. **Which part was hardest to write?** For most people it's *Definition of done* — because we do these tasks by habit and have never articulated what "finished" means. That's a useful thing to learn about your own work regardless of AI.
2. **What constraint did you almost forget?** There's usually a confidentiality or template constraint that's so obvious to you it never got said out loud. Those are the ones that cause problems.
3. **What's your approval scope?** If the honest answer is "I want to check everything," that's fine for task one. Notice how it changes by task ten.

---

## 16. Productive Struggle Problem

You are the project director for a major Bowie capital improvement program. A large infrastructure rehabilitation project closed nine days ago. Three things land in the same hour on a Tuesday morning:

- The Finance Director emails asking why contractor costs were 14% over the project estimate, and requests an explanation "with data" by Thursday.
- The City Manager asks for a readiness view of the full capital program, including which projects are at risk of missing their fiscal year milestones, by Friday.
- A contractor has filed a formal claim that their subcontractor was improperly excluded from a change order approval, causing a schedule delay. The City Attorney wants a factual timeline by end of day.

You have two days of actual working time, and you're attending a community meeting on Wednesday evening.

**The challenge:** design your Cowork approach.

- Decide which of the three is a Cowork task, which is a Chat task, and which should not be delegated at all — and justify each choice using the decision rule from §1.
- Write the full five-part prompt for each task you'd delegate.
- Specify your approval scope for each and explain what you'd refuse to let Cowork do.
- Identify one confidentiality constraint that must appear in each prompt, given that the contractor claim may become a legal matter and the Finance Director is asking about costs that involve third-party contractors.
- Estimate whether each task is light, medium, or heavy, and say whether the credits are justified.

There is no single right answer. The quality of your reasoning about *what you refused to delegate* matters more than the prompts themselves.

---

## Glossary

```{glossary}
Copilot Cowork
  The Microsoft 365 Copilot capability, generally available June 16, 2026, that executes complex, long-running, multi-step tasks across apps and returns finished artifacts rather than drafts or recommendations.

Copilot Credits
  The usage-based billing unit for Cowork. Consumption is driven by four inputs: model use, context retrieval, tool calls, and runtime.

Microsoft 365 Copilot USL
  The User Subscription License that is a prerequisite for Cowork. Separately includes Copilot Chat, Copilot in the Office apps, Work IQ, multi-model intelligence, pre-built agents (Researcher, Analyst), and Agent Builder.

Work IQ
  The context engine that grounds Copilot in an organization's actual systems — email, files, meetings, chats, and sites — subject to the signed-in user's permissions.

Five-Part Prompt Structure
  Microsoft's official guidance for scoping a Cowork task: Outcome, Inputs, Definition of done, Constraints, and Approval scope.

Approval Scope
  The fifth part of a Cowork prompt — an explicit statement of which actions you want to review, beyond Cowork's default checkpoints.

Approve All
  An approval option that clears all pending approvals at once, displaying the count (e.g. Approve All (3)). Should not be used on any batch containing an externally-facing action.

Risk Level Indicator
  A signal shown on medium and high risk actions in the approval dialog, alerting the user to actions with greater consequence.

Scheduled Prompt
  A Cowork prompt configured to run automatically on a recurring schedule.

Event-Driven Task
  A Cowork task configured to run when a defined event occurs, such as an email arriving or a Teams message posting.

Custom Skill
  A user- or organization-defined Cowork skill. Up to 50 can be created; Cowork discovers them automatically at the start of each session.

Plugin
  An add-on from the Microsoft 365 App Store that extends Cowork with new skills, specialized expertise, or external data connections. Can be deployed org-wide by admins.

Sandboxed Cloud Environment
  The protected, isolated cloud environment in which Cowork tasks execute — the reason tasks continue running when a user's device is off and the reason files are not stored locally.

Light / Medium / Heavy Task
  Microsoft's three observed Cowork task patterns, distinguished by number of knowledge sources, depth of reasoning, and number of outputs.

Project Closeout
  The final documentation, financial reconciliation, and reporting process that formally concludes a capital or operating project — the City of Bowie equivalent of post-project reconciliation.

Constituent Services Workflow Chain
  The end-to-end sequence of steps by which a resident inquiry or service request is received, classified, assigned, processed, and resolved across city departments.

Capital Improvement Program (CIP)
  The multi-year plan and budget for major city infrastructure and facility investments. The primary project portfolio for Public Works, Parks & Recreation, and Planning.

Change Order
  A formal amendment to a city contract that modifies scope, cost, or timeline, requiring documented approval before implementation.

Grant Compliance Deadline
  A federally or state-mandated milestone by which a grant-funded program must demonstrate required enrollment, expenditure, or deliverable completion to remain in compliance with award terms.

Notice of Funding Availability (NOFA)
  The federal or state announcement that a grant program is accepting applications, including eligibility requirements, evaluation criteria, and application deadlines.

Bargaining Unit Classification
  The workforce classification and corresponding labor agreement governing a city employee category — rates, overtime thresholds, and applicable collective bargaining terms.
```

---

## Discussion

Cowork changes what "doing the work" means for City of Bowie employees. When the production of an artifact is delegated, the professional value shifts to two things: the quality of the brief at the front, and the rigor of the review at the back.

Consider your own role at the City. Which parts of your work are genuinely craft — where your judgment, community knowledge, or on-the-ground read is the value — and which parts are assembly, where you are moving information between systems and formats because nobody else will?

Then consider the harder question: if the assembly work were delegated, would you actually use the recovered time on the craft work? Or would it fill with more assembly?

::::{admonition} 📝 Discussion Guidelines
:class: note

Post your reflection in the course discussion forum before the next session. Your response should:

- Identify one specific recurring task in your role that you would delegate to Cowork, and write out its five-part prompt in full — Outcome, Inputs, Definition of done, Constraints, Approval scope.
- Identify one task in your role that you would **refuse** to delegate, and explain which of the City of Bowie values — Accountability, Responsiveness, Stewardship, or Pride — drives that refusal.
- Address the approval question directly: what is your personal rule for when you would and would not use Approve All, and why?
- Respond to at least **two peers** with substantive engagement — challenge a scoping decision, point out a confidentiality constraint they missed, or push back on something they chose to delegate.
- Reference at least one credible source — Microsoft's Cowork documentation, local government technology research, or the City of Bowie's own values framework.

Minimum 300 words for your main post.
::::

---

## Leader's Takeaway

Every previous chapter in this book made your employees faster at work they were already doing. This one changes what they do.

That is a bigger deal than a feature release, and it should be managed like one. Three things determine whether Cowork becomes an operational advantage for the City of Bowie or an expensive experiment.

**First: scoping is the skill, and it has to be taught.** The five-part structure — Outcome, Inputs, Definition of done, Constraints, Approval scope — is not a nice-to-have. It is the difference between a deliverable your team ships and a generic document they quietly throw away. It is also, not incidentally, the primary cost-control lever against the adopted budget. Teach it explicitly, build a shared prompt library by department, and treat a well-scoped prompt as the reusable asset it is.

**Second: the approval habit is a culture question, not a training question.** Somebody on your team will hit **Approve All** on a batch containing a constituent email. The only reliable defense is a culture where reviewing a preview properly is understood as professional behavior rather than friction — the same way verifying a contractor invoice before payment is understood as professional behavior. **Accountability** means we are answerable for our decisions and actions. **Responsiveness** means we communicate accurately with our community. Say both out loud, repeatedly, until they're reflex.

**Third: the value is in the work nobody currently has time for.** The temptation is to use Cowork on the tasks you already do, and there's real value there. But the larger return sits in the analyses that get skipped every busy construction season — the cross-project cost patterns, the grant compliance history that lives in three people's memories, the resident service comparison nobody has weeks for. Those are the tasks where Cowork doesn't make an existing process faster; it makes a previously impossible process routine.

The City of Bowie has grown from a 1870 railroad junction to Prince George's County's largest city by doing the hard work of building community, infrastructure, and services that 70,000+ residents depend on. The challenge of city government has never been lack of judgment or lack of dedication — it has been that the mechanical assembly work eats the time that judgment and dedication deserve.

Cowork is the same capability turned toward that problem — on the operational work of running a full-service city with lean teams and immovable service commitments.

The tool will keep improving. Cowork 1 is coming. More models will follow. What will not change is the underlying professional shift: from doing the work, to briefing the work and standing behind the result.

That has always been what excellent leadership looks like at a community meeting or a Council briefing. Now it's what excellent individual work looks like too.
