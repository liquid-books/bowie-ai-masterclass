---
title: "Overview & Introduction: Why This Moment Matters"
subtitle: "A Message to the City of Bowie Team"
short_title: "Introduction"
description: "An introduction to the AI master class designed specifically for City of Bowie professionals, setting the stage for transformative learning."
label: ch-00-introduction
tags: [introduction, AI, Bowie, Microsoft Copilot, Copilot Cowork, overview]
---

```{admonition} Download this Chapter as PDF
:class: tip

[Download PDF](https://github.com/liquid-books/bowie-ai-masterclass/raw/main/pdfs/ch00-introduction.pdf)
```

# Overview & Introduction: Why This Moment Matters

:::{figure} ../images/ch00-intro-infographic.png
:label: fig-ch00-infographic
:alt: Illustrated overview of AI transformation in municipal government, showing a journey from traditional city workflows to AI-augmented public service excellence
:width: 80%
:align: center

The AI transformation journey — from curiosity to mastery. This master class is your roadmap.
:::

> *"The illiterate of the 21st century will not be those who cannot read and write, but those who cannot learn, unlearn, and relearn."*
> — Alvin Toffler

There are rare moments in history when a new technology doesn't just improve how we work — it fundamentally redefines what work means. The steam engine ended the era of manual labor as the primary source of economic power. The transcontinental railroad stitched a nation together and gave birth to countless communities that would grow into great cities. The internet collapsed the cost of information to near zero. Artificial intelligence, and specifically the large language model revolution we are living through right now, is doing something arguably more profound: it is democratizing *cognitive leverage*.

For the first time in history, every professional at every level of an organization has access to something that used to be reserved for the most elite: an infinitely patient, extraordinarily well-read thinking partner available around the clock, at zero marginal cost, with expertise spanning project management, public policy, communications, finance, data analysis, and virtually every other domain of human knowledge. That thinking partner is already sitting inside your Microsoft 365 account. It is called Copilot.

And as of **June 16, 2026**, it has a second gear. Microsoft released **Copilot Cowork** into general availability — a layer that doesn't just answer your question, it *does the work*. More on that in a moment.

This book is your master class for understanding it, using it, and — most importantly — thinking with it.

## A City Built to Move Forward

:::{figure} ../images/ch00-behmn-message.png
:label: fig-ch00-city-history
:alt: Illustration representing the spirit of Bowie, Maryland — from its origins as a railroad junction town to a thriving, proud city of 70,000+ residents leading the way in public service innovation
:width: 80%
:align: center

From railroad junction to Prince George's County's largest city — Bowie has always been a place that moves forward.
:::

Bowie, Maryland did not become the largest city in Prince George's County by standing still.

In **1870**, what would become Bowie was little more than a dusty railroad junction — the crossing point of the Baltimore and Potomac Railroad line that connected the nation's capital to the wider world. The name "Bowie" itself honors Oden Bowie, a Maryland governor and railroad president who understood that infrastructure was destiny. The trains didn't just pass through. They created a community, a reason for people to stop, to settle, to build.

A century later, Bowie made another decisive move. In **1963**, residents voted to incorporate — to take ownership of their own future, to have a voice in their own governance. In the more than **60 years since**, Bowie has grown from that bold vote into a city of more than **70,000 residents**, home to Bowie State University, the beloved Bowie Baysox, the natural sanctuary of Allen Pond Park, and the proud streets of historic Old Town Bowie. It has become a place where families put down roots, where the public schools matter, where neighbors know each other's names, and where city employees show up every day to make that quality of life possible.

The railroad brought the first transformation. Digital technology is bringing the next one.

And just as the citizens of 1963 didn't wait for someone else to decide Bowie's future, the employees of today's City of Bowie don't have to wait either.

This book is the guide for that transition.

## A Message from the Author

:::{figure} ../images/ch00-author-message.png
:label: fig-ch00-author
:alt: Illustration of a practitioner-teacher bridging technical AI capability and working public service professionals, representing hands-on instruction grounded in real government operations
:width: 80%
:align: center

This book is a practitioner's book. Every technique in it has been run against real work before it was written down.
:::

