# GHL Snapshot Workflows -- Copy Map

> Every client gets these workflows imported via the MetaTech/RizzDial snapshot.
> This document defines exactly what copy each workflow needs.
> Generate copy for EVERY slot listed below.

---

## WORKFLOW 01: OPT-IN SEQUENCE
**GHL Name:** 01 -- Opt-In Workflow (AI Calls, SMS & Emails)
**Trigger:** Tag `new lead`
**Purpose:** Immediately contact new leads across SMS, email, and AI voice. 6 call attempts over 2 days.

### Copy Slots:
1. **SMS 1** (Immediate, within 30 sec) -- Pattern interrupt, name only. "Hey {{first_name}}"
2. **SMS 2** (30 sec after SMS 1) -- Company intro + who you are. "This is [agent] from [company]"
3. **SMS 3** (30 sec after SMS 2) -- Booking link + soft CTA. "Book a time with us here: {{booking_link}}"
4. **Email 1** (Simultaneous with SMS 1) -- Welcome + value prop + booking link. Subject line required.
5. **Retry SMS 1** (30 min after no response) -- Different angle, not a repeat
6. **Retry SMS 2** (2 hours after no response) -- Urgency or social proof angle
7. **Retry SMS 3** (Next morning 9am) -- Fresh day, new hook
8. **Retry SMS 4** (Next afternoon 2pm) -- Loss aversion angle
9. **Retry SMS 5** (48 hours) -- First name only with question mark: "{{first_name}}?"

### Rules:
- Business hours only (9am-5pm client timezone)
- Stop if appointment is set (tag: `ai appt set`)
- After all attempts with no booking, move to nurture (tag: `nurture-active`)

---

## WORKFLOW 05: NURTURE SEQUENCE
**GHL Name:** 05 -- Nurture Sequence (SMS & Email)
**Trigger:** Tag `nurture-active`
**Purpose:** Long-term drip. Seinfeld-style emails + conversational SMS. Loops when complete.

### Copy Slots:
1. **Email 1** -- Story-driven, educational, soft CTA. Subject + body.
2. **SMS 1** (1 day after Email 1, 5 min offset) -- Conversational, references the email topic
3. **Email 2** -- Different angle, new story. Subject + body.
4. **SMS 2** (1 day after Email 2, 5 min offset)
5. **Email 3** -- Social proof or case study angle. Subject + body.
6. **SMS 3** (1 day after Email 3, 5 min offset)
7. **Email 4** -- Identity/cost of inaction angle. Subject + body.
8. **SMS 4** (1 day after Email 4, 5 min offset)
9. **Email 5** -- Authority/proof angle. Subject + body.
10. **SMS 5** (1 day after Email 5, 5 min offset)

### Rules:
- Later waits increase to 30 days between touches
- Sequence restarts when complete (nobody remembers an email from 9 months ago)
- Pattern: Email > Wait 1 day (M-F 9-5) > SMS 5 min later > Email > repeat

---

## NURTURE SEQUENCE CALLS
**GHL Name:** Nurture Sequence Calls
**Trigger:** Tag `new lead` (separate from workflow 01)
**Purpose:** AI calls on Day 3, 7, 14. Gated by `ai appt set` tag.

### Copy Slots:
1. **Day 3 Voicemail Script** -- Warm check-in, reference their initial interest
2. **Day 7 Voicemail Script** -- Value-based, share a quick insight or stat
3. **Day 14 Voicemail Script** -- Last attempt angle, soft urgency

### Rules:
- Check for `ai appt set` tag before each call. If present, stop.
- Voice scripts should reference the offer and sound human.

---

## WORKFLOW 02: INBOUND CALL HANDLER
**GHL Name:** 02 -- Inbound Call
**Trigger:** Tag `inbound`
**Purpose:** Route inbound calls, create opportunity in pipeline.

### Copy Slots:
1. **Internal notification email** -- Alert the team. Include contact name, phone, source.

### Rules:
- This is internal only. No client-facing copy needed.

---

## AI CALL ON REPLY (P1 + P2)
**GHL Name:** AI Call On Reply -- P1 & P2
**Trigger:** Customer replies (SMS/email)
**Purpose:** When a lead replies, send friendly SMS then trigger AI call.

