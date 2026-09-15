---
title: "Chapter 15: Creative AI with Nano Banana"
subtitle: "Image Generation for Ideation — What It Can Do, What It Cannot, and Why the Boundary Matters"
short_title: "Creative AI with Nano Banana"
description: "Google's Nano Banana family of image generation models, accessed through Google AI Studio, offers City of Bowie communications staff and Parks & Recreation coordinators a powerful ideation tool for community event graphics, park signage concepts, city program flyers, and rapid 'what if' visual exploration — while remaining firmly outside the production art pipeline and the Microsoft 365 trust boundary. This chapter covers capabilities, limitations, prompt discipline, and the confidentiality controls that matter most."
label: ch-15-nano-banana
tags: [Nano Banana, Gemini, image generation, AI art, creative ideation, Google AI Studio, park signage, community events, city communications, mood boards, resident outreach, confidentiality, concept exploration, prompt engineering, visual AI]
---

```{admonition} Download this Chapter as PDF
:class: tip

```

# Chapter 15: Creative AI with Nano Banana

:::{figure} ../images/ch15-nano-banana-infographic.png
:label: fig-ch15-infographic
:alt: Illustrated explainer infographic showing the Nano Banana creative workflow for City of Bowie staff — from text prompt to generated concept image, with labeled examples of community event graphic exploration, park signage concepts, and resident outreach visual generation, positioned firmly in the ideation phase before professional designers finalize city-branded materials
:width: 80%
:align: center

Nano Banana gives City of Bowie communications staff and Parks & Recreation coordinators a new tool for the earliest phase of visual work — the "what if" exploration that happens before anyone commits to a direction. The output is never the deliverable. The output is how you find the deliverable faster.
:::

> *"The best way to have a good idea is to have lots of ideas."*
> — Linus Pauling

Here is a scene that plays out in City of Bowie offices regularly.

A Parks & Recreation coordinator is preparing for the Allen Pond Park Summer Concert Series. The event is six weeks out, and the team needs promotional materials that convey "community celebration" — welcoming, vibrant, and distinctly Bowie — without the generic stock-photo look that residents have come to ignore. The brief has words like "family-friendly," "local pride," and "outdoor energy" — concepts that mean different things to different people.

The coordinator has three visual directions in mind. In the old workflow, she would sketch rough ideas, describe them in a meeting, and hope the communications team can visualize what she means before anything goes to the printer. In the new workflow, she opens Google AI Studio and types:

*"A community park summer concert event flyer concept. Families spread out on a green lawn in front of a low outdoor stage at dusk. String lights overhead, food vendors in the background. The mood is warm, festive, and community-centered. No visible text, logos, or branding."*

Ninety seconds later, she has a visual. Not a finished design — she would never present this to leadership as finished work — but a *direction*. A starting point for conversation. Something that answers "do you mean this feel, or something else?" before the communications team commits hours to a concept that does not match what the coordinator had in mind.

That is what Nano Banana is for. Concept exploration at the speed of conversation. Rapid visual iteration that compresses the early ambiguity phase of creative work. A tool that helps City of Bowie staff arrive at the right direction faster, so the communications team can spend their time on what only professional designers can do: the final work that actually ships with official city branding.

This chapter is for City of Bowie communications staff, Parks & Recreation coordinators, and any department that produces visual materials for residents or City Council. It covers what Nano Banana can do, what it cannot do, where it genuinely helps, and where it must not go. The distinction between ideation tooling and production art is not a footnote. It is the operating principle that makes this tool safe to use.

::::{admonition} 🧭 Values Check — Accountability
:class: note

**We are accountable for our decisions and how we serve our community.**

Accountability in creative AI means being honest about what the output is — and what it is not. A generated image is a concept exploration tool. It is never a finished city communication, and it is never a resident-facing deliverable. When you share an AI-generated visual with a colleague, you say so. Accountability requires that everyone understands what they are looking at.
::::

---

## 1. What Is Nano Banana? The Three Model Tiers

"Nano Banana" is the internal nickname Google's developers gave to their image generation models — a playful name that stuck. The models are part of the Gemini family and are accessed through **Google AI Studio** at [aistudio.google.com](https://aistudio.google.com). You do not need to install anything. You do not need to be a developer. You need a Google account and a browser.

:::{figure} ../images/ch15-three-model-tiers.png
:label: fig-ch15-tiers
:alt: Three-tier comparison diagram showing the Nano Banana model family — Nano Banana (Gemini 2.5 Flash Image) on the left as the fast and economical option, Nano Banana 2 (Gemini 3.1 Flash Image) in the center as the faster successor, and Nano Banana Pro (Gemini 3 Pro Image) on the right as the highest quality option with best text rendering and reasoning
:width: 80%
:align: center

The Nano Banana family has three tiers — each with different tradeoffs between speed, cost, and quality. For City of Bowie creative work, the iteration workflow runs wide and cheap on the fast models, then re-renders only winning concepts on Pro.
:::

**Nano Banana (Gemini 2.5 Flash Image)**

The original. Fast, economical, good for rapid iteration. At approximately $0.039 per generated image, you can explore dozens of directions without thinking about cost. Generation takes seconds, not minutes. This is your workhorse for the "let me try five different approaches" phase.

Strengths: Speed. Cost. Good enough quality for concept exploration. Strong at understanding scene composition and style direction.