I want to tell you why this book exists, and why it is written the way it is.

I have spent my career in two worlds that rarely talk to each other. In one, I work with data and AI systems — building them, stress-testing them, and figuring out where they actually hold up under load. In the other, I serve alongside government professionals — people with real constituents, real deadlines, real accountability, and no patience for tools that don't work on Monday morning.

Those two worlds produce very different books about AI. The technical one produces books that are correct and useless. The teaching one produces books that are inspiring and empty. I have tried to write the third thing: a book that is honest about how these tools actually behave, and specific enough that you can use them before you finish the chapter.

That is why the examples in this book are not generic. A generic AI book would tell you to "summarize a document." This one asks you to summarize a public works project brief, because that is a document you actually have, with quirks a generic example would never surface. It would tell you to "analyze a spreadsheet." This one looks at budget variance *within* a department's fiscal year, because comparing across fiscal periods produces a number that looks fine and is wrong. The specificity is the point. Anything less would be a book about AI rather than a book about your work.

I also want to be direct about the limits, because most AI writing is not. These tools are extraordinary and they are also confidently wrong on a regular basis. They will invent a figure that looks plausible. They will produce a clean, well-formatted answer built on an outdated policy reference. Throughout this book, wherever a technique has a failure mode, I have written the failure mode down next to it. You should not trust anyone who sells you the capability without the caveat.

Here is what I actually want for you. Not that you finish this book impressed by AI — that is easy and worth very little. I want you to finish it with a handful of habits you keep. The habit of giving a tool enough context to be useful. The habit of checking the output before your name goes on it. The habit of noticing when a task you do every week is a task you should never do manually again.

Do that, and the specific products in these pages can change — and they will — without any of your skill going out of date.

Let's get to work.

— **Khalil Lyons**
Author; AI Literacy Specialist

## Why Bowie? Why Now?

:::{figure} ../images/ch00-ges-by-numbers.png
:label: fig-ch00-numbers
:alt: Infographic displaying City of Bowie's scale — 70,000+ residents served, 8 major departments, 60+ years of incorporation, city staff serving every aspect of community life
:width: 90%
:align: center

The operational surface area that makes AI compound at the City of Bowie rather than merely help.
:::

The City of Bowie is not just an address on a map. It is a full-service municipal government responsible for the day-to-day quality of life of more than **70,000 residents** — every pothole reported on a neighborhood street, every permit application submitted by a small business owner, every 911 call answered by a dispatcher, every park maintained for a family's Saturday afternoon.

Think about the sheer operational surface area in that service mission. **City Administration** coordinates the strategic direction that touches every department. **Parks & Recreation** plans and executes events, maintains Allen Pond Park and dozens of other facilities, and builds the programs that keep communities connected. **Public Works & Engineering** manages streets, stormwater, fleet, infrastructure maintenance, and capital projects that run year-round. **Finance & Budget** oversees the fiscal stewardship of public funds with accountability to every taxpayer. **Planning & Community Development** processes zoning applications, development reviews, and long-range planning in one of Maryland's most dynamic growth corridors. **Human Resources** recruits, develops, and supports the people who make all of the above possible. **Public Safety Communications** answers the call — literally — when residents are at their most vulnerable. **Constituent Services** is the front door through which residents experience their government.

That is not a city with an AI opportunity. That is a city where AI **compounds**.

And Bowie is doing this at a genuinely pivotal moment. As the City marks **more than 60 years since incorporation**, it carries the operational wisdom of six decades of community governance into a new era of digital tools that can multiply what every city employee is capable of. For the first time in Bowie's history, a front-line Parks & Recreation coordinator and the City Administrator both have access to the same level of AI-powered cognitive support — the same quality of thinking partner, the same capacity to work faster, communicate more clearly, and serve residents more responsively.

The City of Bowie is not theorizing about AI. This book is part of a real, deliberate initiative to ensure that every employee who wants to grow their skills has a pathway to do so. The question is not whether AI will reshape how municipal governments operate. It is already reshaping them. The question is whether the professionals inside the City of Bowie will shape *how* that transformation happens — or watch from the sidelines while the opportunity passes them by.