### Copy Slots:
1. **Friendly response SMS** -- Acknowledge their reply, tell them you're calling. Under 160 chars.

### Rules:
- Check tags (`text`, `ai appt set`, `no show`) before triggering
- Wait 1 min after SMS, then AI call via webhook

---

## APPOINTMENT CONFIRMATION + REMINDERS
**GHL Name:** Appointment Confirmation + Reminder
**Trigger:** Appointment confirmed (Normal type)
**Purpose:** Multi-touch sequence to maximize show rate.

### Copy Slots:
1. **Confirmation Email** -- Celebratory tone. Date/time, what to expect, prep instructions.
2. **Confirmation SMS** -- Short, confirm date/time, excitement.
3. **24hr Reminder Email** -- Value injection. Why this call matters. What they'll learn.
4. **24hr Reminder SMS** -- Quick reminder + "looking forward to it"
5. **24hr "What to Expect" Content** -- Brief overview of what happens on the call
6. **2hr Reminder SMS + Testimonial** -- Social proof. Quick client win or stat.
7. **1hr Reminder SMS** -- Simple "See you in an hour!"
8. **5min Final Reminder SMS** -- "Jumping on in 5, see you there!"

### Rules:
- Add tag `ai appt set`, remove `no show`, remove from other workflows
- 2hr post-appointment: internal notification to team

---

## APPOINTMENT REMINDER CALL
**GHL Name:** Appointment Reminder Call -- 24 Hours Before
**Trigger:** Appointment confirmed (Normal type)
**Purpose:** AI voice call 24hr before appointment.

### Copy Slots:
1. **24hr Reminder Call Script** -- Casual, warm. Confirm they're still good. Build excitement.

### Rules:
- Business hours check before calling
- Webhook to AI calling system

---

## APPOINTMENT NO-SHOW
**GHL Name:** Appointment No Show
**Trigger:** No show / canceled pipeline stage
**Purpose:** Recover no-shows with empathy-first follow-up.

### Copy Slots:
1. **3hr Post-No-Show SMS** -- No guilt. "We missed you" + easy reschedule link
2. **2-Day Follow-Up SMS** -- "Did you give up on [goal]?" Emotional hook + reschedule
3. **Re-engagement SMS** -- Different angle. What they're missing.
4. **No-Show Voicemail Script** -- Empathetic, casual, "life happens" tone

### Rules:
- Tag `no show`, remove `ai appt set`
- Remove from all other workflows first
- After follow-up attempts, add to additional recovery workflow

---

## APPOINTMENT DISPOSITION FORM
**GHL Name:** Appointment Disposition Form Submitted
**Trigger:** Form submission
**Purpose:** Route based on call outcome.

### Copy Slots:
None required (internal routing only). But document the 5 branches:
- Showed/Sold
- Showed/Didn't Close
- No Show
- Canceled
- Rescheduled

---

## POST CALL TRANSCRIPT ANALYSIS
**GHL Name:** Post Call Transcript Analysis
**Trigger:** AI Transcript field changes
**Purpose:** AI categorizes call outcome and updates pipeline.

### Copy Slots:
None required (AI categorization logic only).

---

## POST-SALE / CLOSED WON SEQUENCE
**GHL Name:** Post-Sale / Closed Won Sequence
**Trigger:** Closed Won stage or `client` tag
**Purpose:** Onboard, delight, get reviews and referrals.

### Copy Slots:
1. **Day 0 Welcome Email** -- Congratulations, what happens next, login details
2. **Day 0 Welcome SMS** -- Short, celebratory, personal
3. **Day 3 Check-In Voicemail** -- AI call. "How's everything going? Any questions?"
4. **Day 7 Check-In Email** -- Early value. Quick tip or resource.
5. **Day 7 Check-In SMS** -- "How are things looking so far?"
6. **Day 30 Review Request Email** -- Ask for Google/social review. Make it easy.
7. **Day 60 Referral Request Email** -- "Know anyone else who could use this?"
8. **Day 60 Referral Voicemail** -- AI call. Warm, not salesy. Plant the seed.

---

