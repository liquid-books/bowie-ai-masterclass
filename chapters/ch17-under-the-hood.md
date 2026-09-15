---
title: "Chapter 17: Under the Hood"
subtitle: "The Graph, Tools, and How Copilot Actually Thinks"
short_title: "Under the Hood"
description: "The advanced chapter for technically curious readers who want to understand the machinery behind Microsoft 365 Copilot. Covers Microsoft Graph as the unified data layer, the semantic index, retrieval-augmented generation, function calling and tool use, Model Context Protocol, Graph connectors, and Copilot Studio — the foundational architecture that makes Copilot genuinely useful at the City of Bowie."
label: ch-17-under-the-hood
tags: [Microsoft Graph, semantic index, RAG, grounding, function calling, tool use, MCP, Model Context Protocol, Graph connectors, Copilot Studio, agents, retrieval, permissions, City of Bowie, Accountability, Responsiveness, Stewardship, Pride]
---

```{admonition} Download this Chapter as PDF
:class: tip

```

# Chapter 17: Under the Hood

:::{figure} ../images/ch17-under-the-hood-infographic.png
:label: fig-ch17-infographic
:alt: Technical architecture diagram showing Microsoft Graph at the center connected to people, files, mail, calendar, meetings, and sites — with the semantic index layer above it, retrieval flows feeding into the LLM, and tool connections extending to external systems and actions
:width: 80%
:align: center

The machinery behind the magic. Microsoft Graph holds your organization's data as a web of relationships. The semantic index makes it searchable by meaning. Tools let Copilot act, not just answer. Understanding these layers makes you a dramatically better operator.
:::

> *"Any sufficiently advanced technology is indistinguishable from magic."*
> — Arthur C. Clarke
>
> *"Any sufficiently analyzed magic is indistinguishable from technology."*
> — The corollary that matters for this chapter

You have spent sixteen chapters learning to *use* Microsoft 365 Copilot. This chapter is different. This chapter is about understanding *how it works* — not because you need to become an engineer, but because understanding the machinery makes you dramatically better at operating it.

Here is why this matters at the City of Bowie specifically: when you understand that Copilot's answers come from a structured web of relationships rather than a generic knowledge base, you start asking different questions. When you understand that a tool call is a structured request the model emits rather than a command it executes, the permission model suddenly makes sense. When you understand that retrieval can fail silently, you stop blaming the AI for answers it was never given the ingredients to produce.

Chapter 1 introduced the flashlight theory — that context is what turns raw intelligence into useful output. This chapter shows you what the flashlight is actually made of. It shows you the data structure underneath, the retrieval system that finds the right content, and the tool architecture that lets Copilot act rather than just talk.

Three big ideas organize everything that follows:

1. **The Graph.** Your organization is not a pile of files. It is a web of relationships between people, documents, meetings, messages, and sites. Microsoft Graph is the unified layer that holds those relationships, and the semantic index is what makes them searchable by meaning rather than keyword.

2. **Tools are the unlock.** A language model alone can only produce text. A model with tools can act: query a database, send a message, book a room, run a workflow. Function calling — the ability to emit a structured request for action — is the single biggest capability jump in the AI era.

3. **Adding your own tools.** Graph connectors bring City of Bowie line-of-business data into Copilot's reach. Copilot Studio lets you build custom agents with custom actions. The Model Context Protocol (MCP) is the emerging open standard. Power Automate flows become callable tools. This is where Copilot stops being Microsoft's product and becomes yours.

By the end of this chapter, you will understand why Copilot can answer questions about your organization that a generic chatbot never could — and why it sometimes cannot answer questions that seem obvious. That understanding is practical, not academic. It changes how you prompt, how you troubleshoot, and how you decide what to build.

---

## 1. The Graph: Your Organization as a Web of Relationships

### 1.1 What Microsoft Graph actually is

Strip away the marketing and here is the core truth: **Microsoft Graph is a unified API and data layer that connects everything in Microsoft 365.**

Not a database in the traditional sense. Not a folder hierarchy. A *graph* — which in this context means a structure of **nodes** (things) connected by **edges** (relationships between things).

The nodes are the entities you work with every day:
- **People** — every user in your organization
- **Documents** — files in SharePoint, OneDrive, Teams
- **Messages** — emails in Exchange, chats in Teams
- **Meetings** — calendar events with attendees and recordings
- **Sites** — SharePoint sites and Teams channels
- **Groups** — Microsoft 365 groups and distribution lists

The edges are the relationships between them:
- Who **authored** a document
- Who **attended** a meeting
- Who **shared** a file with whom
- Who **replied to** an email thread
- Who **works with** whom (inferred from collaboration patterns)
- Which document **belongs to** which site
- Which meeting **relates to** which project

:::{figure} ../images/ch17-graph-structure.png
:label: fig-ch17-graph-structure
:alt: Diagram showing Microsoft Graph as a network of connected nodes — people, documents, emails, meetings, and sites — with labeled edges showing relationships like authored, attended, shared with, replied to, and works with
:width: 80%
:align: center

Microsoft Graph in its simplest form: nodes (entities) connected by edges (relationships). Every person, document, meeting, and message in your City of Bowie Microsoft 365 tenant exists as a node, and the relationships between them are explicit, queryable, and — crucially — permission-controlled.
:::

Here is what makes this powerful: **the relationships are first-class data, not afterthoughts.**

In a traditional file system, a document is just a document. It sits in a folder. The fact that you wrote it, that your colleague edited it, that it was attached to an email chain about a specific capital project, that it was discussed in a Tuesday morning department meeting — all of that context exists only in human memory or in timestamps you'd have to reconstruct manually.

