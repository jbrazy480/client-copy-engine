# Client Copy Engine

> Generate customized copy for a client's GHL snapshot workflows — only the parts they don't already have.

Feed it an offer doc + marketing strategy + an inventory of the client's EXISTING automations. Get back a complete Client Activation Playbook built around a canonical tag schema, a `double_call: true` AI dial cadence, an SMS chatbot, and an email library tuned to the client's nurture model. NEVER generates voicemail scripts.

---

## What It Generates

The skill asks what the client already has in place and only generates the gaps. The core spine (tags, dial cadence, chatbot, pre-call SMS) is always generated.

| Section | What You Get |
|---------|-------------|
| **Call Outcome Tag Schema** | Always. Canonical 8-tag taxonomy Blake applies after every call. This is the integration contract between RizzDial and the client's automations. |
| **AI Dial Cadence** | Always. RizzDial config with `double_call: true` + voicemail detection disabled. Daily dialing 9am-5pm CT M-F with 14-day safety cap → `ai-agent-exhausted`. |
| **Pre-Call SMS** | Always. Day 1 + Days 2+ templates. Fires 60s before the RizzDial webhook, once per day. |
| **AI Call On Reply** | Always. P1/P2 architecture. Reply triggers callback in 60s via double_call. |
| **SMS Chatbot** | Always. Full knowledge base + 20+ Q&A pairs + booking flow + objection responses + after hours + handoff rules. |
| **Post-Booking / Reminders / No-Show / Post-Sale / Database Reactivation** | Only if the client doesn't have their own. The skill asks upfront. |
| **Email Output** | Either a 52-week time-based multi-channel nurture OR an Email Library organized by psychological angle (Pain, Authority, Social Proof, Identity, Direct Ask, Seasonal), depending on the client's nurture model. |
| **Why This Works** | Always. Rationale for the major decisions. This is what gets playbooks signed. |
| **Implementation Checklist** | Every item mapped to where it goes in GHL + RizzDial. Includes explicit `double_call: true` and disable-voicemail config steps. |

**NEVER generated:** Voicemail scripts. Voice AI agent prompts (use `/new-voice-ai-prompt`). Any sections the client marked as already built.

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

You need 6 things before running the skill:

**1. The Offer Doc**
What the client sells, who they sell to, pricing, pain points, desired results, differentiators, unique mechanism, and guarantee.

**2. The Marketing Strategy**
Where leads come from (Meta, Google, webinar, organic), what the ad/landing page promises, what the prospect sees before opting in.

**3. Basic Config**
Company name, agent name, timezone, business hours, industry/vertical.

**4. Lead Source Details**
Where do leads come from? What did the ad promise? What is the CTA that triggers opt-in?

**5. Existing Automations Inventory** (CRITICAL — new in v2)
For each of these, tell the skill KEEP (client has it) or GENERATE (we need to build it): post-booking sequence, appointment reminders, no-show recovery, post-sale/closed-won, nurture emails, database reactivation, annual re-engagement. Sections marked KEEP are skipped entirely to avoid conflicts with the client's existing flows.

**6. Nurture Model** (new in v2)
Time-based (Day 1, Day 7, Day 30 calendar) or journey-stage (awareness → considering → ready-to-buy). Time-based gets a full 52-week calendar. Journey-stage gets an Email Library organized by angle.

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
- Section 1 of the doc is the Call Outcome Tag Schema (the backbone)
- All SMS sounds human (no corporate speak, no em dashes)
- Emails are under 200 words with one CTA
- Chatbot Q&A covers the client's most common questions
- Zero voicemail scripts anywhere in the doc
- RizzDial config section says `double_call: true` and voicemail detection disabled
- Dial cadence has a 14-day hard cap with `ai-agent-exhausted` auto-stop
- Sections the client marked KEEP are explicitly NOT generated

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
- **NO voicemails ever.** Non-negotiable. Use RizzDial's `double_call: true` instead. Voicemails waste per-send budget.
- **Canonical tag naming.** All outcome tags lowercase, hyphenated, no spaces: `ai-agent-booked`, `ai-agent-do-not-contact`, etc.
- **Tag schema always leads the doc.** Section 1 is always the Call Outcome Tag Schema.
- **Every recurring workflow has a safety cap.** Default: 14 business days → auto-stop tag.
- **Human-sounding SMS.** Lowercase starts sometimes, casual contractions ("gonna", "wanna"), sentence fragments, no semicolons, no "Dear" or "Hello."
- **Seinfeld-style emails.** Story-driven, entertaining, soft CTA. Never templated. Never corporate.
- **3-5% typo rate for chatbot.** Configured in GHL settings. Makes the bot sound human.
- **AI voice call is the primary channel.** Fires within 10-30 seconds of opt-in. SMS supports it.
- **Loss aversion framing.** What they're LOSING, not what they'd gain.
- **Pattern interrupts** on every first touch.
- **20+ Q&A pairs** for the chatbot, not 12.
- **Nurture format matches the client's model.** Journey-stage → Email Library by angle. Time-based → 52-week calendar. Not both.

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
