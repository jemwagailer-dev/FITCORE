# FITCORE   [FITCORE_README (1).md](https://github.com/user-attachments/files/29372247/FITCORE_README.1.md)
<div align="center">

# Fitcore
### AI-Powered Fitness App — UX/Product Design Case Study

*A senior-level product design portfolio project covering research, strategy, design system, wireframes, interactive prototype, and accessibility — designed for a potential 2027/2028 launch.*

[![Figma](https://img.shields.io/badge/Figma-Design%20File-F24E1E?style=flat&logo=figma&logoColor=white)](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui)
[![Research](https://img.shields.io/badge/FigJam-Research%20Board-8B5CF6?style=flat&logo=figma&logoColor=white)](https://www.figma.com/board/oes8nIbmyMWwU0ZB4hLh4K/fitcore-research)
[![Prototype](https://img.shields.io/badge/Figma-Interactive%20Prototype-0ACF83?style=flat&logo=figma&logoColor=white)](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=105-2)
[![WCAG](https://img.shields.io/badge/WCAG-2.1%20AA%20Compliant-1A2744?style=flat)](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=0-1)

</div>

---

## The Problem

The fitness app market is saturated — yet user retention remains catastrophically low.

> **Most users don't fail because they lack information. They fail because fitness apps fail them.**

- 68% of users quit because the plan felt unrealistic for their real life
- 54% abandoned after a missed day triggered streak guilt
- 49% felt the personalisation was fake within 2 weeks
- 43% found no recovery path after a gap in training

**Current apps are designed for the ideal user. Fitcore is designed for the real one.**

---

## The Solution

An adaptive fitness platform that gets smarter when life gets harder — adjusting plans, rebuilding confidence after lapses, and never punishing consistency gaps.

| | Fitcore | Typical Fitness App |
|---|---|---|
| Missed a week? | Auto-shortens your return session, no guilt | Streak broken, counter resets |
| Low energy today? | Plan adapts before the session starts | Same plan regardless |
| Feel like quitting? | Specific personal insight ("You held that 4s longer") | Generic "Great job!" |
| Plan feels wrong? | Rebuilds around your real schedule | Fixed plan, you adapt |
| No hands or feet? | Full voice and switch access support | Touch-only |

---

## User Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  ONBOARDING                                                                  │
│  Welcome → Goal Selection → Fitness Level → Preferences → Plan Building     │
│                                              ↓                               │
│  PLAN REVEAL                                                                 │
│  Your plan is ready → Explore full plan ──→ Dashboard                       │
│                     → Start first workout ─────────────────────┐            │
│                                                                 ↓            │
│  CORE WORKOUT FLOW                                                           │
│  Dashboard → Workout Detail → Active Session → Workout Complete              │
│      ↑                              ↓ Skip (loops)       ↓                  │
│      └──────────────── Back to home ←─────────────────────┘                │
│                                                                              │
│  TRACKING & PROFILE                                                          │
│  Dashboard ──→ Progress (nav)                                                │
│            ──→ Profile  (nav) ──→ Accessibility Settings                    │
│                                                                              │
│  EDGE CASE: RETURN FROM LAPSE (the hero flow)                               │
│  5+ day gap detected → Fresh start screen → Shortened session → Complete    │
└─────────────────────────────────────────────────────────────────────────────┘
```

**[→ View full interactive prototype](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=105-2)**

---

## Research & Strategy

**[→ View full research board on FigJam](https://www.figma.com/board/oes8nIbmyMWwU0ZB4hLh4K/fitcore-research)**

### Competitive Analysis

8 competitors analysed across core problem, target users, strengths, weaknesses, UX patterns, retention strategies, and monetisation.

| App | Core Problem Solved | Key Weakness | Our Opportunity |
|---|---|---|---|
| Strava | Social fitness tracking | Social comparison hurts beginners | Remove comparison, keep motivation |
| Nike Training Club | Guided workouts | Fixed plans, no adaptation | Adaptive planning |
| MyFitnessPal | Nutrition tracking | Overwhelming data, guilt-driven | Simplify, context-only nutrition |
| Fitbod | Smart strength programming | Gym-focused, intimidating | Home-first, beginner-safe |
| Apple Fitness+ | Video-led workouts | No real personalisation | True adaptive personalisation |
| Freeletics | HIIT community | Punishing, high dropout | Forgiving, sustainable |
| Future | Human coaching | Expensive ($150/month) | AI coaching at scale |

**Market gap identified:** No app is designed around the moment users almost quit — and then comes back. That gap is Fitcore's positioning.

### User Personas

Five psychologically realistic personas — not demographic boxes.

| Persona | Age | Core frustration | What keeps them |
|---|---|---|---|
| Leila — The Returner | 29 | "I keep starting over and feeling like I've lost everything" | Seeing progress preserved, not reset |
| Marcus — The Busy Professional | 34 | "I have 20 minutes but the app wants 45" | Sessions that fit the actual day |
| Jamie — The Complete Beginner | 22 | "Everyone at the gym looks like they know something I don't" | Guidance without judgement |
| Rosa — The Plateau Hitter | 38 | "I've been doing this for months and nothing is changing" | Specific, data-backed insight |
| Dev — The Low Mobility User | 31 | "Most apps assume I can touch a screen with both hands" | Full voice and switch access |

### Jobs To Be Done

```
When I miss a week of training,
I want to come back without feeling punished,
So I can build a habit that actually lasts.

When I open the app feeling exhausted,
I want the plan to already know that,
So I don't have to choose between pushing through or giving up.

When I complete a session,
I want to know something specific I improved,
So I feel the work was worth it.
```

---

## Design Decisions

### The Return from Lapse Flow
The single most important screen in the app. After 5+ days without a session:

- No streak counter visible
- No "You've missed X days" copy
- Plan auto-shortened (20 min, 2 exercises, low intensity)
- Reason shown: *"Starting easier builds lasting consistency"*
- Message at bottom: *"Gaps are part of the journey. You're back — that's what counts."*

This is the flow no other fitness app has designed. It's also the highest-leverage retention moment.

### Energy Check-in Before Every Session
Before any session starts, users select their energy level (Full / OK / Low). The plan adjusts *before* they begin — not after they fail. This shifts the psychological contract from "can you do the plan?" to "the plan fits you today."

### Specific Insight on Completion
"Great job!" is noise. "You held that plank 4 seconds longer than last time" is signal. Every post-workout screen surfaces one specific, true, personal improvement. Nothing generic.

### Adaptive Plan Reveal
The onboarding loading screen shows a live checklist of what the AI heard:
- Goal: Build muscle ✓
- Level: Just starting out ✓
- Schedule: 3 × 30 min ✓
- Equipment: Home ✓

Transparency about how the plan was built increases trust and reduces "this feels generic" perception by showing the machine understood you.

---

## Retention Strategy

### Why Users Quit (root cause analysis)

| Cause | Frequency | Fitcore response |
|---|---|---|
| Plan felt unrealistic | 68% | Adaptive planning + energy check-in |
| Streak guilt after a miss | 54% | Zero streak UI in the entire product |
| Felt generic within 2 weeks | 49% | Transparent AI + specific insights |
| No recovery path after lapse | 43% | Return from lapse hero flow |

### The Fitcore Habit Loop

```
CUE      → Smart notification based on your actual routine pattern, not a fixed time
ROUTINE  → Energy check → plan adapts → session starts in under 3 taps
REWARD   → Specific personal insight: "You beat last week's plank by 8 seconds"
IDENTITY → "You're someone who trains through busy weeks" — identity reinforcement
```

### Notification Rules
- ✅ Timing based on user's detected routine pattern
- ✅ After 3 missed days: one gentle message, never a guilt counter
- ✅ Return message: *"We updated your plan for today — no catching up needed"*
- ❌ No streak break notifications
- ❌ No "You're falling behind" messaging
- ❌ No leaderboard comparisons

---

## Metrics & KPIs

### North Star Metric
**Weekly Active Training Rate** — % of users who complete ≥2 planned sessions in any given week.

*Why:* Measures real behaviour, not app opens. Tied directly to health outcomes and premium conversion likelihood.

### Full KPI Framework

| Category | Metric | Target | Rationale |
|---|---|---|---|
| **Activation** | Onboarding completion rate | >72% | Under 65% signals a friction point |
| **Activation** | First session started (Day 0–1) | >58% | Intent converted to action |
| **Engagement** | Weekly workout completion rate | >62% | Sessions started vs planned |
| **Engagement** | Energy check-in response rate | >70% | Proxy for plan trust |
| **Retention** | D7 retention | >45% | Industry average is ~25% |
| **Retention** | D30 retention | >28% | 7× above industry average |
| **Retention** | Return after lapse rate | >35% | Fitcore's strongest differentiator |
| **Business** | Free → Premium conversion | >12% | Adaptive engine is the premium hook |
| **Business** | NPS | >55 | Organic growth predictor |

---

## Design System

**[→ View Design System in Figma](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=0-1)**

Built on Material 3 with Fitcore brand adaptations. 18 documented sections.

### Colour Roles (M3 adapted)

| Token | Value | Usage |
|---|---|---|
| Primary | `#1A2744` Navy | Headlines, buttons, nav active |
| Tertiary (Accent) | `#E85719` Orange | CTAs, progress, energy indicators |
| Secondary | `#4A5978` Slate | Secondary actions, supporting UI |
| Success | `#228957` | Completion states, positive feedback |
| Surface | `#FCFCFD` | Card backgrounds, screen backgrounds |

### Typography
Inter — chosen for legibility at fitness-metric data sizes and authority at display weights. 15-stop type scale from Display Large (57px) to Label Small (11px).

### Components Built
Buttons (5 variants) · FAB (4 variants) · Chips (Filter, Assist, Input) · Cards (Elevated, Filled, Outlined, Skeleton) · Navigation Bar · Text Fields (Filled, Outlined, Error) · Progress Indicators (Linear, Circular) · Bottom Sheet · Snackbar · Energy Check-in (Fitcore custom) · Achievement Badges (Fitcore custom)

### Design Principles
1. **One truth at a time** — every screen has one primary action
2. **Forgiveness is a feature** — every failure state has a no-shame path forward
3. **Show the machine working** — if the AI adapts silently, users won't trust it
4. **Human language, always** — "how hard your week was", not "volume load"
5. **Earn the next step** — no feature asks for data it hasn't earned trust for
6. **Celebrate specifically** — "You held that 4s longer", not "Great job!"

---

## Wireframes

**[→ View Wireframes in Figma](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=23-2)**

12 screens at 360×800 Android Large. Grayscale with DS component references annotated on every screen.

| Screen | Purpose | Key UX decision |
|---|---|---|
| 01 Welcome | Value proposition before data ask | Show the "why" before asking anything |
| 02 Goal Selection | 4 goal cards with selected state | Max 4 options — reduces decision fatigue |
| 03 Fitness Level | Cards with embedded progress bars | Visual metaphor for current activity level |
| 04 Preferences | Chip rows — location, days, duration, equipment | Progressive disclosure — most important first |
| 05 Plan Building | Transparent AI loading checklist | Shows what was heard — builds trust |
| 06 Plan Reveal | Summary card + 3-day week preview | Plan shown before CTA — earn the click |
| 07 Dashboard | Today card, energy check-in, week progress | Energy first — plan second |
| 08 Workout Detail | Exercise list, video thumbnails, swap links | Every exercise is replaceable |
| 09 Active Session | Full-screen, progress ring, rest timer | Remove all distractions during exercise |
| 10 Complete | Personal insight, stats, feeling feedback | Specific reward — not generic praise |
| 11 Progress | Bar chart, stat cards, session history | Progress is personal, not competitive |
| 12 Profile | Stats, badges, settings | Achievement-based, not streak-based |

---

## Accessibility — WCAG 2.1 AA

**[→ View Accessibility Audit in Figma](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=105-2)**

### Audit Results

| Criterion | Checks | Pass | Warn | Fail |
|---|---|---|---|---|
| Colour Contrast 1.4.3 | 9 | 8 | 1 | 0 |
| Touch Targets 2.5.5 | 8 | 7 | 1 | 0 |
| Text Size 1.4.4 | 6 | 4 | 2 | 0 |
| Focus Visible 2.4.7 | 4 | 4 | 0 | 0 |
| Motion 2.3.3 | 4 | 2 | 2 | 0 |
| Labels & Structure 1.3.1 | 6 | 6 | 0 | 0 |
| Voice / Screen Reader | 5 | 5 | 0 | 0 |
| **Total** | **42** | **36** | **6** | **0** |

### Fixes Applied in This Project
- Chip touch targets increased from 30px → 44px (27 components)
- Focus rings added to all 11 primary interactive elements (3px navy, 2px offset)
- Video thumbnails given accessible labels and visible alt text
- Swap exercise links enlarged to 44px tap zone
- Orange `#E85719` restricted to 18px+ bold or inside containers only

### Voice & Motor Accessibility

Fitcore is designed for users who cannot use their hands or feet.

**Voice commands supported:**
- `"Start workout"` → begins today's session from any screen
- `"Skip exercise"` → advances to next without touch
- `"Done"` / `"Complete"` → marks current set complete
- `"Go home"` → navigates to dashboard
- `"How much is left?"` → announces remaining exercises aloud

**Screen reader support:**
- All elements have unique accessible names
- Goal cards: *"Build muscle — Gain strength and definition — option 2 of 4 — selected"*
- Progress ring: *"Exercise 3 of 5 complete"*
- Timer reads remaining time every 30 seconds during rest

**Switch access:** Sequential tab order, no focus traps, all targets 44×44px minimum, auto-scan delay 1.5s configurable.

---

## What's Next

- [ ] High-fidelity UI build in Figma (all 12 screens)
- [ ] Dark mode variant
- [ ] Nutrition context layer (nudges only — not a food tracker)
- [ ] Wearable integration spec (Apple Watch, Garmin)
- [ ] Handoff documentation for development

---

## Process

```
Market Research → Competitive Analysis → Personas → Journey Mapping
      ↓
Product Strategy → Vision → KPIs → Retention Strategy → Design Principles
      ↓
Design System → Colour tokens → Typography → Components → States
      ↓
Wireframes → 12 screens → Edge cases → Prototype connections
      ↓
Accessibility → WCAG audit → Voice spec → Fixes applied
```

Total: 9 phases · 18 design system sections · 12 screens · 42 accessibility checks · 32 prototype connections

---

## Links

| | |
|---|---|
| 🔬 Research Board | [FigJam — Strategy, Personas, Journey Maps, Retention](https://www.figma.com/board/oes8nIbmyMWwU0ZB4hLh4K/fitcore-research) |
| 🎨 Design System | [Figma — M3 Tokens, Components, UI States](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=0-1) |
| 📐 Wireframes | [Figma — 12 screens, 360×800 Android](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=23-2) |
| 📱 UI Screens | [Figma — Hi-fidelity screens](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=23-3) |
| ▶ Prototype | [Figma — Interactive prototype, all flows wired](https://www.figma.com/design/QKysZYSjZ6cKrTxGf10Zwc/fitcore-ui?node-id=105-2) |

---

<div align="center">

*Built by a designer who believes the hardest UX problem in fitness isn't the first session — it's the one after you've missed a week.*

</div>
