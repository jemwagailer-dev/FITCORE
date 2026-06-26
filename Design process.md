# Fitcore — Design Process

> A behind-the-scenes account of how this project was built — decisions made, things changed, and what I'd do differently. This is the document hiring managers actually want to read.

---

## How This Project Started

This began as a standard UI design brief from Unified Mentor: build a fitness app with onboarding, goal selection, workout recommendations, and progress tracking. The brief was well-structured but positioned as a UI exercise — design the screens, pick some colours, build a prototype.

I decided to treat it differently.

The fitness app market is one of the most saturated categories in mobile. Building another "nice-looking" fitness UI without asking why it would exist — who it's for, what problem it actually solves, why someone would choose it over Strava or Nike Training Club — felt like the wrong kind of project to put in a portfolio.

So I started with research.

---

## Phase 01 — Research (2 weeks)

### What I did
- Analysed 8 competitors in detail: Strava, Nike Training Club, MyFitnessPal, Fitbod, Apple Fitness+, Freeletics, Future, Couch to 5K
- Looked at retention data across the category
- Identified the most common reason users stop using fitness apps

### The finding that changed everything

Most fitness apps lose users not because they lack features — but because they punish normal human inconsistency.

68% of users quit because the plan felt unrealistic. 54% abandoned after missing a day and feeling guilty about a broken streak. 43% found no way back after a gap.

The entire product strategy flowed from this: **Fitcore is designed around the moment most apps fail — when a user comes back after a week off.**

### What I changed
I initially planned to build a feature-rich app. After research, I cut scope deliberately. No social feeds. No nutrition tracking. No leaderboards. Every feature that could create comparison or guilt was removed. This was a harder decision than it sounds — it meant arguing against features that competitors have and users expect.

### What I'd do differently
I'd interview real users earlier. The personas I built are psychologically informed but they're not based on primary research conversations. If I were doing this for a live product, I'd run at least 8 user interviews before writing a word of copy.

---

## Phase 02 — Strategy (1 week)

### What I did
- Defined the product vision, mission, and UVP
- Chose the North Star Metric (Weekly Active Training Rate)
- Built the retention strategy and habit loop model
- Defined the 15 KPIs across activation, engagement, retention, and business

### The hardest decision

Choosing what *not* to measure. The temptation in product design is to track everything — DAU, time in app, session frequency. I deliberately excluded these because optimising for them would lead to dark pattern design decisions (more notifications, addictive loops, artificial urgency).

If the product works, users train 2–3 times a week and think about the app less, not more. That's counterintuitive for a metrics-driven team but it's the right outcome for the user.

### What I'd do differently
Build the metrics framework before the design system, not alongside it. I ended up reworking some component designs when I realised they were optimising for the wrong outcome.

---

## Phase 03 — Design System (2 weeks)

### What I did
- Built a full Material 3 design system adapted for the Fitcore brand
- 18 documented sections from colour roles to motion tokens
- Fitcore-specific components: energy check-in selector, achievement badges
- Full WCAG 2.1 AA compliance documentation from the start

### Colour decisions

The brief suggested navy and orange. I kept both but interrogated them:

