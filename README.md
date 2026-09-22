# boss-pitch

An [Agent Skill](https://agentskills.io) that helps an AI agent structure a clear, brief decision request for a busy decision-maker.

You ask for approval. The agent puts the question first, gives one everyday picture, compares the options side by side, recommends one, and states the downside of its own pick. The format aims to keep every decision-critical fact above the stop line.

## Why

AI agents can produce long, careful, hedged answers. A manager reading on a phone may need the question, the choice, and the material risk first. Supporting detail can follow below the stop line; any fact that could change the choice must stay above it.

This skill also discourages two habits that can distort a pitch:

- **Steering.** The agent must name the downside of its own recommendation.
- **Hiding options.** "Wait" or "do nothing" stays on the table when it is a real choice.

## When the agent uses it

When you ask it to get a decision, approval or sign-off from someone who does not share your technical background — a manager, an executive, a client, a stakeholder. Typical cases: a security change, a vendor choice, a budget request, a risky deployment.

## What the output looks like

> **Ask:** Locked slot or master key for the new delivery service?
>
> **Picture:** A building has 20 flats, and a new courier needs to reach flat 7. A master key opens every flat; a locked delivery slot accepts one defined kind of envelope for flat 7 only. If the courier is compromised, the key exposes every flat, while the slot permits only the defined delivery.
>
> **Reality check:** This analogy compares access scope, not likelihood or downstream impact.
>
> **Why now:** Nothing reaches flat 7 until you choose. Waiting is safe — it only delays.
>
> | | Slot | Master key |
> |---|---|---|
> | What | One fixed delivery action for flat 7 | Access to every flat |
> | Gain | Limits the courier to the needed action | Fastest to set up |
> | Risk | Courier could misuse that fixed action | Courier could access all 20 flats |
> | Cost | Create, test, and review one narrow permission | Issue and manage one broad key |
> | Undo? | Revoke the permission; past effects remain | Revoke the key; copied information or past effects remain |
>
> **Pick:** Slot. Downside: one more step and a review first.
>
> **Need:** Yes or no on the slot.

All the rules are in [`skills/boss-pitch/SKILL.md`](skills/boss-pitch/SKILL.md).

## Install

**Coding agents supported by the [skills CLI](https://github.com/vercel-labs/skills)**, including Claude Code, Codex and Cursor:

```bash
npx skills add leotong628/boss-pitch
```

**Claude Code, by hand:** copy the `skills/boss-pitch` folder into `~/.claude/skills/` (all projects) or `.claude/skills/` (one project).

**Claude.ai:** ensure *Code execution and file creation* is enabled under *Settings → Capabilities*. Create a ZIP whose root contains the `boss-pitch/` folder and its `SKILL.md`, then go to *Customize → Skills*, click *+ → Create skill → Upload a skill*, and upload the ZIP.

## Use it

Ask in plain words. For example:

- "Pitch this to my manager — we need a yes on the database migration."
- "Write this up for the CFO. She has to choose between the two vendors."

On agents that support automatic skill selection, the description may cause the skill to load when you ask for a technical, security, budget or vendor decision.

## The rules, in short

- The question comes first. Never background first.
- A risk is a concrete outcome, not a label. Not "security risk" — "someone could read every password".
- Say how you know: tested, read, or not checked.
- Say whether a choice can be undone — and what cannot be undone even after you revoke access.
- If you were wrong earlier, say so first.

## License

[MIT](LICENSE)
