# 365-Day Time-Based Nurture Framework

> For clients who use a time-based (calendar-driven) nurture, not journey-stage.
> If the client uses journey-stage nurture, generate an Email Library instead (see email-patterns.md).
>
> 52-week email + SMS sequence that loops. Weeks 1-10 fully written. Weeks 11-52 angle + hook + CTA outline.

---

## WHEN TO USE THIS FRAMEWORK

The client explicitly marked **"time-based"** for the Nurture Model (SKILL.md input 6).

Indicators they want time-based:
- They think about nurture as "Day 1, Day 7, Day 30 emails"
- They run the same sequence for every lead regardless of where they are in the journey
- They have a fixed calendar automation already in place (or want one built)

If the client says "my emails run based on where the lead is in their buyer journey" or "different emails fire based on lead stage," that's journey-stage — generate an Email Library instead, NOT this calendar.

---

## THE 5-PHASE STRUCTURE

### Phase 1: Days 0-14 / Weeks 1-2 — Convert Hot Leads
- Frequency: Daily email + daily SMS
- Tone: Urgent but not desperate. They just raised their hand.
- Archetypes to rotate: Story (pain) → Insight (mechanism) → Social proof → Identity shift → Direct ask
- Angles to lead with: Pain + Loss Aversion, Cost of Inaction, Speed

### Phase 2: Weeks 3-6 — Convert Warm Leads
- Frequency: 3 emails per week + 2 SMS per week
- Tone: Story-driven. Build relationship. Show you understand their world.
- Archetypes: Mostly Story and Insight
- Angles: Authority, Social Proof, Identity Shift

### Phase 3: Weeks 7-12 — Revive Dormant
- Frequency: 2 emails per week + 1 SMS per week
- Tone: "Still thinking?" Direct but not pushy.
- Archetypes: Insight + Direct Ask
- Angles: Cost of Inaction, Price Reframe, Direct Ask

### Phase 4: Weeks 13-26 — Belief Building
- Frequency: Weekly email + biweekly SMS
- Tone: Thought leadership. Teach without giving everything away.
- Archetypes: Insight + Story
- Angles: Authority, Identity Shift (rotate)

### Phase 5: Weeks 27-52 — Stay Top of Mind
- Frequency: Weekly email + 2 SMS per month
- Tone: Casual. Mix of proof and seasonal.
- Archetypes: Story + Seasonal
- Angles: Rotate all six

### Loop rule
After week 52, sequence restarts at week 1. Nobody remembers an email from 9 months ago.

---

## THE SIX ANGLES (rotate across the 52 weeks)

Each angle has its own "voice" and purpose. Rotate so no angle repeats more than 8-10 times across the full 52-week cycle.

### 1. Pain + Loss Aversion
Hook pattern: "The [specific dollar] mistake nobody talks about"
What it does: Frames what they lose by not acting. Visceral, specific, numerical.

### 2. Authority
Hook pattern: "Why we [unusual practice]" / "What banks actually look at"
What it does: Positions the expertise behind the service. Earns trust.

### 3. Social Proof
Hook pattern: "[Specific name] got [specific result]. Here's how."
What it does: Specific real people with specific real results. Bypasses skepticism.

### 4. Identity Shift
Hook pattern: "You don't have a [surface problem] problem"
What it does: Reframes the problem. The reader feels seen and re-educated.

### 5. Direct Ask
Hook pattern: "Still thinking about it?" / "{{first_name}}?"
What it does: Clean yes-or-no. Easy exit. Forces decision.

### 6. Seasonal / Cyclical
Hook pattern: "New quarter, new numbers" / "The holiday [opportunity] window"
What it does: Time-based reason to act now. Fresh narrative for long-running nurture.

---

## PHASE CADENCE TABLE

| Phase | Weeks | Email | SMS | Notes |
|-------|-------|-------|-----|-------|
| 1 | 1-2 | Daily | Daily | Hot leads, hit every angle |
| 2 | 3-6 | 3/week | 2/week | Story-heavy |
| 3 | 7-12 | 2/week | 1/week | Direct asks land here |
| 4 | 13-26 | Weekly | Biweekly | Thought leadership |
| 5 | 27-52 | Weekly | 2/month | Casual + seasonal |

---

## PAIRED SMS RULE

SMS in this nurture is paired with email. Structure:

- Email fires Day X
- SMS fires Day X+1, references the email topic but uses a DIFFERENT angle

**Wrong:** Email about $47K mistake → SMS that says "Check out the email about the $47K mistake"
**Right:** Email about $47K mistake → SMS: "Quick math: if you apply wrong, you blow through your best lenders in 3 weeks. Fixable though."

The SMS doesn't recap the email — it drops a different insight that reinforces the same underlying idea. The reader gets TWO touches on the same big idea without repetition.

---

## WEEKLY OUTLINE STRUCTURE (Weeks 11-52)

For each week beyond 10, provide:

```
Week [X] — [Phase Name]
Angle: [one of the 6]
Email Subject: [under 50 chars]
Email Hook: [opening 1-2 sentences]
Story Concept: [what the story/insight is, 1 sentence]
Email CTA: [what action]
SMS Hook: [under 160 chars, different angle than email]
```

---

## GENERATION INSTRUCTIONS

When generating the 52-week nurture for a time-based client:

1. **Mine the offer doc** for the client's exact language, specific results, named clients, real dollar amounts. Every angle you generate must use their specifics, not generic placeholders.
2. **Write weeks 1-10 fully** (subject + body) using the six angles in rotation. Follow the archetypes defined in email-patterns.md.
3. **Outline weeks 11-52** using the structure above. Each outline is enough for the client (or the automation team) to expand into a full email when ready.
4. **Rotate angles strategically** — no angle repeats more than 8-10 times across the 52 weeks. Pain and Social Proof can skew higher in Phases 1-2; Seasonal and Direct Ask skew higher in Phases 4-5.
5. **Pair every email with an SMS** that uses a different angle targeting the same idea.
6. **Every email under 200 words** with one CTA.
7. **Every subject under 50 characters.**
8. **Zero em dashes. Zero voicemails.** Applies throughout.
9. **Loop rule:** Sequence restarts at week 53 → week 1. Automation-only, no manual trigger needed.

---

## AI CALLING DURING LONG-TERM NURTURE (NOT DEFAULT)

Long-tail AI dialing during the 52-week nurture is OPTIONAL and generated only if the client explicitly asks for it.

If the client wants long-tail dialing on top of the nurture emails/SMS:
- Use the same `double_call: true` pattern from Workflow 01 (see snapshot-workflows.md)
- Fire once per week in Phase 2, once biweekly in Phase 3, once per month in Phases 4-5
- Gate every dial on `ai-agent-booked` tag absence (skip anyone who already booked)
- Pre-call SMS 60s before the dial, same rules as Workflow 01
- NO voicemails — RizzDial's `double_call: true` with voicemail detection disabled

**Default:** Long-tail nurture is EMAIL + SMS only. AI dialing handled by Workflow 01 for the first 14 days only.

---

## WHY THIS FRAMEWORK EXISTS

Time-based calendars work when:
- The client doesn't want to think about lead stages
- Their business has a long sales cycle where consistent touch over time matters more than stage-specific messaging
- They want a fire-and-forget system that runs for a year without intervention

Time-based calendars fail when:
- The client's leads convert on different timelines (some in days, some in months)
- The client has distinct buyer stages with different objections
- The client wants to send different emails to different segments

For those cases, use journey-stage (Email Library by angle) instead.
