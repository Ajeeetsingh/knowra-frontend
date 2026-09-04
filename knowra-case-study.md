# Knowra — Ask your company's documents a question, get a cited answer

**A concept-to-prototype project: product design, design systems, and front-end engineering for an internal AI knowledge assistant.**

---

## Quick-copy blocks (paste these straight into Claude Design)

These two blocks are self-contained — no need to pull from the long case study below unless you want more detail for a project detail page.

### Block 1 — Portfolio card / thumbnail (short teaser, shown before someone clicks in)

> **Knowra**
> Ask your company's documents a question. Get an answer you can verify down to the sentence.
> *Concept AI knowledge assistant — 16-section marketing site + 13-screen product prototype, built around one rule: no source, no claim.*
> Tags: Product Design · Design Systems · Front-End Engineering

### Block 2 — About-page connecting thread (ties this project to my day job)

> I build things that make AI outputs something you can actually check, not just trust blindly. In my day job, that means engineering pipelines that turn legal land descriptions and hand-marked assessor parcel maps into structured, verifiable data — computer vision isolates what matters on a scanned map, and a vision-language model reads it back precisely, boundary call by boundary call. Knowra grew out of the same instinct applied to a different problem: if an employee asks a company AI assistant a question, how do you make that answer as checkable as a boundary call on a parcel map? Different domain, same principle — every output should point back to exactly where it came from.

---

## The full case study (for a project detail page)

## The problem, in plain terms

Every company has the same quiet productivity leak: the answer to "how many vacation days do I have left" or "what's our remote work policy" already exists — buried in a PDF on a shared drive, or in the head of whoever in HR answered it last time. Two bad things happen as a result:

- People ask the same question to a human, over and over, instead of a document that already has the answer.
- When people turn to a general AI chatbot instead, it confidently answers anyway — even though it's never actually read the company handbook.

**Knowra is my answer to that problem**: an internal assistant employees can ask questions in plain English, that answers *only* from a company's own uploaded documents, and shows its work — every claim is backed by a numbered citation that opens the exact source page.

---

## What I designed and built

This wasn't a single screen — it was a full product surface, designed and built end-to-end:

- **A 16-section public marketing site** — explaining what the product is, how it works, and who it's for, with full light/dark theming and responsive layouts.
- **A 13-screen working product prototype** — chat interface, document upload, collections, an admin console with role management, and three analytics dashboards (usage, knowledge coverage, errors).

Everything was hand-built in HTML/CSS/JS with no framework — which forced a level of discipline around the design system that frameworks often paper over.

---

## The part I'm proudest of: making "permission-aware AI" visible

The hardest thing to design in this space isn't the chat window — it's **trust**. How do you show someone, in five seconds, that an AI assistant won't leak information they're not allowed to see?

My solution: a live role-switcher on the landing page. You ask the *exact same question* — "What did we spend on contractors last quarter?" — as four different roles, and watch both the answer **and** the visible source list change in real time:

| Role | What happens |
|---|---|
| Employee | Politely declines — no authorized source exists for this question |
| HR | Gets headcount, but financial figures stay locked |
| Finance | Gets the full number, cited to the exact spreadsheet |
| Admin | Gets the number *and* a full audit trail of who else can see it |

This single interaction does more to explain "retrieval-based access control" than a paragraph of text ever could — and it's the kind of thing that makes a portfolio piece memorable instead of forgettable.

The same philosophy carries through the whole product: click a citation number, and a source viewer slides open scrolled to the exact highlighted sentence the answer came from. No source, no claim — if nothing authorized backs an answer, Knowra says so instead of guessing.

---

## The design system underneath it

Rather than hard-coding colors everywhere, the entire visual language — light mode, dark mode, every button radius, every shadow — runs on roughly 30 CSS custom properties set once at the root. Flip a single `theme` value and the whole product re-themes, including derived colors (tints, washes, borders) computed automatically from the base accent via `color-mix()`.

**Why this matters to a hiring manager or client:** it's the difference between a pretty static comp and a system that's actually maintainable — the same instinct that keeps a real production codebase from becoming a pile of one-off hex codes.

---

## Responsive engineering, not just "it also works on mobile"

- One implementation per screen — no separate mobile version to maintain.
- Fluid typography via `clamp()` instead of a stack of breakpoint overrides.
- Tables collapse into stacked cards below 760px; the app sidebar becomes an off-canvas drawer; the chat view collapses to a single pane with the conversation list as a slide-over.
- Verified across five breakpoints from 390px up to 1280px+.

---

## What this project demonstrates

If someone lands on this case study wondering "can this person actually do the job," here's the honest translation:

- **Product thinking** — identifying the real trust problem (permissions, hallucination) and designing the *interaction*, not just the screen, that solves it.
- **Systems-level design** — a token-driven theme architecture that scales, instead of one-off styling.
- **Front-end craft** — hand-built, dependency-free, responsive, accessible interaction patterns (accordions, tabs, reveal-on-scroll, modals) done properly — fail-safe by default, respecting `prefers-reduced-motion`, keyboard-focusable.
- **Honesty as a design value** — the product deliberately avoids fake compliance badges, fake pricing, and fake urgency. That restraint is itself a signal of how I'd represent a real client's product.

---

## A note on how to present this

A few suggestions for the portfolio page itself:

1. **Lead with the role-switcher as an embedded interactive demo** (or a short screen-recording GIF), not a static screenshot — it's the single most convincing 10 seconds of the whole project.
2. **Show the citation-click interaction next** — it's the second-most tangible "oh, that's clever" moment.
3. Keep the write-up above the fold short; link out to "see the full prototype" for people who want to click through all 13 screens.
4. If you didn't build this for a real client, say so plainly (as the copy above does) — "self-directed concept project" is a completely respectable, common portfolio category, and it reads as more credible than implying client work that wasn't.

---

*Want a shorter one-paragraph version for a portfolio card/thumbnail, or a version tailored to a specific job description you're applying to? Happy to adapt this.*