Limitations: Text rendering is unreliable. Fine details can be inconsistent. Not suitable for images that will be shown to City Council or department directors without heavy caveats about what they are seeing.

**Nano Banana 2 (Gemini 3.1 Flash Image)**

The faster successor. Released as an evolution of the original, with improved speed, better adherence to prompts, and more consistent object representation. Still economical, still fast, now with fewer quirks.

Strengths: Better consistency than the original. Improved prompt adherence. Good for iterating when you need more reliability.

Limitations: Still struggles with text rendering on anything beyond simple short labels. Still not production quality.

**Nano Banana Pro (Gemini 3 Pro Image)**

The flagship. Built on Gemini 3 Pro's reasoning capabilities, this model produces the highest-quality output with the best text rendering — around 94% accuracy on short text, according to Google's benchmarks. Supports 4K resolution output. Better at understanding complex scene descriptions with multiple elements.

Strengths: Highest visual quality. Best text rendering (though still not perfect). Strong reasoning about spatial relationships and composition. 4K output for high-resolution needs. Supports up to 14 reference images for character and style consistency.

Limitations: Slower than Flash models. More expensive (though still far cheaper than a design agency or stock image license). Text rendering, while improved, still fails on long words or unusual terms.

**Which tier when?**

The iteration workflow that works for City of Bowie staff: generate wide and cheap on Nano Banana or Nano Banana 2, explore many directions, identify the winners, then re-render only the selected concepts on Pro for higher quality output. Do not start with Pro. Start with volume.

---

## 2. Where to Find It — Google AI Studio

:::{figure} ../images/ch15-ai-studio-interface.png
:label: fig-ch15-interface
:alt: Screenshot-style diagram of the Google AI Studio interface showing the prompt input area, model selection dropdown, and generated image output panel — with labels pointing to key interface elements for first-time users
:width: 80%
:align: center

Google AI Studio is a browser-based interface — no installation required. Select your model, type your prompt, and generate. The interface is intentionally simple; the complexity is in learning to prompt effectively.
:::

**Getting started:**

1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Sign in with a Google account (personal or Google Workspace)
3. Click "Create new prompt" or use one of the template apps
4. Select the model from the dropdown (look for "gemini-2.5-flash-image" or "gemini-3-pro-image")
5. Type your prompt and click Generate

Google AI Studio includes "Build Mode" templates that let you try specific capabilities — character consistency, image editing, multi-image fusion — without starting from scratch. These are worth exploring when you are learning what the model can do.

**What it costs:**

As of this writing, Nano Banana (Gemini 2.5 Flash Image) is priced at approximately $0.039 per generated image. Nano Banana Pro is higher but still in the dollars-per-session range, not dollars-per-image-at-scale. Google offers a free tier with rate limits for experimentation.

For City of Bowie usage, the cost is negligible compared to the design time saved. A coordinator exploring ten event graphic concepts costs less than a single cup of coffee.

---

## 3. What It Is For — Ideation, Not Production

This is the most important section in this chapter. Read it carefully.

:::{figure} ../images/ch15-ideation-vs-production.png
:label: fig-ch15-ideation-production
:alt: Two-column comparison diagram showing ideation uses on the left (community event concept exploration, mood boards, park signage concepts, resident outreach direction, texture studies) with green checkmarks, versus production uses on the right (final resident-facing flyers, print-ready graphics, official city signage, City Council presentation materials) with red X marks — the division between where Nano Banana helps and where it must not go
:width: 80%
:align: center

The bright line: Nano Banana is for everything to the left of the handoff to production. Professional designers and the communications team own everything to the right. A generated image never goes to residents as finished city communication or to a printer as production art.
:::

**Nano Banana is ideation tooling, not production art.**

That sentence is the operating principle. Let me unpack what it means in the City of Bowie context.

**Ideation** is the early, exploratory phase of visual work. It is the "what if we tried this direction?" phase. It is mood boards, concept sketches, look-and-feel exploration, rapid visual brainstorming. The goal of ideation is to find the right direction before committing significant design time. Nano Banana accelerates this phase dramatically.

**Production art** is the finished work. The flyer that goes to the printer. The graphic that goes on the city's website. The signage that goes up in Allen Pond Park. The visual deliverables that carry the City of Bowie's name and official brand standards. Professional designers and the communications team own production art. Always.

**Why the distinction matters:**

1. **Quality.** Nano Banana output is good enough to explore directions. It is not good enough to represent the City of Bowie's standard of professional communication. A generated event concept has inconsistencies, artifacts, and invented details that would be embarrassing in a final resident-facing deliverable.

2. **Accuracy.** Generated images invent details. They cannot be trusted for actual signage text, specific locations, or factual program information. A generated park wayfinding concept might show a map layout that does not reflect Bowie's actual parks. Never use output as a specification for printed materials.

3. **Brand standards compliance.** City of Bowie communications must follow official brand guidelines — specific colors, fonts, logo placement, and visual standards. AI-generated images do not comply with those standards and cannot be assumed to.

4. **Resident trust.** Residents expect the City of Bowie to produce accurate, professional communications. That expectation is the foundation of public trust — and AI-generated images must never erode it.

**Where Nano Banana genuinely helps:**

::::{tab-set}

:::{tab-item} Community Event Graphics
Before the communications team commits hours to a flyer, explore the visual direction with five generated concepts in ten minutes. "Is the team thinking vibrant and colorful, or clean and elegant?" Find out before anyone opens InDesign.
:::