In Microsoft Graph, all of that context is *explicit and queryable*. The document node is connected to a person node (author) by an "authored" edge. It's connected to other person nodes by "shared with" edges. It's connected to an email thread node. It's connected to a meeting node where it was a shared resource.

When Copilot answers a question about your work, it is not searching a pile of files. It is traversing a web of relationships — following the edges from what you asked to what is relevant, respecting your permissions at every step.

### 1.2 City government as a graph — an analogy you already know

If this sounds abstract, consider something you understand deeply: how a capital improvement project moves through the City.

A capital project is not a list of tasks. It is a *graph* of relationships.

:::{figure} ../images/ch17-show-floor-as-graph.png
:label: fig-ch17-show-floor
:alt: A capital improvement project represented as a graph structure — department nodes connected to project nodes, project nodes connected to budget nodes, contractor nodes connected to permit nodes, inspection nodes connected to Public Works nodes, all connected to a central city administration node
:width: 80%
:align: center

A city capital project is a graph: departments, budgets, contractors, permits, inspections, and residents connected by relationships. You navigate this structure instinctively during project execution — Copilot navigates Microsoft Graph the same way.
:::

The **nodes** are:
- Departments (Planning, Public Works, Finance, Parks & Recreation)
- Projects (capital improvements, road resurfacing, facility renovations)
- Budgets (appropriations, encumbrances, expenditures)
- Contractors (vendors, consultants, engineers)
- Permits (building, grading, right-of-way)
- Residents (affected constituents, stakeholders)
- Services (inspections, utilities, maintenance)

The **edges** are:
- This department **owns** this project
- This project **is funded by** this budget line
- This contractor **is assigned to** this project
- This permit **is required for** this construction phase
- This inspection **relates to** this contractor
- This resident **submitted a comment on** this project
- This project **connects to** the Comprehensive Plan goal

When a Public Works project manager tracks a road resurfacing project, they traverse this graph instinctively. "The paving contractor is working Section 4 → that section requires right-of-way permits from Planning → the contractor's schedule depends on the inspection results → resident notifications go out before lane closures." That is graph traversal — following edges from node to node to understand how everything connects.

Microsoft Graph does the same thing with your organizational data. When you ask Copilot "What did we decide about the timeline for the Belair Road corridor project?", it traverses: your recent meetings → attendees → shared documents → email threads — following the edges to find content that is *relevant to your question*, not just keyword-matched to your words.

### 1.3 Why the Graph is the entire reason Copilot beats a generic chatbot

Here is the insight that changes how you think about Copilot:

**A generic AI chatbot knows language. Copilot knows your organization.**

ChatGPT, Claude, Gemini — they are trained on the public internet. They know what a capital improvement program *is* in the abstract. They do not know what *your* CIP document says, who wrote it, which department it belongs to, or that it was updated last Tuesday after a meeting with the City Manager's office.

Copilot does. Because Copilot is grounded in Microsoft Graph — your Graph, your City of Bowie Microsoft 365 tenant, your relationships.

When you ask Copilot to summarize the status of a project, it can pull from:
- The email threads between you and the department director
- The Teams channel where the project team discussed milestones
- The SharePoint site where the operations SOP lives
- The meeting where the budget revision was finalized
- The document where the contractor schedule was updated

It does not just know that these things exist. It knows *how they relate* — that this email is a reply to that earlier thread, that this document was shared in that meeting, that this person is the project manager and that person is the finance analyst.

That relational knowledge is what makes Copilot's answers specific rather than generic. It is also what makes the permission model work — the Graph knows not just what exists, but who is allowed to see it.

---

## 2. The Semantic Index: Making the Graph Searchable by Meaning

The Graph holds the relationships. The **semantic index** makes them findable.

### 2.1 From keywords to meaning

Traditional search works by keyword matching. You type "road resurfacing budget" and the system finds documents containing those exact words. The problem is obvious: a document might discuss pavement rehabilitation, infrastructure funding, and maintenance appropriations without ever using the phrase "road resurfacing budget" — and traditional search would miss it.

The semantic index solves this with **vector embeddings** — mathematical representations of meaning rather than text.

Here is the intuition: imagine every document, every email, every meeting transcript is converted into a point in a high-dimensional space. Documents that mean similar things end up near each other, even if they use different words. "Road resurfacing budget," "pavement rehabilitation funding," "maintenance appropriation," and "capital outlay for street improvements" all cluster together because they are about the same *concept*.

:::{figure} ../images/ch17-semantic-index.png
:label: fig-ch17-semantic-index
:alt: Visualization of the semantic index showing documents represented as points in a vector space, with conceptually similar content clustered together regardless of exact wording — a query about road resurfacing budgets retrieving documents about pavement rehabilitation, infrastructure funding, and maintenance appropriations
:width: 80%
:align: center

The semantic index converts documents into vector embeddings — mathematical representations of meaning. Conceptually similar content clusters together, enabling search by meaning rather than keyword. This is why Copilot can find relevant content even when you phrase your question differently than the document was written.
:::

When you ask Copilot a question, your question is also converted into a vector. The system then finds the Graph content whose vectors are *closest* to your question — the content that is semantically most relevant, regardless of exact word choice.

This is why Copilot can answer "What's the plan for repaving the neighborhood streets this summer?" even if the operations plan uses the phrase "residential pavement rehabilitation schedule" instead of "repaving plan." The semantic index understands that these are the same concept.

### 2.2 How retrieval actually works — RAG and grounding

When you prompt Copilot, you are not talking directly to the language model. Your question goes through a retrieval pipeline first.

**RAG — Retrieval-Augmented Generation** — is the technical term for this pattern:

