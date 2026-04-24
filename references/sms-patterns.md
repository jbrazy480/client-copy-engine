# SMS Craft — The Micro-Copy Discipline

> Read copy-style-guide.md first. This document is the tactical layer for every SMS you generate.
>
> SMS is the hardest copy discipline in direct response. Every word has to pull weight. 160 characters is a novel.

---

## THE FUNDAMENTAL SMS PRINCIPLE

A text message is a person texting. Not a brand broadcasting.

If the receiver can't imagine a real human pressing "send" on this message, the message fails.

Every rule below flows from this single principle.

---

## THE LOCK-SCREEN TEST

Phone lock screens show roughly the first 40-60 characters before the text gets cut off. That preview IS your headline. Everything that matters in the text must fit in those characters.

Good lock-screen previews (the reader sees this and pauses):
- "Hey {{first_name}}, quick question about the funding..."
- "this is Blake from Jeff's team. before you apply..."
- "Saw something that reminded me of our convo."
- "{{first_name}}?"

Bad lock-screen previews (ignored in 0.3 seconds):
- "Hi {{first_name}}! I hope this message finds you well..."
- "Thanks so much for reaching out! We are so excited..."
- "**PROMOTIONAL** Limited time offer..."

The first 50 characters is a billboard. Write it like one.

---

## LENGTH TIERS

### Tier 1: Under 70 characters — The Friend Text
Feels like a real person typing on their phone. Best for first touch, follow-ups, confirmations, and anything that needs to feel personal.

Examples:
- "Hey {{first_name}}, quick question about the funding"
- "{{first_name}}?"
- "Giving you a quick call right now"
- "not trying to blow you up, just want to help"

### Tier 2: 70-160 characters — The Short Message
One SMS segment. Enough to convey a full idea. Best for middle-of-sequence messages that need to deliver value or social proof.

Examples:
- "Most people with a 700+ score are sitting on $50-150K in funding and don't even know it. Takes 15 min to see where you stand."
- "We just helped a client with a similar profile pull $85K in round one. Reminded me of your situation."

### Tier 3: 160-320 characters — The Borderline Text
Two segments. Uses carrier concatenation. Risk of being flagged as promotional by carriers. Use sparingly, only when the content requires it.

NEVER GO OVER 320. At three segments, carrier filtering is aggressive. The message may not deliver at all.

---

## THE PHONE-IS-IN-HAND MOMENT

The highest-conversion SMS window is the 30-second moment right after the reader has picked up their phone for another reason (notification, text from a friend, email alert).

That's why:
- Pre-call SMS (60s before a dial) works — the notification puts the phone in hand, the call rings while they're still holding it
- The 30-second staggered 3-text pattern works — text 2 arrives while they're still looking at text 1
- Reply-triggered AI callbacks work — they just hit send, their hand is still on the phone

Every SMS strategy should respect this principle: **write for a reader holding their phone, not a reader who will "check messages later."**

---

## THE 3-TEXT SPEED-TO-LEAD PATTERN

Highest-converting inbound SMS sequence across every vertical we've tested. Use this for every speed-to-lead workflow.

### The sequence:

**Text 1** (fires 10-30 seconds after opt-in):
```
Hey {{first_name}}, quick question about the [specific thing they signed up for]
```

Mechanics:
- Under 70 characters. Looks like a friend texting.
- References what they JUST opted in for. Connects dots in their memory.
- Ends without a period. Feels like typing is still in progress.
- No link. No pitch. No CTA.

Psychology: Pattern interrupt. They expect a promotional message. They get what looks like a real question from a real person. Their brain leaves the "automation" bucket.

**Text 2** (30 seconds after Text 1):
```
This is [Agent] from [Company]. Before you [take the obvious next step], there's one thing you need to know.
```

Mechanics:
- Identity + curiosity gap. Now they know who's texting. Now they have an open loop.
- "One thing you need to know" is the hook. Their brain will work to close that loop.
- No link yet. The loop does the selling.