:::{tab-item} Park Signage Concepts
Generate visual explorations of sign style, scale, color palette, and environmental feel. "What does a welcoming entrance sign look like for a neighborhood park?" Show three interpretations before committing to a design direction.
:::

:::{tab-item} City Council Presentation Visuals
When preparing a concept for a Council presentation — a proposed park improvement, a new program launch — generate concept visuals that communicate the direction without pulling designers off active projects. The concept visual sparks conversation; the final presentation gets professional polish.
:::

:::{tab-item} Resident Outreach Direction
Explore how a campaign might feel before writing the final copy. "What does 'Bowie Cares' look like visually — what colors, imagery, and energy?" Generate options to align the team before the communications work begins.
:::

:::{tab-item} Park Improvement Concepts
Test how a public space might feel with different landscaping, seating arrangements, or facility upgrades. "What if the Allen Pond Park amphitheater had a shade canopy and expanded seating?" See the concept before committing to a planning study.
:::

:::{tab-item} Texture and Material Studies
Explore surface treatments, signage finishes, and environmental design combinations before consulting with Public Works or a design firm. "What does weathered wood signage look like next to brushed aluminum?" Generate options before requesting formal estimates.
:::

:::{tab-item} Program Concept Clarification
When a department director describes something vague, generate interpretations. "When you say 'modern but community-centered,' do you mean something like this? Or more like this?" Visual clarification beats verbal ambiguity — especially before a budget decision.
:::

::::

**The workflow in practice:**

1. Program or event brief arrives, or a planning conversation opens
2. Coordinator or communications staff generates 5-10 concept directions in Nano Banana
3. Team reviews, selects 2-3 directions worth developing
4. Professional designers develop selected directions into production-quality, brand-compliant work
5. Final materials go to residents, the City website, or print

Step 2 is what Nano Banana is for. Steps 4 and 5 are where professional designers do what they do. The tool compresses step 2 from days to minutes. It does not replace steps 4 and 5.

---

## 4. The Confidentiality Boundary — This Is Not Inside the Trust Perimeter

::::{admonition} ⚠️ STOP — Read This Before You Generate Anything
:class: danger

**Google AI Studio is NOT inside the Microsoft 365 trust boundary.**

City of Bowie employees work within a Microsoft 365 environment where Copilot respects the city's enterprise trust architecture and permission structure.

Google AI Studio is a general-purpose consumer AI tool. It is not part of the City of Bowie's enterprise environment. It does not know the city's permission structure. It does not enforce confidentiality.

**What this means:**

- **Never upload sensitive city planning documents.** Unreleased development plans, preliminary budget documents, or internal personnel communications must not be processed through any external AI tool.
- **Never upload resident personal information.** Constituent service records, permit applicant data, or any document containing personally identifiable information (PII) must remain within the city's secure systems.
- **Never upload preliminary legal or contract documents.** City contracts, legal opinions, and pre-decisional documents are confidential until officially released.
- **Never upload internal security information.** Facility layouts, security protocols, and Public Safety Communications materials are never appropriate for external AI tools.

**The safe pattern:**

Describe what you want in words. Do not upload what you have. A prompt that says "a community park event flyer with families and outdoor lighting" is safe. A prompt that attaches an actual constituent's permit application or an internal planning document is not.
::::

:::{figure} ../images/ch15-confidentiality-boundary.png
:label: fig-ch15-confidentiality
:alt: Diagram showing the confidentiality boundary between Microsoft 365 (inside the trust perimeter, containing SharePoint, Teams, Copilot, and City of Bowie data) and Google AI Studio (outside the trust perimeter, accessed via browser with no enterprise integration) — with a clear barrier between them and warning labels on what must not cross
:width: 80%
:align: center

The trust boundary is architectural, not optional. Google AI Studio operates outside the City of Bowie's enterprise security perimeter. Resident data, confidential planning documents, and internal communications stay inside the perimeter. Creative prompts go out; confidential assets do not.
:::

**Why confidentiality matters especially in local government:**

City of Bowie employees handle information that residents share in trust — permit applications, constituent service requests, planning inquiries, code enforcement concerns. Residents provide that information to receive city services, not to have it processed through external AI tools they did not consent to.

Maryland state law and federal regulations govern how government agencies handle personally identifiable information. The City's obligation is not just ethical — it is legal.

**Practical prompting for confidentiality:**

Instead of: *"Here is a resident's permit application. Generate a flyer showing what their proposed fence addition might look like."*

Do this: *"Generate a concept image showing a residential backyard with a 6-foot wooden privacy fence along the property line. Suburban neighborhood setting, well-maintained lawn. No specific address, resident information, or identifying details."*

The difference: the first prompt leaks constituent data. The second prompt describes what you need without exposing anything confidential. The generated image will not reference the actual resident — it will be a conceptual illustration that shows the *type* of improvement being discussed. That is exactly what ideation needs.

::::{admonition} 🧭 Values Check — Stewardship
:class: note

**We are stewards of the public trust and the resources our community entrusts to us.**

Every prompt you type is a choice about what to expose. The tool has no judgment about what is confidential. You have that judgment. Stewardship means using it — every time, without exception, even when you are in a hurry and the Council meeting is tomorrow morning and it would be so much easier to just upload the file.
::::

---

