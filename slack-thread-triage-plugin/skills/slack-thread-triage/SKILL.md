---
name: slack-thread-triage
description: Analyzes Slack/Teams conversation threads to detect consensus, unresolved questions, and next steps, then generates the minimum viable reply to move the thread forward.
---

# Slack Thread Comprehension & Minimal Responder

## Objective
Read an ongoing chat thread between two or more participants, determine the conversational state (alignment, pending decisions, blockers), and craft the minimum sufficient reply.

## Analysis Protocol
Before drafting a response, evaluate the thread against four checks:

1. **Consensus Check**: Has agreement already been reached (e.g., "+1", "sounds good", "let's do that", explicit confirmation)?
2. **Alignment Check**: Are the participants genuinely aligned, or is there an unaddressed misunderstanding/misalignment?
3. **Next Steps & Ownership**: Are action items already assigned and clear, or is the conversation stalling due to missing ownership?
4. **Pending Ask**: Is there a direct, unanswered question waiting on someone?

---

## Response Decision Matrix

- **If mutual agreement is already reached and next steps are clear:**
  - *Action:* No heavy explanation. Draft a one-line closure or acknowledgment (e.g., confirming receipt, date/time acknowledgment, or an emoji reaction recommendation).
- **If next steps are ambiguous or missing an owner:**
  - *Action:* Formulate a 1-sentence prompt assigning ownership or asking for the missing variable.
- **If participants are misaligned:**
  - *Action:* State the single point of divergence in 1 sentence and propose a direct resolution.
- **If a direct question is pending:**
  - *Action:* Provide the direct, concrete answer in 1–2 sentences maximum.

---

## Output Format
Always format the output strictly as follows:

**Thread Status**: [Aligned & Settled | Action Items Pending | Misaligned / Clarification Needed]  
**Key Consensus**: [1 short sentence stating what both sides already agree on, or "None"]  
**Minimal Reply**:  
> "[Drafted reply ready to send, 1–2 sentences max. Professional, zero conversational padding.]"