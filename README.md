# pcl-workshop

Papercut Labs workshop scaffolding for non-technical participants using the Claude desktop app.

## For workshop participants — paste this to start

1. Open the Claude desktop app.
2. Start a new session.
3. Select a folder to work in. Any normal working folder is fine — your Documents, Desktop, or a projects folder. Just don't pick your home folder directly.
4. Paste this prompt:

```text
Read https://raw.githubusercontent.com/papercutlabs/pcl-workshop/master/README.md and follow the "Claude desktop app setup" section to set up a workshop project for me.
```

Claude will set the workshop up in the folder you selected.

The workshop loop is:

1. **Interview** — clarify the problem by reacting to concrete statements and short questions. Output: `problem-brief.md`.
2. **Solutioning** — propose a useful deliverable, output format, plan, and concrete checks. Output: `plan-brief.md`.
3. **Build** — make the thing described in the plan.
4. **Retro** — reflect, capture your point of view, and save future-useful facts, preferences and decisions to Claude's memory, and turn anything you will run again into a skill.

## What's inside

- `CLAUDE.md` — the short workshop instructions. It holds no business context. Facts, preferences and decisions go to Claude's own memory (`/memory` shows what was kept), and procedures you will run again become skills.
- `.agents/skills/` — the skill source copied into Claude's global skills folder during setup:
  - `/interview`
  - `/solutioning`
  - `/retro`
  - `/give-feedback` — correct how Claude is working mid-session, and make the fix stick

## Repo layout

```text
pcl-workshop/
├── README.md                 ← setup instructions read by Claude
├── CLAUDE.md                 ← copied into the participant's workshop folder
└── .agents/skills/           ← copied into Claude's global skills folder
    ├── interview/SKILL.md
    ├── solutioning/SKILL.md
    ├── retro/SKILL.md
    └── give-feedback/SKILL.md
```

The workshop files (`CLAUDE.md` plus the skills) install into whatever normal working folder the participant selected (Documents, Desktop, or a projects folder). The only folder to avoid is the home folder (`~`) directly.

## Claude desktop app setup

If you are Claude reading this README to set up a workshop project for a participant, follow this section.

### 1. Choose the folder

Run:

```bash
pwd
```

If the current folder is a **normal working folder** — anything that isn't the home directory (`~`) itself, e.g. Documents, Desktop, or a projects folder — it's fine. Set the workshop up right here and continue to the next step. Do not create a new nested folder or ask the participant to switch; use the folder they selected.

The one folder to avoid is **home (`~`) directly** — installing the workshop there clutters it. Only if `pwd` shows you are in the home folder, create a dedicated workshop folder and use that instead:

```bash
mkdir -p ~/Documents/projects/workshop/pcl-workshop
```

Then tell the participant, in plain English:

> "I've set up a workshop folder at `~/Documents/projects/workshop/pcl-workshop`. Start a new session in the Claude desktop app, select that folder, and paste the setup prompt again."

Then **stop** — don't continue installing into home.

### 2. Fetch the workshop kit

Run:

```bash
git clone --depth 1 https://github.com/papercutlabs/pcl-workshop.git /tmp/pcl-workshop-src
```

If that fails because git or the network is unavailable, try this fallback:

```bash
curl -fsSL https://github.com/papercutlabs/pcl-workshop/archive/refs/heads/master.tar.gz | tar -xzC /tmp && mv /tmp/pcl-workshop-master /tmp/pcl-workshop-src
```

### 3. Install the files

Skills install globally so Claude can use `/interview`, `/solutioning`, `/retro`, and `/give-feedback` from the workshop session. `CLAUDE.md` installs into the workshop folder and gives Claude the workshop instructions.

First install the skills:

```bash
mkdir -p ~/.claude/skills
cp -r /tmp/pcl-workshop-src/.agents/skills/* ~/.claude/skills/
```

Then install the workshop instructions file. If `./CLAUDE.md` already exists, do not overwrite it silently. Tell the participant you found an existing `CLAUDE.md` and ask whether to replace it or merge the workshop instructions into it.

If there is no existing `CLAUDE.md`, run:

```bash
cp /tmp/pcl-workshop-src/CLAUDE.md ./CLAUDE.md
```

If the participant chooses to merge instead of replace, preserve their existing notes and add the workshop instructions from `/tmp/pcl-workshop-src/CLAUDE.md`.

### 4. Clean up

Run:

```bash
rm -rf /tmp/pcl-workshop-src
```

### 5. Verify

Run:

```bash
ls -la CLAUDE.md ~/.claude/skills
```

Expected:

- `CLAUDE.md` exists in the workshop folder.
- `~/.claude/skills/` contains `interview/`, `solutioning/`, `retro/`, and `give-feedback/`.

### 6. Tell the participant what's next

Tell them in plain English:

> "Workshop folder is ready. Start a new session in the Claude desktop app and select `~/Documents/projects/workshop/pcl-workshop` so Claude picks up the workshop instructions. Then tell me what you want to work on and I'll use `/interview` to walk through it."

Then **stop**. Do not auto-fire `/interview`. The participant needs a fresh session so Claude reads the local `CLAUDE.md`.

## Troubleshooting

**Skills do not appear after setup**

Start a new session in the Claude desktop app and select the workshop folder. Skills and project instructions are picked up when the session starts.

**`CLAUDE.md` does not seem to be used**

Start a new session in the Claude desktop app and select `~/Documents/projects/workshop/pcl-workshop`.

**Fetching the workshop kit fails**

Tell the participant:

> "I could not download the workshop kit from GitHub. Please ask the facilitator for help with the workshop setup."