## 5. The Real Limitations — What Actually Goes Wrong

Nano Banana is powerful, but it has specific failure modes that every City of Bowie staff member using it needs to understand. These are not theoretical concerns — they are observable, repeatable behaviors that will bite you if you do not plan for them.

:::{figure} ../images/ch15-text-failure-modes.png
:label: fig-ch15-text-failures
:alt: Grid of six example images showing common Nano Banana text rendering failures — garbled words on signage, invented copyright notices, fabricated organization names, nonsense text on document props, unwanted captions, and inconsistent letter spacing — each with a label describing the failure mode
:width: 80%
:align: center

Text rendering is the #1 failure mode. The model attempts to write what it thinks you want — and frequently invents, garbles, or hallucinates text that was never requested.
:::

### Text Rendering Fails

This is the number one problem. Nano Banana struggles with text, especially:

- **Long words.** Anything beyond 6-7 characters becomes unreliable. "REGISTRATION" becomes "REGISTRATON." "RECREATION CENTER" becomes "REKREATION CENTER." "CONSTITUENT SERVICES" becomes "CONSTITUENT SERVISES." This is not occasional — it is the default behavior. Expect every long word to fail unless proven otherwise.

- **Uncommon terms.** Government and municipal vocabulary that the model has not seen frequently in training data becomes unrecognizable. "DRAYAGE" may render as "DRAYGE." More importantly, department names and city-specific program names will fail. "PARKS & RECREATION" may become "PARKS & RECRATION" or worse. General consumer vocabulary ("WELCOME," "OPEN," "INFO") works. Municipal government vocabulary often does not.

- **Any text on props.** If your generated image includes a clipboard, a document, a computer screen, a poster, or any surface that could have text on it, the model will put text there — and that text will be gibberish. Generated documents show words that have no meaning in any language. In one test, a generated image of a city program flyer showed a document prop with the heading "COMUNITY PROGRAMES INFORMATON" — a creative interpretation of "Community Programs Information" that would embarrass anyone who shared it with a resident.

- **Numbers, dates, and addresses.** Event dates, times, and addresses are equally unreliable. A park event flyer concept might display "June 14, 2025" as "Jun 14 2O25" or "Jne 14-25." Room numbers, hall designations, and any numerical labeling will require post-generation editing or careful prompt exclusion.

### Invented Attribution

This is a real concern. When generating images, Nano Banana sometimes invents:

- **Fabricated copyright notices.** "© 2024 City of Bowie Recreation Department" stamped on an image — except the exact phrasing and context are fabricated. You did not request that copyright claim. The model sees that professional materials often have copyright notices, so it adds one.

- **Fake website URLs.** "www.bowiemaryland.gov/events" appearing on generated signage — this could be a real URL or a subtly incorrect one. Either way, it creates confusion and should never appear in materials shared with anyone. A URL in a generated image could direct someone to an incorrect or nonexistent page.

- **Invented program names and logos.** In observed cases, generated images include fabricated logo placements and program name variations for real organizations. A city seal that looks almost right — but is not — is worse than no seal at all, because it creates confusion about what is official.

- **Fake accreditations and certifications.** Generated images of professional settings sometimes include fabricated certification badges, award logos, or association marks. These do not exist and should never appear in anything shown to residents or leadership.

### Unwanted Captions and Labels

The model often adds descriptive text nobody asked for:

- "A community event flyer for a local park" as a caption along the bottom of an image
- "Concept design" watermarked across the image
- Explanatory labels pointing to features in the image

These additions make the output unusable without editing — and editing AI-generated images is its own skill set.

### Dimensional and Geographic Unreliability

Generated images look plausible but are not accurate:

- A "Allen Pond Park" prompt will not produce an image of the actual park — it will produce a generic park setting
- Spatial relationships between structures may be physically impossible
- Any generated image purporting to show a specific Bowie location is an invention, not documentation

**Never use a generated image to represent a specific Bowie location, facility, or program as if it were photography.** It is a visual direction concept, not documentation.

### The Prompt Discipline That Fixes This

After extensive use, the following prompt structure produces dramatically cleaner results:

**Explicit text control:**

End every prompt with explicit instructions about text:

*"...the only text visible in the image should be [LIST EXACT SHORT LABELS]. Do not include any other text, copyright notices, URLs, logos, watermarks, captions, or readable content on any props, documents, screens, or surfaces."*

**Keep text short:**

Any text you do want should be 1-3 SHORT common words:

- ✅ "WELCOME" (one word, 7 letters)
- ✅ "OPEN DAILY" (two short words)
- ✅ "INFO" (one word, 4 letters)
- ❌ "PARKS & RECREATION DEPARTMENT" (too long, will garble)
- ❌ "CONSTITUENT SERVICES" (will fail)
- ❌ "ALLEN POND PARK AMPHITHEATER" (will become nonsense)

**Forbid props that invite text:**

If you do not need documents, clipboards, or screens in the image, explicitly exclude them:

*"...no visible documents, papers, screens, signage with text, or readable materials in the scene."*

---

## 6. Prompt Structure for Visual Work

Prompting for images is different from prompting for text. When you ask a text model for help, you are having a conversation. When you ask an image model for a visual, you are describing a scene.