This master class says: you will not watch. You will lead.

## Anchored in Bowie's Values

:::{figure} ../images/ch00-true-values.png
:label: fig-ch00-values
:alt: Four-pillar diagram of the City of Bowie's core values — Accountability, Responsiveness, Stewardship, and Pride — shown as the foundation supporting AI practice
:width: 85%
:align: center

Accountability, Responsiveness, Stewardship, Pride. AI does not replace these values — it tests them.
:::

Everything in this book sits on top of the four values the City of Bowie already lives by. AI does not replace them. It tests them.

| Value | What it means at the City of Bowie | What it means with AI |
|---|---|---|
| **Accountability** | Own your actions and outcomes, and be transparent with residents and colleagues | AI is a tool, not an oracle. Verify outputs. Never let a machine sign off on a public document without you reading it first. |
| **Responsiveness** | Answer the question, serve the resident, close the loop — quickly and completely | AI can help you respond faster. It cannot replace the judgment about *what* to say and *how* to say it to a resident in distress. You still own that. |
| **Stewardship** | Manage public resources — time, money, infrastructure, information — as a public trust | Your name is on the deliverable. AI does not absolve you of the budget estimate, the permit decision, or the safety advisory. You own it. |
| **Pride** | Take pride in your work, your city, and the service you provide to 70,000+ residents | AI raises the floor for everyone. City employees raise the ceiling. Use the time AI gives back to do the work only you can do — the work that requires human judgment, local knowledge, and genuine care. |

If you remember nothing else from this introduction, remember that framing. **AI raises the floor. You raise the ceiling.**

## What This Book Is

Think of this as a TED talk you can read. We are not going to burden you with academic jargon or lengthy technical treatises. We are going to answer the questions that actually matter to you, as a city government professional:

- **What exactly is AI?** Not the science fiction version. The real version. And what can it actually do?
- **What is Microsoft Copilot and how does it work inside your daily tools?**
- **What is Copilot Cowork, and when should you delegate an entire task instead of asking a question?**
- **How do I use it to become measurably better at my job — whether that job is in Public Works, Parks & Recreation, Finance, Planning, HR, or City Hall?**
- **What are the rules, risks, and responsibilities that a public servant like you needs to understand?**
- **How do I move from simply using AI to genuinely *thinking with* AI?**

This book won't just give you knowledge. It will give you a new *relationship* with thinking itself.

## Copilot, and Now Cowork

Most people meet AI as a **conversation**. You ask, it answers. You refine, it revises. That is Microsoft 365 Copilot, and it is genuinely useful: summarize a 60-page capital project report, draft a reply to a resident's inquiry, build a first-pass presentation for City Council, explain a formula in a budget reconciliation workbook.

**Copilot Cowork**, generally available since **June 16, 2026**, is a different mode of working. Instead of a conversation, it is a **delegation**.

:::{figure} ../images/ch00-copilot-vs-cowork.png
:label: fig-ch00-copilot-cowork
:alt: Side-by-side comparison showing Copilot as a back-and-forth conversation producing an answer, versus Cowork as a delegated task producing a finished multi-part deliverable
:width: 90%
:align: center

Ask versus delegate. One document is Copilot. A project is Cowork.
:::

Cowork executes complex, long-running, multi-step tasks end to end across **Outlook, Teams, Word, Excel, PowerPoint, and SharePoint** — and returns *completed results*, not drafts you still have to assemble. A few things make it meaningfully different from the chat experience you may already know:

- **It runs in the cloud.** Tasks keep running when your laptop is closed and you are in a community meeting, out inspecting a park, or on a site visit to a construction project. You hand off the work, then you collect it.
- **It is grounded in Work IQ.** It understands your organizational context — your files, your threads, your meetings, your people — rather than working from a blank page.
- **It stays inside the Microsoft 365 trust boundary.** Your data stays governed by the same enterprise controls that already protect your email and your SharePoint libraries.
- **It is multi-model.** Cowork runs on Anthropic's frontier models — **Claude Opus 4.8** and **Claude Sonnet 4.6** — alongside Microsoft's other model options, chosen for the depth of reasoning that long-horizon, multi-tool work requires.
- **It is billed by usage.** Cowork consumes **Copilot Credits** on top of a Microsoft 365 Copilot license. That matters operationally: delegation is a resource, and like staff hours or budget line items, you should spend it where the return is highest.

