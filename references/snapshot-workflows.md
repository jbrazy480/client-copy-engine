# GHL Snapshot Workflows -- Copy Map

> Every client gets these workflows imported via the MetaTech/RizzDial snapshot.
> This document defines exactly what copy each workflow needs.
> Generate copy for EVERY slot listed below.

---

## WORKFLOW 01: OPT-IN SEQUENCE
**GHL Name:** 01 -- Opt-In Workflow (AI Calls, SMS & Emails)
**Trigger:** Tag `new lead`
**Purpose:** AI VOICE CALL is the PRIMARY channel. Fires within 10-30 seconds. SMS and email fire simultaneously as support channels. 8 call attempts over 2 days with SMS between retries.

### Architecture (CRITICAL -- the team must understand this):
```
SECOND 0-10:  Lead opts in. Tag "new lead" applied.
SECOND 10-30: THREE things fire simultaneously:
              1. AI VOICE CALL via webhook (primary conversion tool)
              2. SMS sequence starts (3-text staggered pattern)
              3. Email 1 sends

IF CALL ANSWERED: Agent qualifies live. Books or transfers. ALL workflows stop.
IF NOT ANSWERED (tag: dna):
  +10 min:  AI Call #2 + pre-call SMS
  +30 min:  AI Call #3 + retry SMS
  +1 hour:  AI Call #4
  +2 hours: AI Call #5 + retry SMS
  +4 hours: AI Call #6 (last Day 1)
  Next 9am: AI Call #7 + retry SMS
  Next 2pm: AI Call #8 + retry SMS
  48 hours: Final SMS (first name only)

AFTER ALL ATTEMPTS: Opportunity created > Nurture stage > tag: nurture-active
```

### Copy Slots:

**PRIMARY: AI Voice Call (fires within 10-30 sec)**
The voice agent handles the call. Copy for the agent is generated separately via /new-voice-ai-prompt or the existing agent is already built. The copy engine generates the voicemail script the agent leaves when nobody answers.

1. **Voicemail Script** -- Left on any unanswered call. Identifies self, references what they signed up for, states the value of the call, gives callback number. Under 30 seconds.

**SUPPORT: SMS (fires simultaneously with first call)**
2. **SMS 1** (Immediate, with first call) -- Short, references what they signed up for. NOT just "Hey {{first_name}}" alone. Must connect to the ad/offer they responded to.
3. **SMS 2** (30 sec after SMS 1) -- Company intro + curiosity hook about why they need to talk before applying anywhere
4. **SMS 3** (30 sec after SMS 2) -- Booking link + CTA framed as "see your number" not just "book a call"

**SUPPORT: Email (fires simultaneously with first call)**
5. **Email 1** -- Value-forward welcome. Explains what happens on the call (we pull your profile and show you your actual number). Sets expectation for the call they're about to receive. Subject line required.

**RETRIES: SMS between call attempts (only fires if previous call unanswered)**
6. **Pre-Call SMS for Retry #2** (10 min) -- "Tried calling, trying again" 
7. **Retry SMS after Call #3** (30 min) -- Different angle: fear of applying wrong
8. **Retry SMS after Call #5** (2 hours) -- Empathetic: "not trying to blow you up"
9. **Retry SMS after Call #7** (Next morning 9am) -- Fresh day, social proof angle
10. **Retry SMS after Call #8** (Next afternoon 2pm) -- Loss aversion with specific dollar amount
11. **Final SMS** (48 hours, no more calls) -- First name only with question mark: "{{first_name}}?"

**POST-CALL: Transcript Analysis**
After every call, the Post Call Transcript Analysis workflow categorizes the outcome:
- INTERESTED_NOT_BOOKED: Continue sequence
- NOT_INTERESTED: Tag, remove from calls, keep in email nurture
- DND: Tag, remove from ALL workflows

### Rules:
- AI VOICE CALL is the primary channel. Everything else supports it.
- Business hours only (9am-5pm client timezone) for all calls
- Stop ALL workflows if appointment is set (tag: `ai appt set`)
- Max 8 call attempts over 2 days. Do not exceed.
- After all attempts with no booking, move to nurture (tag: `nurture-active`)
- The SMS 1 must reference what the lead signed up for (the ad, the webinar, the offer). NOT a generic greeting.

---

## WORKFLOW 05: NURTURE SEQUENCE (MULTI-CHANNEL)
**GHL Name:** 05 -- Nurture Sequence (Email + SMS + AI Voice Calls)
**Trigger:** Tag `nurture-active`
**Purpose:** 365-day multi-channel nurture. THREE channels working together: Email (weekly Seinfeld), SMS (paired with emails), AI Voice Calls (Day 3, 7, 14, then monthly). Loops after completion.

### Architecture:
```
WEEKLY PATTERN:
  Day 1: Email (Seinfeld style)
  Day 2: SMS (references the email topic, 5 min offset)

AI CALL SCHEDULE:
  Day 3: AI call (warm check-in, gated by ai appt set)
  Day 7: AI call (value-based, share insight)
  Day 14: AI call (soft urgency, last early attempt)
  Then MONTHLY: AI call (Phase 3-5, belief building + reactivation)

PHASE CADENCE:
  Phase 1 (Weeks 1-2): Daily email + daily SMS + AI calls Day 3, 7, 14
  Phase 2 (Weeks 3-6): 3 emails/week + 2 SMS/week + AI call weekly
  Phase 3 (Weeks 7-12): 2 emails/week + 1 SMS/week + AI call biweekly
  Phase 4 (Weeks 13-26): Weekly email + biweekly SMS + monthly AI call
  Phase 5 (Weeks 27-52): Weekly email + 2 SMS/month + monthly AI call
```

### Copy Slots:

**EMAILS (Seinfeld style, fully written for first 10, outlined for 11-52)**
1. **Email 1** -- Story-driven. Hook + story + bridge + soft CTA. Under 200 words. Subject required.
2. **Email 2-10** -- Rotate through 7 core angles (Invisible Cost, Unused Value, Authority, Price Reframe, Identity Shift, Speed, Call-Out)
3. **Emails 11-52** -- Angle + hook + CTA outline

**SMS (Paired with each email, different angle)**
4. **SMS 1-10** (paired with emails 1-10) -- Conversational, references the email topic, under 160 chars
5. **SMS 11-52** -- Hook outline

**AI VOICE CALLS (Voicemail scripts)**
6. **Day 3 Voicemail** -- Warm check-in, reference their initial interest, offer the free assessment
7. **Day 7 Voicemail** -- Value-based, share a quick insight or specific result
8. **Day 14 Voicemail** -- Last early attempt, soft urgency, "last check-in for a bit"
9. **Monthly Voicemail Template** -- Rotating topics: new client results, rate updates, seasonal windows, direct asks. One template with topic rotation list.

### Rules:
- ALL three channels must be generated for every client. Email-only nurture is NOT acceptable.
- SMS references the email topic but uses a DIFFERENT angle (don't repeat the same message)
- AI calls gated by `ai appt set` tag. If present, STOP calling.
- Business hours only for AI calls
- Later waits increase to 30 days between email touches in Phase 5
- Sequence restarts after week 52. Nobody remembers an email from 9 months ago.
- Seinfeld emails: story-driven, entertaining, soft CTA. No corporate language. No em dashes.

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