:::{figure} ../images/ch15-prompt-anatomy.png
:label: fig-ch15-prompt-anatomy
:alt: Annotated prompt example showing the six components of an effective image generation prompt — Subject, Setting, Style, Palette, Composition/Lighting, and Aspect Ratio — each highlighted and labeled with examples relevant to city communications and community event design
:width: 80%
:align: center

The anatomy of an effective visual prompt: Subject → Setting → Style → Palette → Composition/Lighting → Aspect Ratio. Each element adds control. Missing elements leave the model to guess.
:::

**The six components:**

```{list-table} Visual Prompt Components
:header-rows: 1
:label: table-ch15-prompt-components

* - Component
  - What It Controls
  - Example
* - Subject
  - What is the main focus of the image?
  - "A community park summer concert event with families on a lawn in front of an outdoor stage"
* - Setting
  - Where is this? What surrounds it?
  - "A suburban Maryland park at dusk, trees lining the perimeter, string lights overhead"
* - Style
  - What is the visual treatment?
  - "Warm photographic style" or "Illustrated poster art" or "Clean graphic design concept"
* - Palette
  - What colors dominate?
  - "Warm greens and golds with soft evening sky blues"
* - Composition
  - Where is the camera? What is the lighting?
  - "Wide establishing shot from slightly elevated angle, golden hour natural lighting"
* - Aspect Ratio
  - What shape is the final image?
  - "Portrait format for flyer" or "16:9 landscape for presentation" or "Square for social media"
```

**Example prompt structure:**

*"[SUBJECT] A community outdoor concert event in a suburban park, with families sitting on blankets and lawn chairs in front of a small outdoor stage. Musicians on stage. [SETTING] A well-maintained public park at dusk, mature trees in the background, string lights strung between poles, a few food vendor tents visible in the background. [STYLE] Warm, photorealistic, celebratory atmosphere. [PALETTE] Warm golden tones, deep greens, soft twilight sky in blues and purples. [COMPOSITION] Wide shot showing the audience and stage together, natural lighting with string light accents. [ASPECT] Portrait format. [TEXT CONTROL] No visible text, logos, signage, banners, copyright notices, URLs, or readable content on any surface."*

**Common mistakes:**

- **Too vague.** "A nice event flyer" gives the model nothing to work with. What kind of event? What setting? What mood?

- **Asking for specific Bowie locations by name.** The model will not produce an accurate image of Allen Pond Park. Describe the *type* of setting you want instead.

- **Forgetting text control.** If you do not forbid unwanted text, you will get unwanted text.

- **No style direction.** Without a style cue, the model picks one — and it may not be what you wanted.

---

## 7. The Iteration Workflow — Generate Wide, Refine Narrow

:::{figure} ../images/ch15-iteration-ladder.png
:label: fig-ch15-iteration
:alt: Vertical workflow diagram showing the iteration ladder — starting at the bottom with "Generate 10 concepts on Nano Banana (fast, cheap)" rising through "Review with team, select 3 directions" then "Refine selected concepts on Nano Banana 2" then "Final concepts on Nano Banana Pro" and ending at the top with "Professional designers take over for brand-compliant production"
:width: 80%
:align: center

The iteration ladder: start wide and cheap, narrow as you climb, hand off to professional designers at the top. The tool accelerates exploration. Humans own execution and brand compliance.
:::

**Step 1: Generate Wide on Nano Banana**

Start with 10-15 concepts on the fast model. Try different directions. Do not self-edit at this stage — the point is volume. A concept that looks strange in your head might look interesting when you see it.

Prompt variations to try:
- Different color palettes for the same event concept
- Different lighting moods (bright and celebratory vs. warm and intimate)
- Different central features (stage focus vs. crowd energy vs. community gathering)
- Different graphic styles (photorealistic vs. illustrated poster vs. clean graphic)

Cost for 15 generations: roughly $0.60. Time: under 10 minutes.

**Step 2: Review and Select**

With your team (or alone if you are the program lead), review the generated concepts. Most will be wrong. Some will be interesting. A few will spark a direction worth pursuing.

Select 2-3 directions to develop further.

**Step 3: Refine on Nano Banana 2**

For your selected directions, refine the prompts based on what you learned. Be more specific. Add the details that were missing. Generate 3-5 variations of each direction.

**Step 4: Final Concepts on Nano Banana Pro**

For the 1-2 concepts you want to show to the team or use in a planning conversation, re-generate on Pro for higher quality output. Use the refined prompts from Step 3.

**Step 5: Professional Designer Handoff**

The winning concept goes to the communications team or a professional designer for actual development. The generated image is reference material — visual direction, not production art. The designer will produce brand-compliant, print-ready materials that go to residents.

**What you have at the end:**

- A clear visual direction agreed upon by the team
- Reference images that communicate that direction
- Significantly less time spent on exploration
- Designers free to focus on execution, not guessing what you meant

**What you do not have:**

- A finished flyer ready to post on the city website
- Brand-compliant graphics ready for print
- Materials that can be presented as official City of Bowie communications

The distinction matters. The iteration workflow produces *direction* — the answer to "which way should we go?" It does not produce *deliverables* — the polished, brand-compliant work that serves residents. That gap is filled by professional designers, and it is not a small gap. The translation from "AI-generated concept that captures a direction" to "official city communication that residents trust" is where design skill and brand stewardship live.

---

## 8. Integrating with the City of Bowie Creative Workflow