Psychology: Open loop. The Zeigarnik effect — incomplete information creates cognitive tension. They wait for text 3 to resolve it.

**Text 3** (30 seconds after Text 2):
```
Got 15 min this week? I can pull your [profile/numbers/situation] and show you [specific outcome]. {{booking_link}}
```

Mechanics:
- "Got 15 min this week?" is a permission close. Low-commitment ask.
- "I can pull your [profile]" = specific value offer, not a vague "chat."
- "Show you [specific outcome]" makes the payoff concrete.
- First link of the sequence.

Psychology: Earned ask. Texts 1 and 2 built curiosity. Text 3 gives them somewhere to put it. Click rate on this third text significantly exceeds standalone booking texts.

**Text 4** (24 hours later, if no response):
```
{{first_name}}?
```

Mechanics:
- Single word. Question mark. Under 20 characters.
- Looks like someone checking in on a conversation, not a marketing message.

Psychology: The highest-reply text ever tested. Creates guilt + curiosity simultaneously. Reader feels like they left someone hanging. They reply to close the social obligation.

### Why this specific staggering works:
- 10-30 seconds after opt-in = they're still on the phone, still holding it
- 30 seconds between texts = simulates real typing speed
- 24 hours for follow-up = long enough to not be annoying, short enough to stay top of mind

Variations for different industries exist but the structure is universal.

---

## THE RETRY SEQUENCE (for dial-support SMS)

When the AI dial isn't producing answers, retry SMS bridge the attempts. Each retry uses a different angle so the reader doesn't feel like the same message over and over.

### Retry 1 (same day, a few hours after initial sequence)
Angle: Casual nudge + restated value
```
Hey {{first_name}}, just making sure you saw this. We help [specific audience] [specific outcome]. Got a sec?
```

### Retry 2 (same day, later)
Angle: Empathetic / reduces pressure
```
Not trying to blow you up. Just don't want you to [common mistake] before we can help. Worth 2 min?
```

### Retry 3 (next morning, 9am)
Angle: Fresh day, social proof
```
Morning {{first_name}}. We just helped someone with a similar profile pull [specific result]. Happy to show you what yours looks like.
```

### Retry 4 (next afternoon, 2pm)
Angle: Loss aversion with a number
```
Real talk, most [audience descriptor] are sitting on [specific valuable thing] and don't even know it. Takes 15 min to find out.
```

### Retry 5 (48 hours, final)
Angle: First-name-only (the closer)
```
{{first_name}}?
```

### Retry sequence rules:
- Each retry uses a different psychological angle (value, empathy, social proof, loss aversion, curiosity)
- Never repeat the same language from a previous retry — the reader recognizes pattern and tunes out
- Always include the client's actual language (from offer doc) for the specific outcome
- Never use the word "following up" — it screams automation

---

## APPOINTMENT CONFIRMATION & REMINDER SMS

Only generate these if the client DOESN'T already have their own post-booking sequence. Check the Existing Automations Inventory first.

### Confirmation SMS (immediately after booking)
```
You're all set for {{appointment_date_and_time}}. Looking forward to [specific thing from offer]. Talk soon.
```

Under 120 chars. Warm, not corporate. Mentions what they'll get (not "your consultation").

### 24hr Reminder SMS
```
Hey {{first_name}}, quick prep for tomorrow. If you have [specific useful info], bring it. Makes the [duration] call way more useful.
```

Gives them something to do. Feels helpful, not nagging.

### 2hr Reminder SMS + Social Proof
```
2 hours out. Quick thing, we just [specific recent result for similar client]. Excited to show you what yours looks like.
```

Injects a real, specific client result right before the call. Builds anticipation.

### 1hr Reminder SMS
```
One hour out. See you soon {{first_name}}.
```

Simple. Short. Friendly.

### 5-minute Final SMS
```
Jumping on in 5. See you there.
```

Under 35 chars. Feels like a friend saying "omw."

---

## NO-SHOW RECOVERY SMS

Only generate if the client DOESN'T already have their own no-show sequence.

