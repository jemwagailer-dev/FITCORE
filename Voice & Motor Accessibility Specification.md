# Fitcore — Voice & Motor Accessibility Specification

> Fitcore is designed to be fully usable by people who cannot use their hands or feet. This document covers the complete specification for VoiceOver, TalkBack, Voice Control, Switch Access, and haptic/audio feedback.

---

## Why This Matters

Most fitness apps are built exclusively for users with full motor control and full vision. Fitcore is designed differently — because fitness is for everyone, and the users most underserved by current apps are often the ones who need guidance the most.

> "Most fitness apps assume I have two hands, full mobility, and perfect vision. I have none of those. But I still want to train." — Dev, Persona 05

This specification covers four interaction modalities:
1. Screen readers (VoiceOver / TalkBack)
2. Voice control (Apple Voice Control / Android Voice Access)
3. Switch access (single switch, head tracking, eye gaze)
4. Haptic and audio feedback

---

## 01 — Screen Reader Support

### VoiceOver (iOS) and TalkBack (Android)

All screens must be fully navigable with screen readers enabled. No content should be inaccessible without touch and sight.

### Navigation Gestures

| Gesture | VoiceOver | TalkBack |
|---|---|---|
| Next element | Swipe right | Swipe right |
| Previous element | Swipe left | Swipe left |
| Activate element | Double-tap | Double-tap |
| Scroll | Three-finger swipe | Two-finger swipe |
| Back | Escape gesture | Back button |

### Element Labelling Specification

Every interactive element must have a unique, descriptive accessible name.

**Goal Cards (S02)**
```
Label:   "Lose weight — Burn fat and feel lighter — option 1 of 4"
Label:   "Build muscle — Gain strength and definition — option 2 of 4 — selected"
Label:   "Improve fitness — Boost energy and endurance — option 3 of 4"
Label:   "Stay active — Build a sustainable movement habit — option 4 of 4"
```

**Fitness Level Cards (S03)**
```
Label:   "Just starting out — Little or no regular exercise — option 1 of 4 — selected"
Label:   "Getting back into it — Used to train, took a break — option 2 of 4"
Label:   "Fairly active — Exercise 2 to 3 times per week — option 3 of 4"
Label:   "Very active — Train 4 or more times per week — option 4 of 4"
```

**Filter Chips (S04)**
```
Label:   "Home — location option — selected"
Label:   "Gym — location option"
Label:   "3 days — frequency option — selected"
Label:   "30 minutes — duration option — selected"
```

**Energy Check-in (S07)**
```
Label:   "Full energy — Ready to push it — energy option 1 of 3"
Label:   "Moderate energy — Normal session — energy option 2 of 3 — selected"
Label:   "Low energy — Lighter today — energy option 3 of 3"
Hint:    "Your workout plan will adjust based on your selection"
```

**Navigation Bar**
```
Label:   "Home — tab 1 of 4 — selected"
Label:   "Workouts — tab 2 of 4"
Label:   "Progress — tab 3 of 4"
Label:   "Profile — tab 4 of 4"
```

**Exercise Rows (S08)**
```
Label:   "Push-up — 3 sets of 10 reps — Keep core tight — exercise 1 of 4"
Hint:    "Double-tap to view demonstration video. Swipe up for options including swap exercise."
```

**Video Thumbnails**
```
Label:   "Push-up demonstration video — tap to play"
Label:   "Shoulder Press demonstration video — tap to play"
Label:   "Tricep Dip demonstration video — tap to play"
Label:   "Incline Push-up demonstration video — tap to play"
```

**Active Session Progress Ring (S09)**
```
Label:   "Exercise progress — 3 of 5 complete"
```

**Rest Timer (S09)**
```
Label:   "Rest timer — 14 seconds remaining"
Behaviour: Reads remaining time every 30 seconds automatically via live region
```

**Session Complete Screen (S10)**
```
Label:   "Session complete"
Label:   "Personal insight — You completed 100 percent on your first session. All 4 exercises done."
Label:   "Statistics — Duration 28 minutes, Exercises 4 of 4, Estimated 112 calories"
```

**Achievement Badges (S12)**
```
Label:   "First workout badge — earned"
Label:   "7 days active badge — earned"
Label:   "Comeback badge — earned"
Label:   "Locked badge — not yet earned"
```

### Live Announcements

Dynamic content changes must be announced automatically without user action.