1. **Query understanding.** Copilot interprets your question and determines what kind of information would answer it.

2. **Retrieval from the Graph.** The system queries the semantic index, following relationships in the Graph to find content that is relevant to your question *and* that you have permission to see.

3. **Grounding.** The retrieved content is assembled into context — the "flashlight beam" from Chapter 1. This context accompanies your question when it goes to the language model.

4. **Generation.** The language model produces an answer, grounded in the retrieved content. When Copilot cites a source, it is citing what the retrieval system found.

:::{figure} ../images/ch17-rag-grounding-flow.png
:label: fig-ch17-rag-flow
:alt: Flow diagram showing the RAG process — user question enters, retrieval queries the semantic index and Microsoft Graph, retrieved content is assembled as grounding context, the grounded prompt goes to the LLM, and the response returns with source citations
:width: 80%
:align: center

The retrieval-augmented generation (RAG) flow: your question triggers a search of the semantic index and Microsoft Graph, retrieving relevant content you have permission to see. That content grounds the language model's response, which is why Copilot can cite specific sources.
:::

This architecture is why Copilot's answers are specific to your organization. The language model provides the reasoning; the Graph provides the facts. Without the Graph, you would get generic answers. Without the language model, you would get search results without synthesis.

### 2.3 Permission trimming — the Graph enforces access at retrieval time

Here is a fact that should give you confidence: **the Graph enforces your permissions at retrieval time, before any content reaches the language model.**

Chapter 12 covered this from the SharePoint governance perspective. Here is the technical mechanism underneath:

When retrieval queries the Graph on your behalf, it runs *as you* — with your identity, your permissions, your access rights. Content you cannot see in SharePoint directly, you cannot see through Copilot. The filtering happens at the data layer, not at the presentation layer.

This is not a policy overlaid on top of the system. It is the architecture. Microsoft Graph was built with identity and access control as foundational principles because it was designed to serve all of Microsoft 365 — including applications where permission enforcement is legally mandated.

The practical implication: **Copilot cannot show you a document you were never given access to.** If you ask about a personnel matter you are not authorized to view, and the answer would require content from HR's restricted SharePoint site, Copilot will not retrieve it. Not because it chose to hide it, but because the retrieval system — running as you — cannot see it.

This is also why oversharing in SharePoint becomes a risk through Copilot. If you *do* have access to content you should not (because someone shared too broadly), Copilot will find it and use it. The system enforces the permissions that exist, not the permissions that should exist. That is why Chapter 12's governance guidance matters operationally — especially given Maryland's Public Information Act (MPIA) and government data classification requirements.

::::{admonition} 🎯 Accountability Check
:class: note

**Accountability** — *we are responsible for our actions and our results.*

The permission model is trustworthy because it is architectural, not behavioral. Copilot does not decide to respect your access rights — it cannot do otherwise. But that trust depends on correct permissions being set in the first place. If a document containing confidential personnel information or pre-decisional budget materials is readable by someone who should not see it, the Graph will serve it faithfully. Accountability for data security starts with setting the right permissions — not with trusting that the AI will sort it out.
::::

### 2.4 Graph connectors — bringing City of Bowie data into the Graph

The Graph contains Microsoft 365 data by default. But what about the systems that are not Microsoft 365?

The City of Bowie operates line-of-business systems for permitting, work orders, constituent services, finance, and records management that exist outside the Microsoft 365 environment. That data lives outside the Graph — which means, by default, Copilot cannot see it.

**Graph connectors** solve this by ingesting external data into the semantic index, making it searchable and retrievable alongside Microsoft 365 content.

A Graph connector does three things:

1. **Ingestion.** It reads data from the external system — a database, a SaaS application, a custom platform.

2. **Mapping.** It converts that data into Graph-compatible entities with properties and relationships.

3. **Indexing.** It feeds the data into the semantic index so it becomes part of what Copilot can retrieve.

The result: Copilot can answer questions that require your municipal data, not just your email and documents.

**For the City of Bowie, the connector opportunity is substantial:**

- **Permitting system.** Active permit applications, inspection status, contractor compliance records — indexed and retrievable when a Planning or Public Works staff member asks "What permits are pending for this address?"
- **Work order management.** Public Works service requests, maintenance schedules, asset conditions — so staff can ask "What open work orders exist for Belair Road?" without switching systems.
- **Constituent services platform.** Resident requests, case status, resolution history — so Constituent Services staff can ask "Has this resident submitted prior requests?" and get a real answer.
- **Finance and budget system.** Appropriation balances, encumbrances, expenditures by department and project — so Finance and department directors can ask "Where does our Parks & Recreation capital budget stand?" with real data.

Microsoft publishes pre-built connectors for common systems (Salesforce, ServiceNow, Jira, and over 1,400 others) and provides a connector SDK for building custom connections to proprietary systems.

::::{admonition} ⚠️ Connector governance
:class: warning

Every Graph connector widens the retrieval surface. That is the point — and also the risk.

When you connect an external system to the Graph, its data becomes subject to the same permission model as everything else. If the external system has its own access controls, those controls need to be mapped correctly, or data that was restricted in the source system becomes broadly retrievable through Copilot.

Connectors for City of Bowie line-of-business data should be deployed with the same care as SharePoint site permissions — and with particular attention to Maryland MPIA compliance. The question is always: "Who should be able to ask Copilot about this, and will the connector enforce that correctly?" Some municipal records are public; others are confidential. The connector must reflect that classification.
::::

### 2.5 Honest limits — what the Graph cannot do

Understanding how retrieval works also means understanding when it fails.