:::{figure} ../images/ch15-booth-concept-workflow.png
:label: fig-ch15-workflow
:alt: Horizontal workflow diagram showing how Nano Banana integrates with City of Bowie creative process — Program or Event Brief, AI Concept Exploration (10-15 concepts in Nano Banana), Team Review and Direction Selection, Designer Development with Brand Standards, Internal Review, Resident-Facing Publication — with the AI phase clearly bounded and labeled as ideation only
:width: 80%
:align: center

Nano Banana slots into the City of Bowie creative workflow at the concept exploration phase — after brief intake, before design development. It compresses a multi-day exploration into a morning's work.
:::

**Where it fits:**

| Workflow Phase | Who Does It | Nano Banana Role |
|----------------|-------------|------------------|
| Brief intake and planning | Program lead, Communications | None — understand the need first |
| Concept exploration | Program lead, Coordinator | **Primary use** — generate visual directions |
| Direction selection | Department team | Review generated concepts |
| Design development | Communications, Professional designer | Reference only — AI concepts as direction |
| Brand standards review | Communications director | None — reviewing human work |
| Internal approval | Department director | None — reviewing human work |
| Resident-facing publication | Communications | None — publishing official materials |
| Future revision cycles | Designer | Optional — quick visual exploration of new directions |
| Final production | Print vendor, Web team | **Never** — production is human work |

**Communication conventions:**

When sharing a generated concept internally:
- "Here's an AI-generated concept for visual direction — this is ideation, not a deliverable"
- Include the prompt used so others can refine it
- Do not present it as design work — it is exploration work

When using it as reference for professional designers:
- "Here's the visual direction we're going for"
- Expect the designer to interpret and improve, not replicate
- The generated image is a starting point, not a target

---

## 9. What Nano Banana Cannot Do — Honest Limits

:::{figure} ../images/ch15-creative-workflow-integration.png
:label: fig-ch15-creative-integration
:alt: Venn diagram showing the overlap and boundaries between AI capabilities and professional designer capabilities — AI excels at rapid exploration, volume, and visual direction-finding; humans excel at judgment, brand accuracy, production quality, legal compliance, and resident trust; the overlap zone shows direction finding and concept refinement
:width: 80%
:align: center

The capabilities Venn diagram: AI tools and professional designers have different strengths. Effective city communications teams use both — AI for speed and volume in exploration, humans for judgment, brand standards, and quality in execution.
:::

::::{admonition} 🧭 Values Check — Responsiveness
:class: note

**We respond to our community's needs with care and accuracy.**

Responsiveness in the context of AI tools means recognizing that the tool's limitations are not failures to be frustrated by — they are boundaries to be understood. A coordinator who sees their AI-generated event concept fail to render text correctly should not feel like the tool failed them. The tool worked exactly as expected. Understanding its limits is part of using it well.

More importantly: responsiveness applies to residents. A resident who sees an AI-generated image used in an official city communication without professional polish deserves better. The standard for city communications is accuracy and professionalism — and AI ideation tools do not meet that standard on their own.
::::

**Cannot do:**

- **Production-ready graphics.** Output is not print-ready and should not go to print vendors, the city website, or any resident-facing channel. Resolution, color accuracy, and detail quality are insufficient for official communications.
- **Brand standards compliance.** Cannot reproduce the City of Bowie's official colors, fonts, logo, or visual identity standards accurately. Every official city communication must comply with established brand guidelines.
- **Accurate location representation.** Cannot produce accurate images of Allen Pond Park, the Bowie Community Center, or any specific Bowie facility. Generated images of named locations are inventions, not documentation.
- **Reliable text.** Long words, government terms, and department names fail frequently. Text rendering remains the model's most consistent weakness.
- **City logos and seals.** Cannot reproduce the City of Bowie's official seal or logo accurately or appropriately. Generated logo approximations must never appear in shared materials.
- **Code and policy compliance.** Cannot know ADA requirements, city style guide rules, or communications policy constraints. A generated design may violate requirements the model has no way of knowing.
- **Photography replacement.** Cannot replace actual photos of Bowie parks, facilities, or community events. Generated "locations" are inventions, not documentation.
- **Final resident communications.** Cannot produce the polished, brand-compliant materials that residents receive. The quality and accuracy gap is immediately visible to anyone who reviews them professionally.

**Can do, with caveats:**

- **Visual concept exploration** — but requires review and selection by communications professionals
- **Mood and tone communication** — but is not a finished mood board
- **Direction finding** — but the direction must be executed by designers following brand standards
- **Rapid iteration** — but quality and compliance require professional polish
- **Visual brainstorming** — but judgment about what is appropriate for city communications still requires humans

::::{admonition} 🧭 Values Check — Pride
:class: note

**We take pride in serving Bowie with professionalism and excellence.**

Pride means knowing what each tool is for. Nano Banana is excellent at ideation. Professional designers are excellent at execution and brand stewardship. Using each for what it does well — that is how we serve residents well. Using AI output as a resident-facing deliverable is not faster service. It is lower quality presented as official communication. That is the opposite of the pride we take in representing Bowie.
::::

---

## 10. Try This — A Complete Ideation Session

::::{admonition} 🧪 Try This: AI-Assisted Community Event Concept Exploration
:class: tip

**Time required:** 30-45 minutes

