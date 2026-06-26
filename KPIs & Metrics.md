# Fitcore — Metrics & KPIs

> Every metric here is tied to a design decision. These are not vanity metrics — they are outcomes that prove the product thesis. If Fitcore is working, these numbers move in the right direction.

---

## North Star Metric

**Weekly Active Training Rate**

The percentage of users who complete 2 or more planned sessions in any given week.

**Target:** >62% of active users in weeks 2–8

**Why this is the North Star:**

1. It measures real behaviour, not app engagement. A user can open the app every day and still not train. This metric only counts when they actually do the work.

2. It is directly tied to health outcomes. Research consistently shows that 2+ training sessions per week produces measurable fitness improvement over 8 weeks.

3. It predicts premium conversion. Users who hit this threshold 3 weeks in a row are 4× more likely to convert to premium than users who don't.

4. It cannot be gamed by the product team. You cannot inflate this metric by sending more notifications, adding more content, or making the app more visually appealing. The only way to move it is to make the training experience genuinely work for users.

---

## Activation Metrics

Activation measures whether users reach the "aha moment" — the point where the product's value becomes real and personal.

For Fitcore, the aha moment is: **completing the first session and seeing a personal insight.**

| Metric | Definition | Target | Red flag |
|---|---|---|---|
| Onboarding completion rate | % of users who reach the Plan Reveal screen | >72% | <65% on any step signals friction |
| First session started (Day 0–1) | % of users who begin session 1 within 24h of onboarding | >58% | <40% means plan reveal failed to convert |
| First session completed | % of users who complete session 1 | >74% | <60% means session was too hard |
| Plan shown as personalised | % of users who see personalised copy on plan reveal | 100% | Any drop below 100% is a system failure |
| Completion screen reached | % of first-session starters who reach the completion screen | >80% | Dropout during session = friction in active session UI |

### Why onboarding completion matters at step level

If 72% overall completion is the target, any individual step below 85% is a problem. Steps should be audited monthly:

| Step | Target completion |
|---|---|
| S01 Welcome → S02 Goal | >92% |
| S02 Goal → S03 Fitness Level | >88% |
| S03 Fitness Level → S04 Preferences | >85% |
| S04 Preferences → S05 Loading | >82% |
| S05 Loading → S06 Plan Reveal | 100% (auto) |
| S06 Plan Reveal → First session | >75% |

---

## Engagement Metrics

Engagement measures how well the product is serving users who have activated.

| Metric | Definition | Target | Why it matters |
|---|---|---|---|
| Weekly workout completion rate | Sessions completed ÷ sessions planned per week | >62% | Core North Star input |
| Energy check-in response rate | % of sessions preceded by energy check-in | >70% | Proxy for plan trust — if users skip it, they don't believe it matters |
| Post-session screen viewed | % of completed sessions where user views completion screen | >80% | Indicates insight relevance — if they skip it, insights aren't landing |
| Session skip rate | % of planned sessions skipped without completing | <25% | Too high = plan is wrong for this user |
| Exercise swap rate | % of exercises swapped per session | <15% | Too high = plan exercise selection is poor |
| Average session duration vs planned | Ratio of actual vs planned session duration | >0.85× | Consistently finishing early = sessions too short or too easy |

### Energy check-in as leading indicator

The energy check-in response rate is an early warning system. If this drops below 60%:

- Users don't believe the plan adapts (transparency problem)
- The check-in UI is creating friction (UX problem)
- Users are opening the app but not intending to train (intent problem)

This metric should be monitored weekly in the first 90 days post-launch.

---

## Retention Metrics

Retention measures whether users come back. This is the hardest problem in fitness apps.

**Industry benchmarks for fitness apps:**
- D1 retention: ~35%
- D7 retention: ~18%
- D30 retention: ~4%

**Fitcore targets:**

| Metric | Definition | Target | vs Industry |
|---|---|---|---|
| D1 retention | % of users who return the day after install | >62% | +77% vs industry |
| D7 retention | % of users who return 7 days after install | >45% | +150% vs industry |
| D14 retention | % of users active in week 2 | >36% | — |
| D30 retention | % of users active 30 days after install | >28% | +600% vs industry |
| D90 retention | % of users active 90 days after install | >18% | — |
| Return after lapse rate | % of users who return after 5+ day gap | >35% | No industry benchmark (no app measures this) |
| Churn recovery rate | % of churned users reactivated within 30 days | >12% | — |

### Why D30 of 28% is achievable

The industry average of 4% is so low partly because of poor lapse recovery design. Most users who "churn" have actually just hit a gap in their routine and never came back because the app made them feel bad.

Fitcore's return from lapse flow is designed to recover these users. If 43% of dropouts cite "no recovery path" as a reason (per research), and Fitcore removes that barrier, recovery of even half of those users moves D30 retention dramatically.

### Lapse return funnel