**If it is not in the Graph, Copilot cannot see it.** A document on a local hard drive, records in a system not yet connected, institutional knowledge that exists only in a long-tenured employee's memory — none of this is retrievable. Copilot is grounded in what the Graph contains, and the Graph contains only what has been ingested into it.

**Retrieval fails silently.** When Copilot cannot find relevant content, it does not say "I searched the Graph and found nothing." It generates an answer from what it *did* find — which may be nothing, in which case you get a generic response, or may be the wrong thing, in which case you get a confidently incorrect response. The absence of a "no results" signal is one of the hardest things to calibrate for.

**Stale documents poison answers.** The semantic index reflects what is in the Graph today. If a superseded ordinance sits next to the amended version without being archived, both are indexed, and retrieval may find either. This is the grounding drift problem from Chapter 12 — and it is a retrieval problem at heart.

**Recency is a weak signal.** The semantic index prioritizes *meaning* over *time*. An older document that is semantically closer to your question may rank above a newer one that is less similar. This is usually correct, but it means "give me the latest" requires explicit phrasing, and even then retrieval may not perfectly capture your intent.

**The Graph knows relationships, not truth.** A document that is connected to the right people and stored in the right channel will be retrieved — even if its content is wrong. The Graph tells Copilot that this document is relevant; it does not tell Copilot that this document is accurate.

---

## 3. Tools Are the Unlock

Everything so far has been about retrieval — finding information and grounding answers in it. Now we turn to the capability that changed everything else: **tools**.

### 3.1 The fundamental shift — from talking to acting

A language model, by itself, can only produce text. It can reason, summarize, draft, explain — all valuable. But it cannot *do* anything. It cannot send an email, book a room, query a database, run a calculation, or update a record.

**Function calling** — also called tool use — changes this. It gives a language model the ability to request actions, not just generate text.

Here is the crucial insight: **the model does not execute the action itself.** It emits a *structured request* that a trusted layer executes on its behalf.

:::{figure} ../images/ch17-tool-calling-loop.png
:label: fig-ch17-tool-loop
:alt: Diagram showing the tool-calling loop — user request enters, LLM reasons about what tool to call, emits a structured JSON request, trusted execution layer runs the tool and returns results, LLM incorporates results into its response
:width: 80%
:align: center

The tool-calling loop: the language model decides which tool to invoke and constructs a structured request (typically JSON). A trusted execution layer — not the model itself — runs the tool and returns results. The model then incorporates those results into its response. This separation is what makes the permission model work.
:::

When you ask Copilot to send an email, here is what actually happens:

1. **Reasoning.** The model determines that your request requires sending an email and identifies the recipient, subject, and body from your prompt.

2. **Tool call.** The model emits a structured request — essentially a JSON object specifying "call the send_email function with these parameters."

3. **Execution.** The Copilot system receives this request, validates it, and executes the email send using your identity and your Outlook permissions.

4. **Return.** The result (success, failure, confirmation) returns to the model.

5. **Response.** The model incorporates the result into its response to you.

The model decided *what* to do and *how* to specify it. The system did the actual doing. This separation is not a technical detail — it is the entire reason tool use is safe enough to deploy in a government environment.

### 3.2 Why this is the single biggest capability unlock

The intelligence has been impressive for years. What changed is that the intelligence can now *work*.

Consider the difference:

**Without tools:** "Here is a draft of the email you should send to the contractor about the revised project timeline. You can copy it and send it yourself."

**With tools:** "I have sent the email to the contractor about the revised project timeline. Here is what I sent."

The second version saves thirty seconds. Multiply by a thousand tasks a day across City departments, and you are looking at structural time recovery. But the real transformation is not time — it is *what becomes possible*.

**Cowork is a tool-use story.** When Cowork assembles a status report by pulling data from SharePoint, analyzing it in Excel, drafting a summary in Word, and preparing an email to the department director, it is executing a sequence of tool calls — each one a structured request to a specific capability.

**Power Automate integration is a tool-use story.** When a Copilot agent triggers a flow that updates a record in a constituent services platform, it is calling a tool — the flow itself — with parameters derived from the conversation.

**Graph queries are tool calls.** When Copilot searches your email or retrieves a document, it is calling the Microsoft Graph API — another tool in the toolkit.

:::{figure} ../images/ch17-tools-unlock.png
:label: fig-ch17-tools-unlock
:alt: Before-and-after comparison showing a language model without tools (can only generate text, suggest actions, provide drafts) versus with tools (can send email, query databases, run workflows, create documents, book meetings, update records)
:width: 80%
:align: center

The tool unlock: without tools, a language model can only talk. With tools, it can act. This is the difference between an advisor who suggests and an operator who executes.
:::

### 3.3 Tool permissions inherit from the user

Here is the security principle that makes tool use deployable at scale: **every tool executes with your identity and your permissions.**

When Copilot sends an email, it sends from your account, subject to your Outlook configuration. When it retrieves a SharePoint document, it retrieves only what you can access. When it triggers a Power Automate flow, the flow runs with your connection credentials.

The model does not have its own identity. It does not have elevated privileges. It acts *as you*, with *your* rights, subject to *your* limits.

:::{figure} ../images/ch17-tool-permission-inheritance.png
:label: fig-ch17-tool-permissions
:alt: Diagram showing tool permission inheritance — user identity flows through to every tool call, tools execute with user permissions not elevated privileges, access controls from the underlying systems (SharePoint, Exchange, line-of-business apps) are enforced at execution time
:width: 80%
:align: center

Tool permission inheritance: Copilot's tool calls execute with your identity and permissions. The model has no independent access rights — it inherits yours. This is why the existing permission model in Microsoft 365 automatically governs what Copilot can do.
:::