Here is the practical distinction, in City of Bowie terms:

| You want to... | Use |
|---|---|
| Summarize a resident complaint thread for a supervisor | **Copilot** |
| Review six months of 311 service requests, build a category breakdown, write a summary memo, and drop it in the department SharePoint | **Cowork** |
| Draft one reply to a permit applicant's scope question | **Copilot** |
| Read 40 inbound constituent emails, categorize by issue type, draft responses for the routine ones, and flag the exceptions for a supervisor | **Cowork** |
| Explain a budget variance calculation | **Copilot** |
| Pull expenditure data from three departments, build a cost-per-program analysis, produce a summary deck, and share it with the Finance team | **Cowork** |

Throughout this book, when a workflow is big enough to be worth handing off rather than steering turn by turn, we will flag it. Learning *when to delegate* is a skill in itself — the same judgment you already apply when deciding which resident concerns need a supervisor's attention and which you can resolve directly.

:::{tip}
**A simple rule of thumb.** If the task is one document, one question, or one answer — that's Copilot. If the task is a *project* with several steps, several files, and a deliverable at the end — that's Cowork.
:::

## The Arvin Ash Principle

There is a science communicator on YouTube named Arvin Ash whose channel has captivated millions of people with a seemingly simple approach: take the most complex ideas in physics, mathematics, and technology, and explain them using *nothing but analogies and curiosity*. No unnecessary jargon. No condescension. No hand-waving. Just the real concept, explained so clearly that you can share it with someone at dinner that same night.

That is the operating principle of this book.

Every concept we cover — from Large Language Models to context windows to AI agents — will be explained the way Arvin would explain it: starting with something you already know, building a bridge to the new idea, and then revealing the implications that should genuinely surprise you. Because they should. The implications of what you are about to learn are genuinely astonishing.

And because this is Bowie, the bridge we build will start from things you already live with: a constituent complaint that needs a careful response, a permit application that has to be processed accurately, a budget request that has to be right before it goes to Council, a public works crew that needs a clear work order at the start of every shift.

## Who This Book Is For

:::{figure} ../images/ch00-who-this-is-for.png
:label: fig-ch00-audience
:alt: Six audience groups shown as illustrated role cards — City Administration, Parks and Recreation, Public Works and Engineering, Finance and Budget, Planning and Community Development, and Public Safety Communications
:width: 90%
:align: center

Eight departments, one book. The City of Bowie is not a company of desk workers, and this material does not pretend otherwise.
:::

The City of Bowie is not a city of desk-bound knowledge workers, and this book does not pretend otherwise. The examples in these chapters are written for the whole organization:

- **City Administration** — department directors, executive assistants, communications staff. Strategic planning, Council communications, inter-agency coordination.
- **Parks & Recreation** — program coordinators, facility managers, event staff. Community events, park maintenance schedules, facility reservation management.
- **Public Works & Engineering** — project managers, inspectors, fleet and infrastructure teams. Work orders, capital project tracking, infrastructure condition reporting.
- **Finance & Budget** — budget analysts, accounts payable and receivable, grant administrators. Budget preparation, expenditure analysis, grant reporting.
- **Planning & Community Development** — planners, zoning staff, permit technicians. Development applications, planning reports, resident communications on land use.
- **Human Resources** — recruiters, benefits administrators, training coordinators. Job postings, onboarding documentation, policy communications.
- **Public Safety Communications** — dispatch supervisors, quality assurance staff. Shift reports, incident summaries, protocol documentation.
- **Constituent Services** — front-line staff, caseworkers, neighborhood liaisons. Resident intake, case documentation, follow-up correspondence.

If you recognize your job in that list, you are the audience. If you recognize *someone else's* job in that list, even better — a lot of the value in this book comes from the handoffs between those groups.

