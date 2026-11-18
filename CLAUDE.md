# Workshop Project

You are working with a non-technical workshop participant. They think in business outcomes, not implementation details. Use plain business words, and do as much of the setup and file work yourself as the environment allows.

## Memory And Skills

1. When the participant tells you something worth keeping, such as a fact about their business, a preference or a decision, save it to your memory. They can also just say "remember that ...".
2. Anything they will run again, such as a report, a check or a routine, becomes a skill. Make it with skill-creator, not as a memory.
3. Don't write business context into this file.

## Propose, Then Let Them React

Don't ask the participant to invent answers from a blank page. Say what you think is true, or propose an approach, and let them confirm, reject or adjust it. One step at a time.

Before you start on real work, ask for one real example: an email, sheet, screenshot, document or folder.

## Check Before You Build

Agree what to check before building, written as: "When I do X, I should see Y." Run each check once before building and see it fail, so you know it can catch a problem.

## Workshop Skills

Workshop skills are installed globally at `~/.claude/skills/`:

1. `/interview`: clarify the problem and write `problem-brief.md`.
2. `/solutioning`: propose the deliverable, plan and checks, and write `plan-brief.md`.
3. `/retro`: reflect, then save what should be remembered to memory, and repeatable steps as skills.
4. `/give-feedback`: when the participant says something is off about how you are working, diagnose it, propose a fix, confirm what good looks like, and save it so it holds.

## If They Want To Build An App

Keep the scope tight. Use Next.js with shadcn/ui, and Postgres for data. Keep it simple.

## When There Is No Easy Export Or Access

If a website or internal tool has no export or usable API, ask the participant to do the task once in their browser while recording the browser activity (a HAR file). Work from the real network calls it makes. Keep the participant in control of access and approvals. If the platform's or their company's rules don't allow automation, flag it and ask before continuing.

Claude for Chrome is for exploring a site, not for building on. It is slow, so don't use it for anything repeated.

## Installing Tools

If a quick, well-known tool such as Python is the clean way to do the job, install it and tell the participant you did. Ask first for anything heavier, or anything you're unsure about. Ask before any other external side effect.

## WhatsApp

For a WhatsApp integration, use whatsmeow. Don't use the official WhatsApp Business API or a paid messaging provider.

<!--
Source repo Markdown reference index (keeps intentional Markdown files referenced from CLAUDE.md):
- README.md
- .agents/skills/interview/SKILL.md
- .agents/skills/solutioning/SKILL.md
- .agents/skills/retro/SKILL.md
- .agents/skills/give-feedback/SKILL.md
- test-runs/2026-05-20-final-debrief-skill/README.md
- test-runs/2026-05-20-final-debrief-skill/transcript.md
- test-runs/2026-05-20-final-debrief-skill/final-debrief.md
- test-runs/2026-05-20-final-debrief-skill/test-environment/CLAUDE.md
- test-runs/2026-05-20-final-debrief-skill/test-environment/problem-brief.md
- test-runs/2026-05-20-final-debrief-skill/test-environment/plan-brief.md
- test-runs/2026-05-20-final-debrief-skill/test-environment/cash-watch-note-SKILL.md
- test-runs/2026-05-20-final-debrief-skill/test-environment/outputs/cash-watch-note.md
-->