### 3-hour post-no-show SMS
```
Hey {{first_name}}, we missed you today. No worries at all, life happens. Want to grab another time? {{booking_link}}
```

Zero guilt. Opens the door without judgment. Low-friction reschedule.

### 2-day follow-up SMS (identity challenge)
```
{{first_name}}, did you give up on [specific goal they came in for]? If not, I saved your spot. Just pick a new time: {{booking_link}}
```

"Did you give up?" hits the pride/identity nerve. Triggers a defensive response ("no, I didn't give up") which converts.

### Re-engagement SMS (different angle)
```
{{first_name}}, quick thought. [Specific time-based consequence of waiting]. Worth 15 min to find out what's possible: {{booking_link}}
```

Pivots from rescheduling to a fresh angle. Feels like a new conversation.

---

## DATABASE REACTIVATION SMS

Only generate if the client DOESN'T already have their own reactivation flow.

### Initial hook SMS
```
Hey {{first_name}}, it's been a minute. Quick question, did you ever end up [solving the problem they came to solve]? We just [specific new development].
```

"Did you ever end up" is human. "Quick question" sets expectation. "We just" gives a reason to re-engage now.

### Positive sentiment response (they replied interested)
```
Nice! Let's get you on the calendar so we can take a look at [specific thing]. What day works this week? {{booking_link}}
```

Assumptive close. "Let's get you" beats "Would you like to schedule?"

### Negative sentiment response (they're not interested)
```
Totally get it. If anything changes down the road, you know where to find us. Have a great day {{first_name}}.
```

Graceful exit. Never pressure. Leaves the door open with dignity.

### Alternative angle SMS (second touchpoint)
```
{{first_name}}, quick question. Are you still [dealing with the problem]? Because we just helped someone with a similar situation [specific result].
```

Different hook than the first message. Specific result. Social proof.

### Final push SMS (last reactivation attempt)
```
Last one from me {{first_name}}. We have [specific real scarcity]. If you're still interested, grab a time: {{booking_link}}
```

Uses REAL scarcity only. Never fake it. "Last one from me" is honest and lands.

---

## THE AI CALL ON REPLY SMS

When a lead replies to any Blake text, the reply-triggered flow fires this pre-call SMS before the RizzDial webhook.

```
Hey {{first_name}}, saw your message. Giving you a quick call right now.
```

Under 75 chars. Sets expectation. Feels like a real person responding to their message. Highest answer rate of any outbound dial trigger.

---

## ANTI-PATTERNS (What NOT to generate)

Study these. If any of them appear in generated SMS, regenerate.

### Corporate openers (burn these)
- "Hi {{first_name}}! I hope this message finds you well."
- "Hello {{first_name}}, I wanted to reach out regarding..."
- "Dear {{first_name}}, Thank you for your interest..."
- "Greetings from [Company]..."

### Promotional phrasing (flagged by carriers)
- "LIMITED TIME OFFER"
- "Don't miss out!"
- "Act now!"
- Excessive exclamation points (!!!)
- ALL CAPS IN MESSAGE BODY

### Vocabulary that screams automation
- "Per our previous conversation"
- "At your earliest convenience"
- "Kindly"
- "Regarding"
- "Pertaining to"
- "Please be advised"
- "I hope you're doing well"
- "Just checking in" (overused, signals spam)

### Structural mistakes
- Bullet points in an SMS (nobody texts with bullets)
- Semicolons (nobody texts with semicolons)
- Em dashes (never)
- Links in the first text of a sequence (earn the click first)
- Multiple CTAs in one text ("book a call AND check out our website AND follow us on Instagram")

### The "trying too hard" tells
- Starting with a corny hook ("Imagine this...")
- Over-styled text ("THIS. CHANGES. EVERYTHING.")
- Emoji avalanches (🔥🔥🔥 or 💰💯🚀)
- Fake personalization ("Hey {{first_name}}! As someone who clearly values success...")
- The "question, answer, question" pattern ("Did you know X? Well it's true. So when will you Y?")

---

## VOICE CHARACTERS

