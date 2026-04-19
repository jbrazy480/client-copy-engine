# Client Copy Engine

> Generate ALL customized copy for a client's GHL snapshot workflows in one shot.

Feed it an offer doc + marketing strategy. Get back a complete Client Activation Playbook with 120+ pieces of copy, mapped to every workflow, ready to paste into GHL.

---

## What It Generates

| Section | What You Get |
|---------|-------------|
| **Opt-In Sequence** | 3 SMS + 1 email + 5 retries + voicemail script. AI voice call architecture with 8 retries over 2 days. |
| **Nurture Sequence** | 5 Seinfeld-style emails + 5 paired SMS. Story-driven, psychology-based. |
| **Appointment Reminders** | Confirmation email/SMS + 24hr/2hr/1hr/5min reminders + value injection + voicemail |
| **No-Show Recovery** | 3 SMS + voicemail. Empathy-first, identity-challenge close. |
| **Post-Sale / Closed Won** | Welcome email/SMS + Day 3/7/30/60 check-ins + review request + referral request + voicemails |
| **Database Reactivation** | 3 workflow angles + sentiment responses + reactivation call script |
| **SMS Chatbot** | Full knowledge base + 20+ Q&A pairs + booking flow + objection responses + after hours + handoff rules |
| **365-Day Nurture** | Multi-channel: weekly emails + paired SMS + AI voice calls (Day 3/7/14 then monthly). 10 fully written + 42 outlined. |
| **Implementation Checklist** | Every item mapped to where it goes in GHL |

---

## Installation

### Prerequisites
- [Claude Code](https://claude.ai/code) installed
- A Claude Code workspace

### Install the Skill

```bash
git clone https://github.com/jbrazy480/client-copy-engine.git ~/.claude/skills/client-copy-engine
```

That's it. The skill is now available in Claude Code.

### Verify Installation

Open Claude Code and type:

```
/client-copy-engine
```

You should see the skill activate and ask for your inputs.

---

## How to Use It

### Step 1: Prepare Your Inputs

You need 4 things before running the skill:

**1. The Offer Doc**
What the client sells, who they sell to, pricing, pain points, desired results, differentiators, unique mechanism, and guarantee. This can be a full document or a detailed summary.

If you don't have one yet, use the Offer Creation GPT to build it on a call with the client.

**2. The Marketing Strategy**
Where leads come from (Meta, Google, webinar, organic), what the ad/landing page promises, what the prospect sees before opting in. This determines the first message tone.

**3. Basic Config**
- Company name
- Agent name (what the AI introduces itself as)
- Timezone
- Business hours
- Industry/vertical

**4. Lead Source Details**
Where do leads come from? What did the ad promise? What is the CTA that triggers opt-in? A lead from a webinar signup gets a different first message than a lead from a Meta ad.

### Step 2: Run the Skill

Open Claude Code and say:

```
/client-copy-engine
```

Or just say "generate client copy" or "build the activation playbook."

Paste your offer doc, marketing strategy, config, and lead source info. The skill will confirm understanding with a brief summary, then generate the full playbook in one pass.

### Step 3: Review the Output

The skill saves a `client-activation-playbook.md` file to the client's folder at:
```
02_RizzDial/clients/[client-name]/client-activation-playbook.md
```

Review the copy. Check that:
- All SMS sounds human (no corporate speak, no em dashes)
- Emails are under 200 words with one CTA
- Chatbot Q&A covers the client's most common questions
- Voice call scripts sound natural with disfluencies
- The opt-in architecture shows AI call as the primary channel

### Step 4: Deploy as a Client Deliverable (Optional)

If you want a premium branded HTML page the client can use:

```
/deploy-client-playbook [client-name]
```

This converts the markdown into a beautiful web page with copy-to-clipboard buttons and deploys it to a unique Netlify URL like `client-name-playbook.netlify.app`.

---

## Copy Style Rules

Every piece of copy follows these rules:

- **No em dashes.** Commas and periods only. This is the #1 tell that copy is AI-generated.
- **Human-sounding SMS.** Lowercase starts sometimes, casual contractions ("gonna", "wanna"), sentence fragments, no semicolons, no "Dear" or "Hello."
- **Seinfeld-style emails.** Story-driven, entertaining, soft CTA. Never templated. Never corporate.
- **3-5% typo rate for chatbot.** Configured in GHL settings. Makes the bot sound human.
- **AI voice call is the primary channel.** Fires within 10-30 seconds of opt-in. SMS and email support it.
- **Loss aversion framing.** What they're LOSING, not what they'd gain.
- **Pattern interrupts** on every first touch.
- **20+ Q&A pairs** for the chatbot, not 12.
- **Multi-channel nurture.** Email + SMS + AI voice calls. Not email-only.

---

## File Structure

```
client-copy-engine/
  SKILL.md                    -- Main skill definition
  README.md                   -- This file
  references/
    snapshot-workflows.md     -- All 18 GHL workflows with copy slots
    copy-style-guide.md       -- Human-sounding copy rules
    sms-patterns.md           -- SMS templates per workflow
    email-patterns.md         -- Seinfeld framework + email templates
    voice-agent-format.md     -- 12-section RizzDial format
    chatbot-rules.md          -- SMS chatbot configuration
    nurture-365.md            -- 52-week multi-channel structure
    industry-angles.md        -- 9 verticals with specific angles
  assets/
    output-template.md        -- Exact output format
```

---

## Supported Industries

The skill has pre-built angles for:

1. Medical / Wellness (med spa, dental, chiro, PT)
2. Home Services (HVAC, solar, roofing, plumbing)
3. Real Estate (agents, investors, property management)
4. Insurance (health, auto, life, commercial)
5. Funding / Lending (business funding, mortgage)
6. Coaching / Info Products (courses, coaching, consulting)
7. SaaS / B2B (software, agencies, professional services)
8. Automotive (dealers, detailing, repair)
9. Universal Template (for any unlisted vertical)

---

## Updates

To get the latest version:

```bash
cd ~/.claude/skills/client-copy-engine && git pull
```

---

## Built by MetaTech AI / EveryThingAI

This skill powers the client activation process for EveryThingAI's RizzDial platform. It's designed to generate the highest-converting copy possible for GHL snapshot workflows, with sales psychology baked into every message.
