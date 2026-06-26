# Fitcore — Design Principles

> These are not values or aspirations. They are constraints. Each principle eliminates a category of design decision so the team moves faster and the product stays coherent. If a screen violates one of these, it goes back.

---

## 01 — One truth at a time

**Every screen has one primary action. If a user cannot immediately identify what to do, the screen has failed.**

Fitness apps historically show too much. A dashboard with 6 cards, 3 tabs, a notification badge, and a floating button is not helpful — it is decision fatigue. Fitcore reduces every screen to a single clear next step.

**What this means in practice:**
- Every screen has one primary button above the fold
- Secondary actions are visually subordinate — never competing
- Information hierarchy is enforced: most important at the top, supporting detail below
- Stats and data live in the Progress screen, not on every surface

**What this eliminates:**
- Split-attention designs with two equally prominent CTAs
- Dashboard overload — showing everything at once
- Notification dots on every nav item
- Pop-ups that interrupt primary actions

**Test:** Cover the screen with your hand except the top third. If you can't identify what the screen wants you to do from that alone, the hierarchy needs work.

---

## 02 — Forgiveness is a feature

**Every state that typically punishes — a lapse, a missed day, a skipped exercise — must have a no-shame path forward. This is in the product specification, not just the copy.**

Most apps treat failure as a design afterthought. The error state is an afterthought. The post-lapse experience is an afterthought. Fitcore treats these as primary design problems because they are the highest-leverage retention moments in the entire product.

**What this means in practice:**
- No streak counters visible anywhere in the product
- No "You've missed X days" copy anywhere
- Return from lapse: plan auto-shortens, reason shown, warm language
- Skipping an exercise has no negative consequence in the UI
- Post-workout "how did it feel?" feeds forward, not backward

**What this eliminates:**
- Streak break notifications
- Negative counter language ("You're 3 days behind")
- Red progress bars for missed sessions
- Guilt-framing copy ("Don't break the chain")
- Leaderboards that show users where they rank against others

**Test:** Show the lapse return screen to someone who hasn't used the app in two weeks. If they feel bad before they've even tapped anything, the design has failed.

---

## 03 — Show the machine working

**The adaptive engine must be visible. If it adapts silently, users won't trust it. Transparency equals retention.**

Personalisation that is invisible feels like a generic plan. Users who don't understand why a plan was built for them assume it wasn't. Fitcore makes the AI's reasoning visible at every decision point.

**What this means in practice:**
- Plan building screen shows a live checklist of what was heard
- When energy check-in changes the plan, a visible notice confirms it
- Plan reveal card explains its own logic ("Based on your goal, level, and schedule")
- If a session is shortened after a lapse, the reason is stated directly
- Progress insights reference the specific data behind them

**What this eliminates:**
- Silent personalisation that feels accidental
- Plans revealed without explanation
- Notifications that give no reason for the recommendation
- Data collected during onboarding that is never referenced again

**Test:** Show the plan reveal screen to a new user. Ask: "Do you understand why this plan was built for you?" If the answer is no, add more transparency.

---

## 04 — Human language, always

**No metric-speak in the product. Every line of copy must pass the "would a friend say this?" test.**

Fitness apps default to clinical language because it sounds credible. "Volume load", "hypertrophy", "progressive overload", "macros" — these terms exclude beginners and intimidate returners. Fitcore speaks the way a knowledgeable, encouraging friend would.

**What this means in practice:**

| Metric-speak | Fitcore language |
|---|---|
| Volume load | How hard your week was |
| Progressive overload | The plan is getting harder — that's the point |
| Hypertrophy phase | Building muscle phase |
| Rest interval | Rest time |
| Caloric deficit | Eating a little less than you burn |
| Session RPE | How did that feel? |
| Adherence rate | Sessions completed out of planned |

**What this eliminates:**
- Jargon in onboarding that excludes beginners
- Clinical labels on UI elements that don't explain themselves
- Stats presented as raw numbers without context
- Error messages that sound like system logs

**Test:** Read the copy aloud. If it sounds like a fitness textbook, rewrite it. If it sounds like a supportive friend who happens to know a lot about fitness, it passes.

---

## 05 — Earn the next step

**No feature asks for data it hasn't earned trust for yet. No screen asks for more than it needs.**

Onboarding that asks for name, age, weight, height, medical history, and wearable permissions before showing any value is extraction, not experience. Fitcore earns each piece of information by demonstrating value first.

**What this means in practice:**
- Welcome screen shows the product's value proposition before asking anything
- Goal selection is step 1 — the minimum viable question
- Energy check-in only appears after the first session (trust earned)
- Wearable connection is offered after the plan is revealed, not before
- Notification permission is requested after the first completed session
- Injury/limitation field is optional with no friction to skip

**Data collected at each step:**
- Step 1 (Goal): What you want → show partial plan preview immediately
- Step 2 (Level): Starting point → plan updates visibly
- Step 3 (Preferences): Schedule and equipment → plan completes
- Post-session 1: Energy check-in introduced for the first time
- Post-session 3: Wearable connection suggested

**What this eliminates:**
- Long onboarding forms before showing any value
- Permission requests before context is established
- Optional fields that feel mandatory
- Data collection that never visibly improves the experience

**Test:** At each onboarding step, ask: "What value does the user receive in exchange for this information?" If the answer is not immediately visible, move the question later or remove it.

---

## 06 — Celebrate specifically

**"Great job!" is noise. "You held that position 4 seconds longer than last time" is signal. Every reward must be true and personal.**

Generic praise is worse than silence because it trains users to ignore it. After three sessions of "Excellent work!", users stop reading the completion screen. Specific, accurate, personal insights are the only kind that build the feedback loop that keeps people training.

**What this means in practice:**
- Every post-workout screen surfaces one specific, true improvement
- Achievement badges reference real behaviour ("7 days active" not "Committed")
- Plan milestones acknowledge the specific effort ("You trained through a busy week")
- Progress chart highlights the exact session where a personal record was set
- Return from lapse acknowledges the gap without shame: "You're back. That's what counts."

**What this eliminates:**
- Generic "Great workout!" copy as the primary completion message
- Badge systems where every user gets the same badges in the same order
- Progress summaries that repeat what the user already knows
- Motivational copy that isn't grounded in actual user data

**Test:** Could this completion message belong to any user? If yes, it is not specific enough. It must reference something only this user did, in this session, on this day.

---

## Principle Summary

| Principle | What it prevents | What it enables |
|---|---|---|
| One truth at a time | Decision fatigue, cluttered screens | Clear action hierarchy |
| Forgiveness is a feature | Guilt loops, dropout after lapse | Sustainable return behaviour |
| Show the machine working | Invisible personalisation, distrust | Transparent AI, plan trust |
| Human language always | Jargon exclusion, clinical distance | Beginner accessibility, warmth |
| Earn the next step | Extraction onboarding, early dropout | Trust before data collection |
| Celebrate specifically | Generic praise, ignored feedback | Personal insights, meaningful reward |

---

## How to Use These Principles

**In design review:**
Every screen should be evaluated against all six principles. A screen can be visually strong and still fail principle 01 (too many competing actions) or principle 06 (generic completion copy).

**In copy review:**
All copy is checked against principle 04 (human language). Any sentence that could appear in a fitness textbook or system log goes back.

**In feature prioritisation:**
New features are tested against principle 05. If the feature asks for something before demonstrating value, it is deprioritised or restructured.

**In edge case design:**
Every error, lapse, and failure state is checked against principle 02. If it punishes the user or creates shame, it is redesigned.
