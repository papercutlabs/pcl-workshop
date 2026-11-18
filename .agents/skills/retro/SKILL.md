---
name: retro
description: "End-of-cycle retrospective. The agent self-critiques, participant reacts, and future-useful learnings are saved to memory, or turned into a skill, immediately. Trigger for: /retro, retrospective, wrap up, what did we learn, end of cycle."
---

# Retrospective — The Codification Loop

Run this at the end of each build cycle, or any time mid-session when something worth keeping surfaces and we need to capture it before it slips.

Goal is not a retro document. Goal is codification: improve the next cycle by saving what should be remembered to Claude's memory, and turning anything repeatable into a skill.

You are codifying two kinds of things:

- **Improvements** — what to do differently so the next cycle is better.
- **Facts** — what is now true about the participant's business, workflow, data, preferences, or constraints.

A fact with nothing "wrong" attached still gets codified. "The data refreshes every Monday" is worth remembering even if nobody made a mistake.

## How This Will Go (tell the participant upfront)

Before doing anything else, tell the participant what you are about to do:

> "I'm going to do the workshop retro now. First I'll reflect back what happened and capture your point of view — what worked, what felt wrong, and what facts about your work I should remember. Then we'll walk through what I'm saving to memory and any skill I'm making, so future sessions pick them up. The output is what gets saved, not a separate retro document."

Then start the procedure below.

## The Shape: Agent Self-Critiques First

Open by self-critiquing. You know your own failure modes best — surface them before the participant has to. They react, add what you missed, then you encode both.

This matches the react-not-articulate principle: do not ask the participant to invent feedback from a blank page. You propose; they react.

## Mid-Session Mode

`/retro` does not only run at end-of-cycle. If the participant says something that sounds like a learning mid-session — "oh wait, X always means Y", "we tried Z and it didn't work because W", "actually, can you not do A in this project" — surface it on the spot:

> "That sounds worth remembering for next time. I'll save it to memory unless you want it kept out."

If they agree, run a compressed version for that one learning:

1. State the learning back in one sentence.
2. Decide where it goes. A fact, preference, correction or decision is saved to memory. A procedure they will run again becomes a skill.
3. Generalise it so it helps future sessions.
4. Save it in front of them. For memory, say what you are saving, and they can check it with `/memory`. For a skill, make it with the skill-creator skill.
5. Read back what you saved.

Then continue whatever the participant was doing before. Do not run the full self-critique procedure for a single mid-session learning — that is saved for end-of-cycle.

## Procedure

### 1. Self-critique (you go first)

Look back across the cycle. Output a concrete self-critique in three short lists.

**What I got wrong / had to correct:**

- Specific things. Example: "I assumed the export had one row per order, but it had one row per item. I had to adjust the summary."
- Not vague self-improvement language.

**What worked:**

- Specific things that went smoothly and should be reinforced.
- Example: "Running the checks on the real spreadsheet caught the missing cancelled-order rule."

**What I learned about your work:**

- Facts about the business, process, files, timing, preferences, people, or constraints.
- Example: "The Tuesday report is for the ops lead, not finance, so the summary needs to focus on blockers, not accounting detail."

Keep each list to 3–5 items. Do not pad.

### 2. Let the participant react

Ask:

> "What did I miss or get wrong in that read?"

They may add:

- Things they noticed that you did not.
- Things you flagged that are not actually issues.
- Patterns they want to reinforce or avoid.
- Business context they want future sessions to remember.

Take what they add seriously. They see things you do not.

### 3. Find codification opportunities

For each item, decide where it belongs:

1. **Memory** — facts about the domain, workflow, data, timing, or people; preferences on output style, review style, wording, or pacing; corrections; and decisions, including tradeoffs and failed approaches and why.
2. **A skill** — a repeatable procedure or report they will run again. Make it with the skill-creator skill, or update the existing skill.

Claude's automatic memory is on, so the participant can also just say "remember that ...". `/memory` shows what was kept.

### 4. Generalise

Every rule or fact must be useful beyond this exact moment:

- Bad: "When the participant says 50 boxes, double-check."
- Good: "Always confirm quantities before placing orders."

- Bad: "The cancelled-order bug is fixed."
- Good: "When summarising orders, exclude cancelled orders and show the rule used."

### 5. Encode immediately

Make the changes now. Do not list what should change later.

Save the facts, preferences and decisions to memory. Turn any repeatable procedure into a skill with skill-creator, or edit the existing skill. Then read back what you saved briefly:

> "Saved to memory: the order-status rule and the Tuesday report audience. Future sessions will have those before building."

### 6. Close

Briefly summarise:

- What was built this cycle.
- What was saved to memory.
- Any skill made or changed.

## Output

The changed files are the real output. Do not create a standalone retro-notes file.

## Do Not

- Do not skip the self-critique step. If you genuinely have no specific mistakes, say so plainly so the participant can correct you.
- Do not skip the fact scan. Facts that are not tied to a mistake are the easiest to lose.
- Do not write a retro document as the output.
- Do not write business context into `CLAUDE.md`. It holds the workshop instructions only. Facts go to memory, procedures go to skills.
- Do not retroactively praise the participant or yourself. Retro is for encoding, not morale.
- Do not mention Git or commits unless the participant explicitly asks for version control.
