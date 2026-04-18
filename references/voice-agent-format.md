# Voice AI Agent Format -- Bridge Reference

> This file tells the copy engine WHAT format to use for voice agents.
> For the FULL generation rules, read the canonical files listed below.

---

## THE 12-SECTION RIZZDIAL BUILDER FORMAT

Every voice AI agent prompt must be pre-sliced into exactly 12 sections:

| # | Section Name | What Goes Here |
|---|-------------|---------------|
| 1 | Project Instructions / Request | Mission, who the prospects are, objectives, timezone, call length target |
| 2 | Greetings | Pattern-interrupt opener, time contract, permission close |
| 3 | Call Flow | Stage order with arrows, golden rules, timing targets |
| 4 | Character | Agent name, role, personality, disfluencies, signature phrases, mindset |
| 5 | Transfer Call | When/how to hand off to human. DO NOT EDIT block for most agents. |
| 6 | Critical Instructions / Guardrails | Rules #0-#4, iPhone screening, hard rules, AI disclosure, exit rules |
| 7 | Custom Field References | CRM variables table, data captured, GHL functions, tags applied |
| 8 | What Your Company Does | 15-20 sec elevator pitch (short + extended version) |
| 9 | Script | Actual spoken dialogue with stage tags, one question per line, pause instructions |
| 10 | Objection Handling | 12+ objections with psychology responses (acknowledge, isolate, reframe, forward) |
| 11 | Booking Flow | GHL calendar logic, availability check, slot presentation, confirmation |
| 12 | FAQ / Knowledge Base | 10+ Q&A pairs, industry-specific, "are you AI?" response |

---

## CANONICAL FILES TO READ

Before generating any voice agent section, the copy engine MUST read:

1. **`02_RizzDial/templates/GENERATION-ENGINE.md`** -- Full generation rules, section-by-section guide, quality checklist
2. **`02_RizzDial/templates/MODULE-sales-psychology-hooks.md`** -- Pattern interrupts, time contracts, SPIN, loss aversion, all frameworks
3. **`02_RizzDial/templates/MODULE-iphone-call-screening.md`** -- Required for all outbound agents
4. **`02_RizzDial/templates/MODULE-ghl-booking-flow.md`** -- Calendar booking logic (DO NOT EDIT block)
5. **`02_RizzDial/templates/MODULE-industry-discovery-questions.md`** -- Vertical-specific qualification questions
6. **`02_RizzDial/MASTER_PROMPT_GUIDE.md`** -- Top-priority rules, voice style, quality rubric

---

## WHICH TEMPLATE TO USE PER USE CASE

| Use Case | Template File | Key Difference |
|----------|--------------|----------------|
| Speed-to-lead (transfer only) | 01-speed-to-lead-live-transfer.md | Qualifies then warm transfers |
| Speed-to-lead (booking only) | 02-speed-to-lead-booking.md | Qualifies then books appointment |
| Speed-to-lead (both) | 03-speed-to-lead-both.md | Tries transfer first, falls back to booking |
| No-show recovery | 04-no-show-recovery.md | Empathy-first, reschedule focus |
| Long-term nurture | 05-360-nurture.md | Warm reactivation of cold leads |
| Annual re-engagement | 06-annual-reengagement.md | 12-month check-in |
| Appointment reminder | 07-appointment-reminder-2hr.md | Casual confirmation + excitement |
| Post-sale welcome | 08-post-sale-welcome.md | Onboarding, expectation setting |
| No-show v2 | 09-appointment-no-show-v2.md | Alternative no-show script |
| Database reactivation | 10-database-reactivation.md | Cold lead + new offer angle |
| Webinar invite | 11-webinar-invite.md | Curiosity, tease-don't-teach, under 90 sec |

---

## KEY RULES FOR VOICE SECTIONS

1. ONE question at a time. Always. Non-negotiable.
2. Disfluencies IN the script lines ("um," "uh," "gotcha"), not just described in Character.
3. Pattern-interrupt opener (never "Hi, is this {{first_name}}?")
4. Time Contract ("43 seconds, 3 questions, you'll know if this is worth your time")
5. Permission closes minimum 3 per call ("Sound good?" "Fair enough?")
6. Loss aversion math before any booking/transfer attempt
7. Assumptive Bridge for close (never ask IF, ask WHEN/HOW)
8. Silence Bomb at end ("Anything I didn't cover?" then SHUT UP 5 seconds)
9. iPhone Call Screening handler in Guardrails (all outbound)
10. Never speak variable names out loud
11. Never say "as an AI"
12. Pause after every question. Wait for full response.