**What you need:**
- A browser and a Google account
- Access to Google AI Studio ([aistudio.google.com](https://aistudio.google.com))
- A fictional brief (create one, or use the example below)

**Fictional brief:**

*"The City of Bowie Parks & Recreation Department is launching its annual Fall Family Festival at Allen Pond Park. The event runs Saturday, October 18, 2025 from 11 a.m. to 5 p.m. Family activities include hayrides, a pumpkin patch area, live music, food vendors, and a kids' craft tent. The visual tone should feel welcoming, community-centered, and distinctly autumnal — not corporate or generic. The communications team needs concept direction before beginning the official flyer design."*

---

**Step 1: Generate Initial Concepts (Nano Banana)**

Open Google AI Studio. Select the Gemini 2.5 Flash Image model.

Generate 5 different concept directions using different approaches:

1. **Warm autumn gathering approach:** *"A community fall festival in a suburban park. Families with children near hay bales and pumpkins. Mature trees showing autumn color in the background. Warm afternoon light. Food tents visible in the distance. Festive and welcoming atmosphere. No text, signage, logos, or branding visible."*

2. **Kids-centered approach:** *"Children at an outdoor autumn craft activity table under a tent. Parents nearby. Colorful craft supplies and finished crafts on the table. Fall-colored trees in background. Warm, sunny day. Joyful atmosphere. No text or logos."*

3. **Community panorama approach:** *"Wide shot of a fall community festival in a park. Crowd of diverse families on a lawn. A small outdoor stage with musicians at one end, pumpkin and craft activity areas at the other. Fall foliage all around. Aerial perspective showing the whole event layout. No text."*

4. **Food and harvest approach:** *"A farmers market and festival vendor row in a fall park setting. Tents with seasonal produce, apple cider, baked goods. Families browsing. Hay bales for seating. Rich autumn colors throughout. No text or logos."*

5. **Illustrated poster style approach:** *"A stylized illustrated poster concept for a fall community festival. Bold autumn colors — deep oranges, reds, and golds. Simple illustrated icons: a pumpkin, a leaf, a family silhouette, a music note. Clean graphic design aesthetic. Vintage Americana poster feel. No text."*

---

**Step 2: Review and Select**

Look at your five generated concepts. Ask yourself:

- Which one best captures "welcoming, community-centered, and distinctly autumnal"?
- Which one would work as the visual foundation for an official city flyer?
- Which one feels most like Bowie — not generic?

Select 2 directions to refine.

---

**Step 3: Refine Selected Concepts**

For your selected directions, generate 3 variations each, refining the prompt based on what you learned:

- Add details that were missing
- Adjust elements that did not work
- Try different color variations
- Explore different framing options

---

**Step 4: Final Quality on Pro (Optional)**

If you have access to Nano Banana Pro, re-generate your best 1-2 concepts for higher quality output.

---

**Step 5: Document Your Process**

Write a brief note:
- Which concepts resonated and why
- What prompt adjustments produced better results
- What you would hand to the communications team as visual direction

---

**Debrief questions:**

1. How did the AI-generated concepts compare to what you imagined before generating?
2. Did any concept surprise you in a useful way?
3. What limitations did you encounter?
4. How would you describe the "direction" to a professional designer based on what you generated?
5. What would you do differently next time?
::::

---

## 11. Productive Struggle Problem

::::{admonition} 🔨 Productive Struggle: The Abstract Program Brief
:class: important

**Scenario:**

The City Manager's office has requested a visual campaign for a new city initiative called "Bowie Forward" — a community engagement effort tied to the city's 2026 strategic planning process. The brief describes the campaign as intended to convey "optimism," "community ownership," and "Bowie's next chapter."

When asked for visual references, the requesting department says: "We don't have any — that's why we're asking you to explore directions."

**Your challenge:**

Using Nano Banana, generate a range of concept directions that might communicate "optimism," "community ownership," and "Bowie's next chapter" in a city communications context. You have 45 minutes.

**The struggle points:**

1. How do you translate abstract civic concepts into visual prompts?
2. What visual elements could represent "community ownership" without being clichéd (no generic handshakes or abstract globe imagery)?
3. How do you generate enough range that decision-makers see genuinely different directions?
4. How do you avoid generating anything that looks like it belongs to a different city?

**Constraints:**

- Do not include any city logos, seals, or official marks (the model will garble them)
- Do not include text in the generated images
- Generate at least 8 distinct concept directions
- Document your prompt evolution as you learn what works

**What to submit to your team:**

- Your 3 best concepts with the prompts that generated them
- A brief explanation of how each concept communicates "Bowie Forward"
- Notes on what prompt strategies worked and what failed
- Honest assessment: which concept would you recommend for the communications team to develop, and why?

**Why this is hard:**

Most briefs are concrete: "we need a flyer for the summer concert series" or "we need a graphic for the permit office waiting room." This brief asks you to make an idea visible — to find an image for values and aspirations that different people understand differently. That is a translation challenge that AI cannot do alone. You have to figure out what "Bowie Forward" might look like, then describe it well enough for the model to generate it, then evaluate whether it actually communicates what the brief asked for.

The productive struggle is the translation — from abstract civic concept to visual prompt to generated image to professional judgment about whether it worked.
::::

---

## Glossary

```{glossary}
Nano Banana
  Internal nickname for Google's Gemini-based image generation models. The family includes Nano Banana (Gemini 2.5 Flash Image), Nano Banana 2 (Gemini 3.1 Flash Image), and Nano Banana Pro (Gemini 3 Pro Image).

Google AI Studio
  Browser-based interface for accessing Google's AI models, including the Nano Banana image generation family. Accessible at aistudio.google.com with a Google account.

Ideation
  The early, exploratory phase of creative work where multiple directions are explored before committing to development. Nano Banana accelerates ideation; it does not replace professional design and production.

Production Art
  Finished creative work that goes to residents, to print, or to the city website. Production art is created by professional designers following official brand standards. AI-generated images are never production art.

Text Rendering
  The ability of an image generation model to include readable text in generated images. Nano Banana's text rendering is unreliable, especially for long words and government/municipal terms.

Prompt
  The text description given to an image generation model to specify what image should be created. Effective prompts include subject, setting, style, palette, composition, and text control elements.

Character Consistency
  The ability of an image model to maintain the appearance of a character or object across multiple generated images. Useful for generating consistent visual concepts across a campaign.

Multi-Image Fusion
  The capability to combine elements from multiple input images into a single generated output. Useful for placing objects into scenes or combining visual elements.

Brand Standards
  The official visual identity guidelines for the City of Bowie, including approved colors, fonts, logo usage, and layout conventions. All resident-facing and official city communications must comply with brand standards. AI-generated images do not comply automatically.

Trust Boundary
  The security perimeter that defines what data an AI tool can access and what confidentiality protections apply. Google AI Studio operates outside the Microsoft 365 trust boundary that protects City of Bowie's Copilot usage.

SynthID
  Google's invisible digital watermarking technology applied to AI-generated images, allowing them to be identified as AI-created or edited.
```

---

:::{seealso}
**Resources for Chapter 15**

- 🎨 Google AI Studio (access Nano Banana models): [aistudio.google.com](https://aistudio.google.com)
- 📖 Gemini API Image Generation Documentation: [ai.google.dev/gemini-api/docs/image-generation](https://ai.google.dev/gemini-api/docs/image-generation)
- 🔒 Google AI Studio Terms of Service: [ai.google.dev/terms](https://ai.google.dev/terms)
- 🛡️ SynthID Digital Watermarking: [deepmind.google/science/synthid](https://deepmind.google/science/synthid/)
- 📋 OpenRouter (alternative API access): [openrouter.ai](https://openrouter.ai)
:::

---

## Discussion Questions

1. **The ideation boundary.** Where exactly does ideation end and production begin in the City of Bowie's communications workflow? How would you communicate to a new department coordinator that AI-generated images are for exploration, not for distribution to residents?

2. **Confidentiality in practice.** A colleague is rushing to prepare for a Council presentation and asks if they can "just upload the constituent's permit photos to get better AI concept images." How do you respond? What is the principle, and how do you make it practical under time pressure?

3. **Quality judgment.** You generate a park signage concept that looks good, but something feels off. It would take time to explain to the communications team what you want; the generated image seems close enough for an internal meeting. What is the right call? What criteria should guide the decision?

4. **Resident communication.** A resident asks to see what their proposed park improvement would look like, and someone suggests sharing an AI-generated concept to give them an idea. What are the risks? How would you explain why this is not appropriate?

5. **Text failure workarounds.** Your event concept needs to show "PARKS & RECREATION DEPT" on a sign, but Nano Banana keeps garbling it. What options do you have? When is it worth fighting the tool, and when is it better to work around it?

6. **Brand integrity.** You generate a concept that looks like it could represent Bowie — but the generated city seal in the corner is clearly wrong. A colleague thinks it looks "close enough" for an internal slideshow. Where is the line, and why does it matter even for internal use?

---

## Leader's Takeaway

Nano Banana gives City of Bowie staff a valuable new tool for the ideation phase of communications and program planning — but only if the boundaries are clear and the discipline is maintained.

**What leaders need to ensure:**

1. **The ideation/production boundary is understood.** Every staff member using this tool needs to understand that AI-generated images are exploration tools, not deliverables. This is a professional and legal standard, not a guideline.

2. **Confidentiality discipline is enforced.** Google AI Studio is outside the Microsoft 365 trust boundary. Resident personal information, confidential planning documents, and internal security materials must never be uploaded or described in detail. Prompts describe general concepts; they do not expose confidential city information.

3. **Professional designers and communications staff are not bypassed.** The value proposition is clear: AI handles rapid visual exploration so the communications team can focus on brand-compliant execution. The tool does not replace professional design skill or brand stewardship. It accelerates finding the direction that those skills will develop.

4. **Brand standards are non-negotiable.** No AI-generated image goes to residents, print vendors, or the city website without professional review and brand compliance verification. The City of Bowie's communications standards exist to maintain public trust.

5. **Prompt skills are developed deliberately.** Effective prompting is a learnable skill. Invest in a few hours of experimentation so staff know what works and what fails — before they need the tool for a real project.

**The opportunity:**

A Parks & Recreation event that used to require waiting for the communications team's availability can now be explored visually in hours, giving the team a clear direction before the design work begins. A department director can see three concept directions for a new program before anyone has committed design time. A planning conversation that used to involve lengthy verbal descriptions can be anchored in visual references generated in minutes.

The time saved is real. The risk is manageable with clear discipline. The combination gives City of Bowie staff a better path from "we need something visual" to "here's what we're going for" — so the professionals can do their best work.

Use the tool. Respect the boundaries. Keep humans in the loop where humans belong — and in city government, that is especially where residents are involved.