This is why Copilot Cowork pauses before consequential actions. The tool call is ready to execute — but the system gives you the chance to review before your identity commits to the action.

::::{admonition} 🎯 Accountability Check
:class: note

**Accountability** — *we are responsible for our actions and our results.*

When Copilot executes a tool call on your behalf, the action happens under your identity. An email sent by Copilot is your email. A document created by Copilot is your document. A record updated by Copilot was updated by you. The delegation of labor does not delegate accountability. Review what Copilot does — because whatever it does, you did. In a government context, this is not just a best practice. It is a professional and legal obligation.
::::

---

## 4. The Model Context Protocol — The Emerging Open Standard

Microsoft Graph and Microsoft's built-in tools are powerful, but they are proprietary to the Microsoft ecosystem. What about connecting to everything else?

**The Model Context Protocol (MCP)** is the answer — an open standard for connecting AI systems to external tools and data sources, introduced by Anthropic in late 2024 and now adopted across the industry.

### 4.1 What MCP actually is

MCP standardizes how language models discover, invoke, and receive results from external tools and data sources. Think of it as a universal adapter — a way for any AI system to connect to any tool without custom integration code for every possible combination.

:::{figure} ../images/ch17-mcp-standard.png
:label: fig-ch17-mcp
:alt: Diagram showing MCP as an open standard layer between AI models and external systems — standardized protocol for tool discovery, invocation, and result handling, with connections to databases, APIs, file systems, and enterprise applications
:width: 80%
:align: center

The Model Context Protocol: an open standard for connecting AI systems to external tools and data. Instead of building custom integrations for every model-tool pair, MCP provides a universal protocol that any conforming system can use.
:::

The protocol specifies:
- **Tool discovery.** How a model learns what tools are available and what parameters they accept.
- **Invocation.** How a model requests a tool call with specific arguments.
- **Result handling.** How tool outputs are returned to the model in a format it can incorporate.
- **Context provision.** How external data sources can provide context alongside tool capabilities.

Microsoft has embraced MCP for Copilot extensibility. Copilot Studio supports MCP servers as a way to add custom tools and data sources to agents. This means tools built for MCP work across Copilot, Claude, and other conforming systems — you build once, connect everywhere.

### 4.2 Why this matters for the City of Bowie

MCP is the standard that lets you connect City-specific systems to Copilot without waiting for Microsoft to build a Graph connector for each one.

A custom MCP server for the City of Bowie could expose:
- **Permit lookup.** Query the permitting system for application status, inspection history, and contractor compliance — instantly surfaced when Planning or Public Works staff ask about a specific address or project.
- **Work order status.** Check the Public Works management system for open service requests, scheduled maintenance, and asset condition records.
- **Budget inquiry.** Pull current appropriation balances, encumbrances, and year-to-date expenditures from the finance system, so department managers get real-time budget data in Copilot conversations.
- **Constituent case lookup.** Retrieve case status and history from the constituent services platform, so staff can quickly orient to a resident's prior interactions.

Each of these becomes a tool that Copilot agents can call — structured requests that the MCP server executes against City systems and returns as grounded context for responses.

The protocol is open source and documented at modelcontextprotocol.io. Building an MCP server requires development work, but the standard means that work produces a reusable asset rather than a point-to-point integration.

---

## 5. Copilot Studio — Building Custom Agents with Custom Tools

Understanding the machinery lets you build on top of it. **Copilot Studio** is where that building happens.

### 5.1 What Copilot Studio provides

Copilot Studio is Microsoft's low-code/no-code platform for creating custom AI agents. These agents can be:

- **Declarative agents for Microsoft 365 Copilot.** Custom agents that appear alongside the built-in Copilot, with their own knowledge and capabilities.
- **Standalone agents.** AI assistants deployed to Teams, websites, or other channels.
- **Agent actions.** Custom tools that extend what agents can do.

The key capability for this chapter is **actions** — the mechanism for adding custom tools to agents.

### 5.2 Actions — adding tools to agents

An action in Copilot Studio is a tool that an agent can call. Actions can be:

- **Power Automate flows.** Any flow you build becomes a callable tool — query a database, update a record, send a notification, integrate with a third-party system.
- **Connector actions.** Microsoft's 1,400+ connectors (Salesforce, ServiceNow, SAP, etc.) each expose actions the agent can invoke.
- **REST API actions.** Upload an OpenAPI specification and Copilot Studio creates actions from your API endpoints.
- **MCP servers.** Connect to MCP-compliant tool servers for standardized tool access.

:::{figure} ../images/ch17-custom-agent-tools.png
:label: fig-ch17-custom-tools
:alt: Diagram of a custom Copilot Studio agent with multiple tool connections — Power Automate flows for workflow actions, Graph connectors for external data, REST APIs for line-of-business systems, and MCP servers for standardized tool access
:width: 80%
:align: center

A custom Copilot Studio agent with multiple tool types: Power Automate flows for workflow execution, Graph connectors for external data grounding, REST APIs for line-of-business integration, and MCP servers for standardized tool access. The agent reasons about when to call which tool based on user requests.
:::

### 5.3 A City of Bowie worked example — the Public Works field operations agent

Here is a concrete example of what this enables at the City of Bowie.

**The scenario:** A Public Works project manager needs quick answers during an active infrastructure project. They want to ask natural language questions and get actionable responses grounded in real data — without switching between three systems and four browser tabs.

**The agent:** A custom Copilot Studio agent for Public Works field operations, deployed in Teams.

**The tools:**

