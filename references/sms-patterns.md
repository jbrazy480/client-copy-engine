# SMS Copy Patterns -- Master Template Library

> Templates for every SMS touchpoint across all GHL workflows.
> Placeholders: [COMPANY], [AGENT], [OFFER], [PAIN], [RESULT], [LINK]
> Rules: No em dashes. Under 160 chars ideal, 320 max. One CTA. Human tone.

---

## 1. SPEED-TO-LEAD 3-TEXT PATTERN (Workflow 01)

The highest-converting inbound SMS sequence. Use for every new lead.

**Text 1** (Immediate, within 30s of opt-in):
```
Hey {{first_name}}
```
~16 chars | Psychology: Pattern interrupt. Feels like a real person, not a bot.

**Text 2** (30 seconds after Text 1):
```
This is [AGENT] from [COMPANY]
```
~35 chars | Psychology: Identity. Now they know who's texting.

**Text 3** (30 seconds after Text 2):
```
Book a time with us here: {{booking_link}}
```
~45 chars + link | Psychology: Clear CTA. No fluff. Action step.

**Text 4** (24 hours later):
```
{{first_name}}?
```
~8 chars | Psychology: Curiosity bomb. Impossible to ignore. Highest reply rate of any message.

### Why This Works:
- Staggered timing feels like someone actually typing
- Short messages feel personal, not automated
- The 24hr first-name-only text forces a response (they HAVE to reply or it nags them)

---

## 2. OPT-IN RETRY PATTERNS (Workflow 01, after no response)

**Retry 1** (30 min after initial sequence, no response):
```
Hey {{first_name}}, just wanted to make sure you saw this. We help [RESULT]. Got a sec?
```
~90 chars | Angle: Casual nudge + value restatement

**Retry 2** (2 hours after, no response):
```
Quick heads up, we only take on a few new [clients/businesses] each month. Didn't want you to miss the window.
```
~115 chars | Angle: Scarcity (real, not fake)

**Retry 3** (Next morning, 9am):
```
Morning {{first_name}}. Still interested in [RESULT]? Happy to jump on a quick call today if the timing works better.
```
~120 chars | Angle: Fresh day, new energy, offer flexibility

**Retry 4** (Next afternoon, 2pm):
```
Most [industry] owners we talk to are losing [PAIN]. Just takes 15 min to see if we can fix that for you.
```
~108 chars | Angle: Loss aversion + low time commitment

**Retry 5** (48 hours, final):
```
{{first_name}}?
```
~8 chars | Angle: First-name-only repeat. Works every time.

---

## 3. APPOINTMENT CONFIRMATION/REMINDER PATTERNS

**Confirmation SMS** (Immediately after booking):
```
You're all set for {{appointment_date_and_time}}! Looking forward to showing you how we [RESULT]. Talk soon.
```
~110 chars | Tone: Celebratory, warm

**24hr Reminder SMS**:
```
Hey {{first_name}}, just a reminder about tomorrow at {{appointment_time}}. Come with any questions, we'll make it worth your time.
```
~130 chars | Tone: Casual, value-forward

**2hr Reminder SMS + Testimonial**:
```
See you in 2 hours! Quick stat: our last client in [industry] saw [specific result] in the first 30 days. Can't wait to show you.
```
~130 chars | Angle: Social proof injection

**1hr Reminder SMS**:
```
One hour out! See you soon {{first_name}}.
```
~42 chars | Tone: Simple, personal

**5min Final Reminder SMS**:
```
Jumping on in 5. See you there!
```
~31 chars | Tone: Casual, like a friend texting

---

## 4. NO-SHOW RECOVERY PATTERNS (No-Show Workflow)

**3hr Post-No-Show SMS**:
```
Hey {{first_name}}, we missed you today. No worries at all, life happens. Want to grab another time? {{booking_link}}
```
~115 chars | Angle: No blame. Easy reschedule. Door open.

**2-Day Follow-Up SMS**:
```
{{first_name}}, did you give up on [RESULT]? If not, I saved your spot. Just pick a new time here: {{booking_link}}
```
~115 chars | Angle: Identity challenge. "Did you give up?" triggers pride.

**Re-engagement SMS** (different angle):
```
Saw something that reminded me of our convo. [One-line insight about their industry]. Worth 15 min to chat?
```
~108 chars | Angle: Personal, value-based, not a reschedule nag