| Trigger | Announcement |
|---|---|
| Plan building step completes | "Step [n] of 4 complete — [step name]" |
| Plan revealed | "Your plan is ready. Beginner Strength Builder. 3 sessions per week, 30 minutes, home." |
| Energy check-in changes plan | "Your plan has been updated for low energy today. Today's session: 20 minutes, 2 exercises." |
| Exercise completed | "Exercise [n] of [total] complete. Next: [exercise name]." |
| Rest timer ends | "Rest complete. Next set: [exercise name], set [n] of [total]." |
| Session complete | "Session complete. 100 percent completion. Duration 28 minutes." |
| Return from lapse | "Welcome back. Your plan has been reset for today. No catching up needed." |

### Reading Order

All screens must be read top-to-bottom, left-to-right, matching the visual layout exactly.

**S07 Dashboard reading order:**
1. Status bar (time, signal)
2. Greeting: "Good morning James"
3. Today card: title, description, tags, Start workout button
4. Energy check-in: question, three options
5. This week: heading, progress, description
6. Quick actions: Log activity, Browse, Progress
7. Navigation bar: Home (selected), Workouts, Progress, Profile

---

## 02 — Voice Control

### Apple Voice Control (iOS) and Android Voice Access

Users can navigate and interact with the app entirely by spoken commands. No touch required.

### Primary Voice Commands

**Navigation**
```
"Go home"           → Navigate to Home Dashboard (S07)
"Go back"           → Navigate to previous screen
"Back"              → Navigate to previous screen
"Progress"          → Navigate to Progress screen (S11)
"Profile"           → Navigate to Profile screen (S12)
"Workouts"          → Navigate to Workout Detail (S08)
"Accessibility"     → Navigate to Voice & Motor screen
```

**Onboarding**
```
"Continue"          → Advance to next onboarding step
"Back"              → Return to previous step
"Select [goal]"     → Select goal card by name
                      e.g. "Select build muscle"
"Choose [level]"    → Select fitness level by name
                      e.g. "Choose just starting out"
"Build my plan"     → Trigger plan building (S04 → S05)
```

**Dashboard & Session**
```
"Start workout"     → Begin today's session from any screen
"Begin session"     → Same as above, from Workout Detail screen
"Skip exercise"     → Skip current exercise during active session
"Skip"              → Same as above
"Done"              → Mark current set as complete
"Complete"          → Same as above
"Finished"          → Same as above
"Next set"          → Move to next set of current exercise
"Pause"             → Pause rest timer
"Resume"            → Resume rest timer
"How much is left?" → Read remaining exercises aloud
"What's next?"      → Read next exercise name and details
```

**Post Workout**
```
"Back to home"      → Navigate to Dashboard after session
"View next session" → Open next planned workout
"Too easy"          → Select difficulty feedback chip
"Just right"        → Select difficulty feedback chip
"Very hard"         → Select difficulty feedback chip
```

**Return from Lapse**
```
"Start fresh"       → Begin shortened return session
"See my plan"       → View full plan from lapse screen
```

### Implementation Notes

Voice Control works by assigning tap targets to spoken labels. Every interactive element in Fitcore must have a visible or accessible label that matches what a user would naturally say.

Where an element's visual label differs from what a user would say, add an alternative label:
- Button label: "Let's go →" → also accepts: "Start", "Continue", "Let's go"
- Energy option: "⚡ Full" → also accepts: "Full energy", "Full", "High energy"

---

## 03 — Switch Access

### Single Switch, Head Tracking, Eye Gaze

Switch access allows users to navigate an interface sequentially — typically cycling through focusable elements and activating the desired one.

### Focus Order Specification

Focus must move through elements in a logical order matching the visual hierarchy.

**S07 Dashboard focus order:**
```
1.  Status bar (skip — not interactive)
2.  Avatar / Profile link (top right)
3.  Today card — full card as one unit
4.  Start workout button (inside today card)
5.  Energy option: Full
6.  Energy option: OK (default)
7.  Energy option: Low
8.  Week progress section (read-only — skip or announce)
9.  Quick action: Log activity
10. Quick action: Browse
11. Quick action: Progress
12. Nav: Home
13. Nav: Workouts
14. Nav: Progress
15. Nav: Profile
```

### Switch Access Requirements

| Requirement | Specification |
|---|---|
| All focusable elements reachable | Via sequential Tab / switch scan without any touch |
| No focus traps | User can always leave any screen, modal, or overlay |
| Auto-scan delay | Minimum 1.5 seconds per element (user-configurable) |
| Skip links | "Skip to main content" and "Skip to navigation" available on each screen |
| No time limits | All interactions are time-unlimited except rest timer (which is pauseable) |
| Minimum target size | 44×44px on all interactive elements |
| Focus indicator | 3px navy `#1A2744` outline, 2px offset, visible on all focused elements |

### Group Navigation

Complex elements should be grouped so users can choose to enter or skip them:

- Today card: Announced as group, user can enter or skip
- Exercise list: Each exercise row announced as group
- Energy check-in: Announced as group with 3 options inside
- Navigation bar: Announced as navigation landmark