1. **Permit and compliance lookup** (Graph connector or MCP server)
   - Input: address or project number
   - Output: active permits, inspection status, compliance holds, contractor certifications
   - Example call: "What permits are active for the Northview Drive culvert replacement?"

2. **Work order status check** (REST API action connected to work order management system)
   - Input: asset ID or service request number
   - Output: work order status, assigned crew, scheduled date, materials ordered
   - Example call: "What's the status of the pothole repair request on Mitchellville Road?"

3. **Budget balance inquiry** (Power Automate flow connecting to the finance system)
   - Input: project number or budget code
   - Output: appropriation amount, encumbrances, expenditures, remaining balance
   - Example call: "How much is left in the FY2026 stormwater infrastructure budget?"

4. **Operations SOP retrieval** (Graph search scoped to Public Works document library)
   - Input: project type or topic
   - Output: relevant sections from standard operating procedures and technical specifications
   - Example call: "What's the City's standard for trench backfill compaction?"

**The interaction:**

The project manager opens Teams and types: "Hey Copilot — what permits are required for the Northview Drive project, and where does our stormwater budget stand?"

The agent reasons: this requires two tool calls — permit lookup for Northview Drive, and budget inquiry for the stormwater fund. It makes both calls, receives the results, and synthesizes a response: "The Northview Drive culvert replacement has an active grading permit and a right-of-way permit; the stormwater easement documentation is still pending from Planning. Your FY2026 stormwater infrastructure appropriation is $1.2M with $847,000 remaining after current encumbrances."

**What this changes:**

Before: The project manager checks the permitting system, then logs into the finance portal, then cross-references with the project tracking sheet. Three systems, five minutes, context switching.

After: One question, one answer, thirty seconds. The manager stays focused on the project.

::::{admonition} 🎯 Stewardship Check
:class: note

**Stewardship** — *we responsibly manage the resources entrusted to us.*

The agent does not replace the project manager's judgment. It retrieves information faster so the manager can apply judgment more often. Stewardship is not the AI answering correctly — it is the manager making better decisions about City resources because they have better information access.
::::

---

## 6. Governance — Tools Are Attack Surface

Understanding the machinery also means understanding the risks.

### 6.1 Every tool is a capability and a vulnerability

When you add a tool to an agent, you give it the ability to act. That action happens with real consequences — data is queried, records are updated, messages are sent.

**Tool permissions matter.** If a Power Automate flow runs with a service account that has elevated access, and that flow is exposed as an agent action, the agent can do things the user asking the question could not do directly. This is a permission escalation risk.

**Tool inputs can be manipulated.** If a user can phrase a question that causes the agent to call a tool with unexpected parameters, the tool executes those parameters. This is why input validation matters at the tool level, not just the prompt level.

**Tool outputs become context.** Whatever a tool returns gets incorporated into the agent's response — and potentially into subsequent reasoning. If a tool returns incorrect data, the agent propagates that incorrectness with the same confidence as correct information.

### 6.2 Government data classification applies to every tool

In a government environment, data classification adds a layer beyond typical enterprise security. City of Bowie data falls broadly into three categories:

- **Public data.** Information the City is required or permitted to share under the Maryland MPIA — approved budgets, meeting minutes, adopted ordinances, most permit records. Copilot tools that surface this data carry lower risk.
- **Internal data.** Working documents, draft policies, pre-decisional budget materials, internal communications. Not subject to MPIA disclosure while in draft form; should not be surfaced to unauthorized users through Copilot.
- **Confidential data.** Personnel records, attorney-client communications, law enforcement sensitive information, sealed records. Must not be surfaced through any Copilot tool without explicit authorization and appropriate access controls.

Every custom tool or connector deployed at the City of Bowie should be evaluated against these classifications before deployment.

### 6.3 The governance checklist

For every custom tool or connector deployed at the City of Bowie:

1. **What permissions does this tool execute with?** If it runs as a service account, does that account have least-privilege access?

2. **What data does this tool return?** Could it return internal or confidential information to users who are not authorized to see it?

3. **What actions can this tool take?** Write operations need more scrutiny than read operations.

4. **What happens if the tool fails?** Does the agent handle errors gracefully, or does it make assumptions?

5. **Who can invoke this tool?** Is it available to all Copilot users or scoped to specific roles and departments?

6. **Does this tool create MPIA exposure?** Could a resident or journalist use a Copilot interaction in a way that surfaces pre-decisional or confidential information?

::::{admonition} ⚠️ Widening the attack surface
:class: warning

Every Graph connector brings external data into Copilot's retrieval scope. Every custom action adds a new capability an agent can invoke. Every MCP server exposes new tools.

This is the point — extending Copilot's reach into City-specific systems. But extension is also exposure. The governance principle is simple: **treat every new tool like a new system being granted access to City records.** Apply the same security review, the same access control thinking, the same logging and audit requirements.

A tool that queries permitting data is useful. A tool that queries permitting data and returns it to any City employee regardless of their authorized role — including returning confidential enforcement notes alongside public permit records — is an MPIA incident and a personnel matter waiting to happen.
::::

---

## 7. Why Understanding This Makes You Better

This chapter has been technical. Here is why it was worth it.

### 7.1 You write better prompts

When you understand that Copilot retrieves before it generates, you phrase questions to help retrieval. "What did we discuss in the budget review meeting about the Parks & Recreation capital request?" is better than "What is the Parks capital budget?" — because the first question gives retrieval a relationship to follow (the meeting), while the second just gives keywords.

When you understand that the semantic index works by meaning, not keywords, you stop trying to guess exact phrases and start describing what you need in natural language.

### 7.2 You troubleshoot effectively