---

## 5. POST-SALE / CLOSED WON PATTERNS

**Welcome SMS** (Day 0):
```
Welcome to [COMPANY] {{first_name}}! Excited to get this rolling for you. You're gonna love what we build. Check your email for next steps.
```
~140 chars | Tone: Celebratory, personal

**Day 7 Check-In SMS**:
```
Hey {{first_name}}, how's everything looking so far? Any questions I can help with? Just text me back.
```
~100 chars | Tone: Helpful, casual

**Day 30 Review Ask SMS**:
```
{{first_name}}, quick favor. If you're happy with the results so far, would you mind leaving us a quick review? Means a lot. [REVIEW_LINK]
```
~140 chars | Angle: Personal ask, not corporate

---

## 6. DATABASE REACTIVATION PATTERNS (Reactivation 01-03)

**Workflow 01 Hook SMS** (Initial reactivation):
```
Hey {{first_name}}, it's been a minute. We just launched something new for [industry] and honestly I thought of you. Got 2 min?
```
~128 chars | Angle: Personal, curiosity, "thought of you"

**Positive Sentiment Response** (They replied positively):
```
Awesome! Let's get you on the calendar so I can walk you through it. What day works best this week? {{booking_link}}
```
~115 chars | Angle: Assumptive bridge, move fast

**Negative Sentiment Response** (They're not interested):
```
Totally get it. If anything changes down the road, you know where to find us. Have a great day {{first_name}}.
```
~110 chars | Angle: Graceful exit, leave door open, no pressure

**Workflow 02 Alternative Angle SMS**:
```
{{first_name}}, quick question. Are you still dealing with [PAIN]? Because we just helped a [industry] owner fix that in [timeframe].
```
~130 chars | Angle: Different pain point, social proof

**Workflow 03 Final Push SMS**:
```
Last one from me {{first_name}}. We have [X] spots left this month for [OFFER]. After that we're full until next quarter. Worth a look?
```
~135 chars | Angle: Scarcity + finality (last message = higher urgency)

---

## 7. NURTURE SMS PATTERNS (Workflow 05, paired with emails)

**Nurture SMS 1** (Identity angle):
```
{{first_name}}, most [industry] owners settle for [mediocre result]. You don't seem like the settling type. Am I wrong?
```
~118 chars | Angle: Identity challenge

**Nurture SMS 2** (Cost of inaction):
```
Quick math: if your [metric] stays the same for another 6 months, that's roughly $[X] you're leaving on the table. Fixable though.
```
~130 chars | Angle: Loss aversion with specific number

**Nurture SMS 3** (Social proof):
```
Just got off a call with a [industry] owner who went from [before] to [after] in [timeframe]. Reminded me of your situation.
```
~125 chars | Angle: Story-based proof

**Nurture SMS 4** (Speed):
```
You don't need another year to figure this out. Most of our clients are up and running in [timeframe]. What's holding you back?
```
~128 chars | Angle: Speed + direct question

**Nurture SMS 5** (Call-out):
```
{{first_name}}, real talk. Are you still serious about [RESULT], or should I stop reaching out? Either way is cool with me.
```
~122 chars | Angle: Takeaway. Forces a decision.

---

## 8. AI CALL REPLY PATTERN (AI Call On Reply P1/P2)

**Pre-Call SMS** (Sent 1 min before AI callback):
```
Hey {{first_name}}, saw your message. Giving you a quick call right now.
```
~72 chars | Purpose: Set expectation so they answer. Feels human.

---

## UNIVERSAL SMS RULES

1. First text is ALWAYS short (under 30 chars). Build intrigue, not information.
2. Never put a link in the first text. Earn the click first.
3. The 24hr "{{first_name}}?" follow-up works everywhere. Use it.
4. Stagger multi-text sequences by 30 seconds (simulates typing).
5. Business hours only (9am-5pm client timezone). No midnight texts.
6. If {{first_name}} is empty, use "Hey there" or skip the name entirely.
7. One CTA per text. Never "book a call AND check out our website AND follow us."
8. Emojis: one max per text, only if brand voice supports it. Default to zero.
9. No hashtags. Ever.
10. No em dashes. Ever.