## POWER DIALER WORKFLOWS
**GHL Name:** 01 -- Send Leads to Power Dialer
**Trigger:** Tag `dialer-active`

### Copy Slots:
None (webhook data pass-through only).

---

## DISPOSITIONS FROM RIZ TO GHL
**GHL Name:** 02 -- Dispositions From Rizzler to GHL
**Trigger:** Tags: `ai appt set`, `bad number`, `follow up`, `not interested`, `renter`, `spanish`

### Copy Slots:
None (tag-to-pipeline mapping only).

---

## DATABASE REACTIVATION (01, 02, 03)
**GHL Name:** Database Reactivation (01, 02, 03)
**Trigger:** Tag `Reactivation`
**Purpose:** 30-week, 3-workflow chain. Re-engage cold leads with varied angles.

### Copy Slots:
1. **Workflow 01 Hook SMS** -- Initial reactivation. Offer/voucher angle. Create curiosity.
2. **Workflow 01 Positive Sentiment Response** -- They replied positively. Push to booking.
3. **Workflow 01 Negative Sentiment Response** -- They're not interested. Graceful, leave door open.
4. **Workflow 02 Alternative Angle SMS** -- Different pain point, same offer. Fresh hook.
5. **Workflow 03 Final Push SMS** -- Scarcity/urgency. Last chance framing.

### Rules:
- Each workflow has up to 10 attempts
- Chains through 3 workflows (30-week total period)
- Sentiment check after each reply (positive = booking, negative = "no worries")

---

## REACTIVATION REPLY HANDLER
**GHL Name:** 04 -- Call on Database Reactivation Reply
**Trigger:** Customer reply from reactivation workflows
**Purpose:** 3 AI call attempts when a reactivation lead replies.

### Copy Slots:
1. **Reactivation Call Script** -- Warm, reference what they replied to. Don't resell, just book.

### Rules:
- 3 call attempts with 15min gaps between each
- If answered, stop. If not, continue sequence.

---

## UTILITY WORKFLOWS
**GHL Names:** Turn Text AI ON/OFF, Remove All Tags, Kill Switch, Annual Re-Engagement

### Copy Slots:
1. **Annual Re-Engagement Email** -- 12-month check-in. "It's been a year. Things change. [industry-specific hook]."

### Rules:
- All other utility workflows are automation-only, no copy needed.

---

## SMS CHATBOT / CONVERSATIONAL AI
**GHL Name:** GHL Conversational AI (text AI)
**Trigger:** Inbound SMS when `ai text on` tag is active
**Purpose:** AI-powered text conversation that qualifies, answers questions, and books.

### Copy Slots:
1. **Knowledge Base Summary** -- What the bot knows about the business (from offer doc)
2. **Personality Guidelines** -- Tone, voice, style rules
3. **Greeting Response** -- How it responds to initial inbound texts
4. **Common Q&A Pairs** (8-12) -- FAQs about the business, pricing, process
5. **Booking Flow Language** -- How it guides to booking
6. **Objection Responses** (8-12) -- Price, timing, trust, competition objections
7. **After Hours Response** -- What it says outside business hours
8. **Handoff Rules** -- When to escalate to a human

---

## VOICE AI AGENTS
**Format:** 12-section RizzDial builder (see voice-agent-format.md)
**Templates:** Use templates from 02_RizzDial/templates/

### Agents to Generate:
1. **Speed-to-Lead Agent** (Primary) -- Full 12-section prompt. Use template 01, 02, or 03 depending on whether client wants transfer, booking, or both.
2. **No-Show Recovery Agent** -- Full 12-section prompt. Use template 04 or 09.
3. **Database Reactivation Agent** (if applicable) -- Condensed prompt. Use template 10.
4. **Webinar Invite Agent** (if applicable) -- Condensed prompt. Use template 11.

---

## 365-DAY EMAIL NURTURE
**GHL Name:** Long-term nurture (integrated into Workflow 05)
**Purpose:** 52 weekly Seinfeld-style emails that loop.

### Copy Slots:
- **Weeks 1-10:** Fully written (subject + body)
- **Weeks 11-52:** Angle + hook + CTA outline

### See: nurture-365.md for the full framework and angle bank.