- **Navy (#1A2744):** Does it communicate trust and authority? Yes — it has healthcare and financial services associations that work well for a health product. Kept.
- **Orange (#E85719):** Does it create energy and action? Yes — but orange on white is 3.9:1 contrast ratio, which fails WCAG at small sizes. Fixed: orange restricted to 18px+ bold or inside containers only, white text on orange at 16px minimum.

### The component I'm most proud of

The energy check-in. No other fitness app I found asks how you're feeling *before* the session starts. Every app asks "how did it go?" after. The energy check-in shifts the product's relationship with the user — the plan responds to you, you don't respond to the plan. Designing this component to feel natural (3 options, one pre-selected, 2-second interaction) took longer than any other single element.

### What I'd do differently
Build the dark mode variant earlier. I flagged it as "next steps" but it should have been part of the design system from day one — it affects colour token decisions significantly.

---

## Phase 04 — Wireframes (1.5 weeks)

### What I did
- 12 screens at 360×800 (Android Large)
- Grayscale with DS component references annotated on every screen
- The return-from-lapse edge case — the most important screen in the product

### The screen I almost didn't build

The return-from-lapse screen (07b) wasn't in the original brief. The brief asked for onboarding, dashboard, workout detail, and progress. I added it because without it, the product would have the same fatal flaw as every other fitness app — no path back after a gap.

This screen has no visual complexity. It's a few text blocks and two buttons. Its entire value is in what it doesn't show: no streak counter, no missed day count, no red warnings. The design is the absence of punishment.

### Wireframe annotation approach

I annotated every screen with three things:
1. Which DS component is used (so there's no ambiguity in the UI build)
2. What the interaction does (what changes state, what navigates)
3. What the prototype connection is (which screen it links to and what transition)

This made the wireframe phase double as the prototype specification. No separate prototyping document needed.

### What I'd do differently
Build the wireframes at 375×812 (iPhone) from the start rather than switching between device sizes. I went back and forth between Android and iOS dimensions and it created unnecessary rework.

---

## Phase 05 — Interactive Prototype (1 week)

### What I did
- All 12 screens with full DS colour tokens applied
- 32 prototype connections wired using Figma's reaction system
- Smart Animate Ease-Out 300ms for major transitions, Dissolve 200ms for loading
- 7 distinct flows covering the full user journey

### The technical problem

Figma's MCP integration can write prototype reactions, but they require the `actions` array format (not `action` singular). This took longer than it should have to debug. The lesson: always verify API schema before assuming familiar parameter names work the same way.

### What makes the prototype feel real

The loading screen (S05) auto-advances to the plan reveal after 2 seconds. This small detail changes how the prototype feels — instead of tapping to advance past a loading screen, the user waits, and the reveal feels earned. Smart Animate with 600ms ease-out on that transition creates a sense of weight.

### What I'd do differently
Create a reduced-motion prototype variant from the start. Currently all transitions use Smart Animate — for users with vestibular disorders, this would be a problem in a real implementation.

---

## Phase 06 — Accessibility (1 week)

### What I did
- 42-check WCAG 2.1 AA audit
- Fixed all failures and documented all warnings
- Built a dedicated voice and motor accessibility screen
- Full voice command specification for VoiceOver, TalkBack, Apple Voice Control, Android Voice Access, and Switch Access

### Why I went beyond the brief

The brief didn't ask for accessibility work. Most portfolio fitness projects don't include it. I included it because:

1. It's the right thing to design for
2. It demonstrates senior-level thinking — accessibility is not a bolt-on
3. Persona 05 (Dev) is a real user type that is almost entirely ignored by the fitness app market
4. WCAG compliance is increasingly a legal requirement, especially in the UK under the Equality Act 2010

### The fix that surprised me

Chip heights. Every M3 chip in my design was 30px tall. WCAG 2.5.5 requires 44px minimum touch targets. I had 27 chips across the design that needed resizing. This is the kind of thing that gets missed when accessibility is an afterthought — and it would have affected every single user's experience, not just users with disabilities.

### What I'd do differently
Run the contrast audit before finalising the colour system, not after. I had to go back and adjust several colour pairings that I'd already used across dozens of screens.

---

## What I'd Build Next

If this were a live product moving into development:

1. **Dark mode** — token-level, not a screen-level override
2. **Wearable integration spec** — how Apple Watch and Garmin data feeds into the adaptive engine
3. **Nutrition context layer** — not a food tracker, just contextual nudges ("A protein-rich meal in the next 2 hours supports your recovery")
4. **Dev handoff documentation** — spacing annotations, interaction states, component API spec
5. **User testing** — 5 sessions with real beginners on the onboarding flow specifically

---

## Tools and Process

| Phase | Tool |
|---|---|
| Research and strategy | FigJam |
| Design system | Figma + Material 3 Design Kit |
| Wireframes | Figma |
| Prototype | Figma (prototype panel + MCP automation) |
| Accessibility audit | Manual WCAG checklist + Figma annotations |
| Documentation | Markdown (this repo) |

---

## Honest Reflection

This project took longer than a standard UI exercise because I kept asking "why" before "what". That slowed the early phases down. By the time I got to UI screens, it sped everything up — every decision was already made by the research and the design principles.

The hardest single thing was the lapse return flow. Not technically — it's a simple screen. Hard because it required arguing against the conventional fitness app wisdom that streaks and accountability are retention tools. The research says they're not, for most users. Designing the alternative required confidence in that research position.

If someone looks at this project and thinks "this is a lot of work for a portfolio piece" — yes. It is. That's the point.

---

*Built by a designer who believes the most important screen in a fitness app is the one after you've been gone for a week.*