When Copilot gives a generic answer, you know why: retrieval found nothing specific, so the model fell back on general knowledge. The fix is not a better prompt — it is better content in the Graph, or scoping your question to a specific source.

When Copilot gives an outdated answer, you know why: stale content in the Graph ranked higher than current content. The fix is archiving the superseded ordinance or policy, not yelling at the AI.

When Copilot says it cannot do something, you know why: it does not have a tool for that action. The fix is building the tool or using a different approach.

### 7.3 You know what to build

Understanding the architecture shows you where the gaps are. If a department staff member's question cannot be answered because the data lives in an unconnected system, you know a connector is needed. If a repetitive workflow requires manual execution, you know a Power Automate flow exposed as an action would help.

The difference between "Copilot should do this" and "here is how we would build this" is exactly this architectural understanding.

---

## 8. Try This: Trace a Copilot Answer

Pick a Copilot answer you received recently that was actually useful — specific to your work, grounded in real content.

Now trace it backwards:

1. **What did you ask?** Write out your exact prompt.

2. **What content was retrieved?** Look at the citations or sources. Which documents, emails, or conversations did Copilot draw from?

3. **What relationships connected them?** How did those sources relate to your question? Were they authored by relevant people? Shared in relevant channels? Attached to relevant meetings?

4. **What made retrieval succeed?** Was it naming? Was it recency? Was it the relationship structure?

5. **What would have made retrieval fail?** If those documents had been named generically, or filed in a folder nobody uses, or superseded but not archived — would Copilot have found them?

This exercise trains you to see Copilot's answer as an output of the retrieval system, not a product of magic. Once you see it that way, you can influence the inputs.

---

## 9. Productive Struggle Problem

You are the IT and operations lead for the City of Bowie. Your department staff frequently needs quick answers during active projects that require information from three sources:

- **The City document library** — SOPs, engineering standards, adopted ordinances (currently in SharePoint)
- **The permitting and work order system** — application status, inspection records, open service requests (currently in a line-of-business application outside Microsoft 365)
- **The finance system** — project appropriations, encumbrances, and expenditure balances (currently in another line-of-business application)

Today, answering a question like "What open work orders exist in the Bowie Town Center area and where does the maintenance budget stand for those asset types?" requires three logins and manual cross-referencing.

**Your challenge:**

1. **Architecture.** Sketch the components needed to make this question answerable through a single Copilot interaction. What stays in SharePoint? What needs a Graph connector? What needs an MCP server or REST API action? What tool calls would the agent need to make?

2. **Data flow.** Trace how the question would flow through the system. What triggers retrieval? What triggers tool calls? How do the results combine into a response?

3. **Permissions.** Who should be able to ask this question? Do the work order and finance systems have their own access controls? How do you ensure the Copilot agent respects them?

4. **Failure modes.** What happens if the work order system is down? What happens if the data is stale? What happens if the agent misunderstands and queries the wrong budget code?

5. **Governance.** What approval is needed before connecting these systems to Copilot? Who owns the connector or MCP server? How is it audited? Does any of the data returned require MPIA classification review?

There is no single right answer. The quality of your thinking about *why* each component is needed and *how* they fit together matters more than the specific technology choices.

---

## Glossary

```{glossary}
Microsoft Graph
  The unified API and data layer underlying all of Microsoft 365. Organizes organizational data as a graph of nodes (people, documents, meetings, messages, sites) connected by edges (relationships like authored, attended, shared with). The foundation Copilot retrieves from.

Node
  In graph terminology, an entity or object. In Microsoft Graph, nodes include people, documents, emails, meetings, calendar events, SharePoint sites, Teams channels, and groups.

Edge
  In graph terminology, a relationship between nodes. In Microsoft Graph, edges include "authored," "attended," "shared with," "replied to," "works with," and "belongs to."

Semantic index
  The search layer that makes Microsoft Graph content findable by meaning rather than keyword. Converts content into vector embeddings — mathematical representations of meaning — enabling retrieval of conceptually similar content regardless of exact wording.

Vector embedding
  A mathematical representation of content as a point in high-dimensional space. Semantically similar content has vectors that are close together. The semantic index uses vectors to match questions with relevant content.

Retrieval-Augmented Generation (RAG)
  The architecture pattern where a language model's response is grounded in retrieved content rather than generated purely from training. Copilot uses RAG — your question triggers retrieval from the Graph, and the results ground the model's answer.

Grounding
  The process of providing retrieved content as context for a language model's response. A grounded answer is based on specific sources; an ungrounded answer is based on general training data.

Permission trimming
  The enforcement of access controls at retrieval time. When Copilot queries the Graph, it queries as you — only content you have permission to access is returned. Content you cannot see in SharePoint cannot appear in Copilot's answer.

Function calling
  The capability of a language model to emit structured requests for external actions rather than just generating text. Also called tool use. The model decides which function to call and with what parameters; a trusted execution layer performs the actual action.

Tool use
  Synonym for function calling. The ability of a language model to invoke external tools — APIs, databases, workflows — by emitting structured requests that a separate system executes.

Tool call
  A single invocation of a tool by a language model. Consists of the tool name and structured parameters. The model does not execute the tool; it requests execution.

Model Context Protocol (MCP)
  An open standard introduced by Anthropic for connecting AI systems to external tools and data sources. Standardizes tool discovery, invocation, and result handling so tools built for MCP work across multiple AI platforms.

Graph connector
  A component that ingests data from external systems into Microsoft Graph and the semantic index. Makes line-of-business or municipal data retrievable alongside Microsoft 365 content. Available as pre-built connectors for common systems or buildable custom via the connector SDK.

Copilot Studio
  Microsoft's platform for building custom AI agents. Provides no-code/low-code tools for creating agents with custom knowledge, custom actions (tools), and deployment to Teams, websites, or Microsoft 365 Copilot.

Action (Copilot Studio)
  A tool that a Copilot Studio agent can invoke. Can be a Power Automate flow, a connector action, a REST API call, or an MCP server connection.

Declarative agent
  A custom agent built in Copilot Studio that extends Microsoft 365 Copilot with specialized knowledge and capabilities while appearing alongside the built-in Copilot experience.

Context window
  The maximum amount of content (measured in tokens) that a language model can process in a single interaction. Retrieved content, conversation history, and the current prompt all compete for space in the context window.

Grounding drift
  The degradation of answer quality caused by stale content in the Graph. Superseded documents that remain indexed can be retrieved and presented as current, producing confidently incorrect answers.

Government data classification
  The categorization of City of Bowie data by sensitivity and disclosure requirements: public (MPIA-releasable), internal (working documents, pre-decisional), and confidential (personnel, legal, law enforcement). Governs how tools and connectors should restrict access to data before surfacing it through Copilot.

Maryland MPIA
  The Maryland Public Information Act — the state's open records law governing what government documents must be disclosed to the public upon request. Relevant to Copilot governance because oversharing in Microsoft 365 could expose pre-decisional or confidential records through AI retrieval before a formal MPIA review.
```