## How to Use This Book

This is a **hands-on master class**. Every chapter includes "Try This" exercises that take you directly into your Microsoft 365 environment and have you interact with Copilot in real time. The exercises are not optional homework. They are the actual learning. Reading about a bicycle and riding a bicycle are entirely different experiences.

You will need:
- A Microsoft 365 account with Copilot enabled (check with your IT administrator)
- Access to [m365.cloud.microsoft](https://m365.cloud.microsoft) — this is your front door to Enterprise Copilot
- Copilot Cowork access, if your license includes it, for the delegation exercises (your IT administrator can confirm whether Copilot Credits are enabled for your team)
- About 15 minutes of focused time per chapter for the exercises

No prior technical knowledge is required. If you can write an email, you can learn to use AI. If you can brief a crew on a morning's work plan, you can already write a good prompt — you just haven't been told that's what it is.

:::{note}
**Use real work, not toy examples.** The exercises are far more valuable when you run them against something on your actual plate this week — a live service request, a real resident inquiry thread, an actual budget variance. Follow your normal data-handling and public records rules, of course. But don't practice on fake material when the real material is right there.
:::

## A Note on Voice

This book will speak to you directly. We will use "you" throughout because this transformation is personal. What AI does for your career, your productivity, and your value inside the City of Bowie is determined by what *you* choose to do with it. The tools are neutral. The results are up to you.

One more thing before we begin. There is a quiet revolution happening in how people interact with AI that we want to put in front of you early. Tools like **Wispr Flow** and **Super Whisper** allow you to speak to your computer — to your AI — the same way you would speak to a colleague. Instead of typing out your prompts, you simply *talk*. Your words are transcribed and sent to Copilot in real time. People who adopt voice-first AI interaction report that their outputs are dramatically better: more natural, more nuanced, more complete. The reason is simple — we speak far faster than we type, and we explain things more naturally in speech than in writing.

For city employees who spend time in the field, on community walkthroughs, at public meetings, or staffing community events, that is not a novelty. That is the difference between capturing resident feedback while you're in a neighborhood meeting and trying to reconstruct it three hours later.

Before this program is over, we want you to try it. You may never go back.

## What's Ahead

:::{figure} ../images/ch00-book-roadmap.png
:label: fig-ch00-roadmap
:alt: Visual roadmap of the book showing progression from foundations through mindset and change management into hands-on application across Microsoft 365 applications
:width: 90%
:align: center

The path ahead: foundations, then the human side, then hands-on work in the tools.
:::

In **Chapter 1: The Essentials**, we build your complete conceptual foundation. You will understand what a Large Language Model actually is, how tokens work, what context engineering means and why it is the most valuable skill in the AI era, how to set your AI's persona, how to communicate with AI like an expert (meta-prompting), how your data is already connected to Copilot, and what an AI agent is and how to build your first one.

From there, the book moves through the mindset shift, change management, and adoption — the human side of this, which is the part that actually determines whether a technology sticks — and then into hands-on work in Word, Excel, PowerPoint, Teams, OneNote, and SharePoint, using public works project reports, budget analyses, resident correspondence, cross-department meeting notes, community event planning documents, and departmental knowledge bases as the material.

By the time you finish Chapter 1, you will not just *know about* AI. You will have used it in ways that are directly relevant to your work at the City of Bowie. You will have seen it respond to your email, your calendar, your department's files. You will have built something.

Let's get started. Bowie is ready. The work is waiting.

---

:::{note}
**For the City of Bowie Team**

Everything in this book has been designed with your specific context in mind. The examples, exercises, and use cases reflect the realities of municipal public service — constituent interactions, permit processing, public works project management, parks programming, budget stewardship, emergency communications, and the inter-departmental coordination that holds it all together. When you see a scenario in these pages — a resident complaint that needs a careful response, a budget line that doesn't add up, a park event that needs a permit package by Friday, a public works crew waiting on a work order — you should recognize it. This is your world, viewed through the lens of what AI makes possible.

Bowie has always been a city that moves forward. What we build next is ours.
:::