The best SMS sounds like a specific person, not a brand. Each client needs a defined character.

### Example: Blake (Baxter Funding)
- 28 years old
- Works on Jeff Baxter's funding team
- Direct but warm
- Uses "real talk" and "look" occasionally
- Drops apostrophes casually in texts ("dont" sometimes, but not always)
- Never corporate
- Tone: confident without being arrogant, like the best sales rep they've ever texted

### How to define a voice character when generating for a new client:
From the offer doc, extract:
- The agent's name (if specified)
- The client's brand tone (direct? warm? educational? irreverent?)
- Any distinctive language patterns the client uses

Build a one-paragraph character profile at the top of the generated playbook that defines the SMS voice. Every text should sound like that specific person.

**Bad practice:** Every SMS sounds like "the company" wrote it.
**Good practice:** Every SMS sounds like Blake, or Tyler, or whoever the defined agent is.

---

## THE HUMAN-SOUNDING RULES

These are the micro-rules that separate "clearly human" from "clearly bot."

### Punctuation
- Drop the period on short texts sometimes ("Hey just checking in" beats "Hey, just checking in.")
- Use commas casually, not always grammatically ("real talk most people...")
- Question marks are your friend (they trigger reply-intent)
- Never use semicolons
- Never use em dashes

### Capitalization
- Roughly 1 in 4 texts starts with a lowercase letter ("hey {{first_name}}, quick thing")
- Proper nouns and sentence starts are the only consistent caps
- ALL CAPS only for emphasis on a single word if it serves the voice ("That is NOT how it works")

### Contractions
- Always use them. "you're" not "you are." "we'll" not "we will." "can't" not "cannot."
- Dropped apostrophes in casual contexts ("dont" or "youre" — one or two per sequence, not every message)
- Casual contractions: "gonna" not "going to," "wanna" not "want to," "kinda" not "kind of"

### Fragments
- Sentence fragments are good. "Worth 2 min?" beats "Would this be worth two minutes of your time?"
- One-word replies hit. "Nice." "Gotcha." "Real."

### Reaction words (crucial for chatbot)
- "Got it"
- "Makes sense"
- "For sure"
- "Nice"
- "Gotcha"
- "Real talk"
- "Fair enough"
- "Yeah that's a good one"

These humanize the response before the next question. Always react before asking.

---

## EXAMPLES FROM THE BAXTER BUILD (study these — they're the bar)

Pre-call SMS Day 1:
```
Hey {{first_name}}, this is Blake from Jeff Baxter's team. You just signed up to learn about the TLU method. Giving you a quick call in a sec.
```

Pre-call SMS Days 2+:
```
Hey {{first_name}}, Blake again from Jeff's team. Trying you one more time about the funding. Quick call incoming.
```

Retry SMS (loss aversion with specific number):
```
Real talk, most people with a 700+ score are sitting on $50K to $150K in accessible capital and don't even know it. Takes 15 min to find out where you stand.
```

Retry SMS (empathy):
```
Not trying to blow you up. Just don't want you to apply somewhere on your own and mess up your profile before we can help. Worth a quick look?
```

Final SMS:
```
{{first_name}}?
```

Notice across all of them:
- No em dashes
- No corporate speak
- Specific numbers ($50K to $150K, 700+, 15 min)
- Casual rhythm
- One CTA each
- Feels like Blake — a specific person — sent it

---

## THE FINAL SMS TEST

Before any SMS ships, check:

1. **Is it under 160 characters?** (Under 70 is ideal for first touch.)
2. **Does the first 50 characters earn the preview?** (What shows on the lock screen.)
3. **Would a real person text this?** If it sounds like a brand, rewrite.
4. **Is there one CTA, or none?** Multiple asks in one text = no action.
5. **Is there a real detail — a number, a name, a specific thing?** Vague SMS gets ignored.
6. **Are there AI tells?** Search for "I hope," "per our," "regarding," em dashes, semicolons.
7. **Does it match the voice character?** Blake texts differently than Mikayla texts differently than Tyler.

Seven checks. If it passes all, ship.