### Head Tracking and Eye Gaze

Head tracking (iOS AssistiveTouch) and eye gaze (Tobii, Grid3) work via dwell activation. All interactive elements must:
- Be large enough to dwell on without precision (44×44px minimum)
- Not move or animate while being focused
- Not auto-advance without user confirmation

---

## 04 — Haptic & Audio Feedback

All feedback must have both a haptic and a visual component. Audio is supplementary — never the only channel.

### Haptic Patterns (iOS)

| Event | Haptic type | Pattern |
|---|---|---|
| Button press (standard) | UIImpactFeedbackGenerator | `.light` |
| Chip selection | UIImpactFeedbackGenerator | `.light` |
| Goal / level card selected | UIImpactFeedbackGenerator | `.medium` |
| Onboarding step advance | UINotificationFeedbackGenerator | `.success` |
| Exercise set complete | UIImpactFeedbackGenerator | `.medium` |
| Exercise complete | UINotificationFeedbackGenerator | `.success` |
| Rest timer end | UINotificationFeedbackGenerator | `.warning` (3 pulses) |
| Session complete | Custom sequence: medium + pause + medium + pause + success |
| Error state | UINotificationFeedbackGenerator | `.error` (3 short) |
| Return from lapse — welcome | UIImpactFeedbackGenerator | `.soft` |

### Audio Tones

| Event | Tone description |
|---|---|
| Exercise complete | Short ascending two-tone (C → E) |
| Rest timer end | Gentle bell tone |
| Session complete | Three-tone ascending sequence |
| Error | Low descending tone |
| Navigation | Subtle click (optional, off by default) |

### Silent Mode Behaviour

When the device is on silent:
- All audio tones are suppressed
- Haptic patterns continue unchanged
- Visual feedback is always present regardless of audio/haptic state

### Reduced Motion Behaviour

When `prefers-reduced-motion` is enabled:
- All Smart Animate transitions replaced with Instant
- Progress ring animation removed (static state shown)
- Loading screen animation removed (static checklist shown)
- Rest timer counts down without any animation

---

## 05 — Adaptive Exercise Content

Fitcore's accessibility extends beyond interface — the exercise content itself must be accessible.

### Chair-Based Alternatives

Every standing exercise has a seated / chair-based alternative accessible via "Swap exercise":
- Push-up → Seated chest press (resistance band) or wall push-up
- Shoulder press → Seated dumbbell press
- Tricep dip → Seated tricep kickback (resistance band)
- Squat → Seated leg press (resistance band)

### Low-Mobility Exercise Categories

A dedicated filter category "Low mobility" surfaces exercises appropriate for users with limited range of motion. This is accessible by voice command: "Show low mobility exercises."

### One-Handed Operation

All primary actions are reachable with one hand on a standard phone without repositioning:
- Start workout button: bottom third of screen
- Done / Skip buttons: bottom third of screen, side-by-side
- Navigation bar: bottom of screen

---

## Implementation Checklist for Developers

### iOS
- [ ] Enable VoiceOver support on all `UIView` elements
- [ ] Set `accessibilityLabel` on all interactive elements per this spec
- [ ] Set `accessibilityHint` on complex interactions
- [ ] Implement `UIAccessibilityPostNotification` for live announcements
- [ ] Respect `UIAccessibility.isReduceMotionEnabled`
- [ ] Implement haptic patterns using `UIFeedbackGenerator`
- [ ] Test with VoiceOver and Voice Control on physical device
- [ ] Test with Switch Control using keyboard as switch

### Android
- [ ] Set `contentDescription` on all interactive `View` elements
- [ ] Use `AccessibilityManager.announceForAccessibility()` for live updates
- [ ] Respect `Settings.System.ANIMATOR_DURATION_SCALE`
- [ ] Implement haptic patterns using `HapticFeedbackConstants`
- [ ] Test with TalkBack and Voice Access on physical device
- [ ] Test with Switch Access using switch interface

---

## References

- [Apple Accessibility — VoiceOver](https://developer.apple.com/accessibility/ios/)
- [Apple Voice Control](https://support.apple.com/en-gb/guide/iphone/iph6c494dc6/ios)
- [Android Accessibility — TalkBack](https://support.google.com/accessibility/android/topic/3529932)
- [Android Voice Access](https://support.google.com/accessibility/android/answer/6151848)
- [WCAG 2.1 — Understanding Success Criterion 1.3.1](https://www.w3.org/WAI/WCAG21/Understanding/info-and-relationships)
- [WCAG 2.1 — Understanding Success Criterion 2.5.5](https://www.w3.org/WAI/WCAG21/Understanding/target-size)