---

## Discussion

Understanding how Copilot actually works changes the relationship. You stop being a user hoping for good results and start being an operator who can diagnose problems and influence outcomes.

Consider your own work at the City of Bowie. Where are the gaps between what Copilot can answer today and what would be genuinely useful? Are those gaps in the Graph (missing content or poor organization), in tools (actions that don't exist yet), or in understanding (staff not knowing how to ask)?

::::{admonition} 📝 Discussion Guidelines
:class: note

Post your reflection in the course discussion forum. Your response should:

- Identify one question you frequently need answered in your department that Copilot currently cannot answer well. Diagnose why — is the data in an unconnected system? Is there no tool for the required action? Is the content in the Graph but poorly organized or stale?
- Propose a solution using the concepts from this chapter. Would a Graph connector help? A custom Copilot Studio action? Better SharePoint governance? Be specific about which component would address which gap.
- Address the governance implications of your proposal. What permissions would be needed? Who would own the connector or action? What are the MPIA or data classification considerations?
- Respond to at least **two peers** with substantive engagement — challenge an architectural decision, point out a governance gap, or suggest an alternative approach.

Minimum 300 words for your main post.
::::

---

## Leader's Takeaway

This chapter gave your team the technical foundation to become genuinely good at AI — not just users, but operators who understand the machinery.

Three strategic implications for City of Bowie leadership:

**First: The Graph is the asset.** Copilot's value is directly proportional to the quality of data in Microsoft Graph. Every investment in SharePoint governance, document organization, and content currency is an investment in AI capability. Conversely, every permission gap or stale document degrades AI quality across the organization. The Graph is not IT infrastructure — it is organizational intelligence infrastructure. For a city government, that intelligence directly affects the quality of services delivered to 70,000+ residents.

**Second: Graph connectors are the municipal advantage.** Microsoft 365 data is table stakes — every organization using Copilot has it. The City's advantage lies in connecting the systems that hold uniquely municipal knowledge: decades of permitting history, accumulated Public Works asset data, the Comprehensive Plan and its relationship to capital projects, constituent services case patterns. Connectors that bring this data into the Graph make Copilot uniquely valuable for City staff. This is where IT investment has outsized ROI in service delivery.

**Third: Tool governance is the discipline that makes tools safe — especially in government.** Every custom action, every Graph connector, every MCP server is a new capability — and a new exposure surface. The instinct to move fast on tools must be balanced by the discipline to govern them properly. In a government context, this is not optional: MPIA compliance, personnel record protections, and attorney-client privilege create legal obligations around data classification that private organizations do not share. The people building tools must be talking to the people who own legal, compliance, and records management.

The chapter's final message is this: understanding how Copilot works is not technical curiosity. It is operational competence. The leaders who build teams that understand the Graph, retrieval, and tools will deliver better public services than those who treat AI as a black box to prompt harder. Understanding is leverage — and in local government, that leverage ultimately serves residents.

---

:::{seealso}
**Resources for Chapter 17**

- 🔗 Microsoft Graph Documentation: [learn.microsoft.com/graph](https://learn.microsoft.com/en-us/graph/)
- 🔍 Semantic Index for Microsoft 365 Copilot: [learn.microsoft.com/microsoftsearch/semantic-index-for-copilot](https://learn.microsoft.com/en-us/microsoftsearch/semantic-index-for-copilot)

- 🔌 Graph Connectors Overview: [learn.microsoft.com/graph/connecting-external-content-connectors-overview](https://learn.microsoft.com/en-us/graph/connecting-external-content-connectors-overview)
- 🤖 Copilot Studio Documentation: [learn.microsoft.com/microsoft-copilot-studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/)
- 🧩 Model Context Protocol: [modelcontextprotocol.io](https://modelcontextprotocol.io/)
- 🔧 Function Calling Overview (Martin Fowler): [martinfowler.com/articles/function-call-LLM.html](https://martinfowler.com/articles/function-call-LLM.html)
- 🏛️ City of Bowie, Maryland: [cityofbowie.org](https://www.cityofbowie.org)
- 📋 Maryland Public Information Act (MPIA): [msa.maryland.gov/msa/mdmanual/43com/html/06pub.html](https://msa.maryland.gov/msa/mdmanual/43com/html/06pub.html)
:::