| Stage | Target |
|---|---|
| Users who lapse (5+ day gap) | 100% (baseline) |
| Users who see lapse return screen | >85% (they must open the app) |
| Users who start fresh session | >60% of those who see screen |
| Users who complete fresh session | >75% of those who start |
| Users still active 7 days later | >50% of those who complete |

If the lapse return flow works as designed, the effective recovery rate from a 5-day lapse is >38%. This is the single highest-leverage retention intervention in the product.

---

## Business Metrics

| Metric | Definition | Target | Notes |
|---|---|---|---|
| Free → Premium conversion rate | % of free users who convert to premium within 30 days | >12% | Among users who complete 2+ sessions/week |
| Premium conversion timing | Median day of premium conversion | Day 18–25 | After habit forms, before plateau hits |
| Premium churn rate | % of premium subscribers who cancel per month | <6% | High premium churn = value not delivered |
| LTV (Lifetime Value) | Average revenue per user over 12 months | >£85 | Based on £7.99/month with 12-month retention |
| CAC (Customer Acquisition Cost) | Average cost to acquire one user | <£8 | Sustainable unit economics |
| LTV:CAC ratio | LTV ÷ CAC | >3.5:1 | Minimum for scalable growth |
| NPS (Net Promoter Score) | Likelihood to recommend (0–10 scale) | >55 | Organic growth predictor |
| Referral rate | % of new users from referral | >22% | High NPS should drive this |

### Premium conversion trigger

The adaptive engine (energy check-in → plan adapts) is the premium hook. Users who experience one manual adaptation (plan changed for low energy) and see the result are significantly more likely to convert.

The optimal paywall placement: after the third session, when energy check-in is introduced. At this moment, the user understands what adaptation means and can see the premium value clearly.

---

## Accessibility Metrics

Fitcore tracks accessibility as a product metric, not a compliance checkbox.

| Metric | Target | Notes |
|---|---|---|
| Voice command success rate | >88% | % of voice commands correctly interpreted and executed |
| Screen reader task completion | >95% | % of primary tasks completable with VoiceOver/TalkBack only |
| Switch access navigation time | Within 2× touch navigation time | Acceptable overhead for switch users |
| Accessibility support requests | <2% of active users per month | High rate = UX problem, not user error |

---

## Dashboard Metrics (Internal)

These are the metrics the product team reviews weekly.

### Week 1 dashboard

```
┌─────────────────────────────────────────────────────────────┐
│  WEEKLY DASHBOARD — W[n]                                    │
├───────────────┬───────────────┬───────────────┬────────────┤
│  New users    │  Onboarding   │  First session │  D7        │
│  [n]          │  completion   │  started       │  retention │
│               │  [n]%         │  [n]%          │  [n]%      │
├───────────────┴───────────────┴───────────────┴────────────┤
│  NORTH STAR: Weekly Active Training Rate                    │
│  [n]% — Target: 62%                                        │
├─────────────────────────────────────────────────────────────┤
│  Energy check-in rate: [n]%   Post-session views: [n]%     │
│  Lapse return rate:    [n]%   Session completion:  [n]%    │
└─────────────────────────────────────────────────────────────┘
```

### Alerts

| Condition | Alert | Action |
|---|---|---|
| Onboarding step drops below 80% | 🔴 Friction alert | Immediate UX investigation |
| First session completion drops below 65% | 🔴 Calibration alert | Session difficulty review |
| Energy check-in rate drops below 60% | 🟡 Trust alert | Copy and UX review |
| D7 retention drops below 38% | 🔴 Retention alert | Full funnel audit |
| NPS drops below 40 | 🟡 Sentiment alert | User interview sprint |

---

## Metric Review Cadence

| Cadence | Metrics reviewed |
|---|---|
| Daily | New users, first sessions started, session completions |
| Weekly | Full activation funnel, North Star metric, lapse return rate |
| Monthly | D30 retention, NPS, premium conversion, LTV:CAC |
| Quarterly | D90 retention, feature adoption, accessibility metrics |

---

## What We Deliberately Do Not Measure

| Not measured | Why |
|---|---|
| Daily active users (DAU) | Users training 3×/week are succeeding — we don't need them opening the app 7×/week |
| Time in app | Long sessions can mean confusion — we want efficient, not extended |
| Sessions per user per day | Multiple daily opens can signal anxiety, not engagement |
| Leaderboard position | We have no leaderboards — no comparison metrics |
| Calories logged | We don't track calories — logging this would contradict the product philosophy |

These omissions are intentional. Measuring them would incentivise design decisions that optimise for the metric at the cost of the user's actual wellbeing.

---

## Success Statement

> Fitcore is working if a user who starts as a complete beginner, lapses twice in their first 60 days, and still considers themselves "someone who trains" by day 90.
>
> Every metric in this document is a proxy for that outcome.
