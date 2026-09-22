---
name: boss-pitch
description: Creates a decision brief: question first, analogy, options by gain, risk, cost and reversibility, then a recommendation with its downside. Use for technical, security, budget or vendor decisions.
license: MIT
metadata:
  version: "1.1"
---

# Boss Pitch

You need a decision. The decision-maker owns the consequence but may not share your technical context.
Your job is to make the **choice** clear without hiding anything that could materially change it.

**One test:** can they make an informed choice from the top half, with every decision-critical fact included? If not, rewrite.

## The shape

**1. The ask.** First line. A question they can answer.
> "Do we let the new service in through a locked slot, or give it the master key?"

**2. The picture.** Use one everyday analogy, in at most three sentences. Map it back to the real mechanism, and say what the analogy does not prove. Keep the scale of the risk honest.

**3. Why now.** What is blocked until they decide. What waiting costs — or "nothing urgent".

**4. The options.** Prefer two. Include defer or do nothing when viable, and never hide a materially different option. Use the same five lines for each:

| | A | B |
|---|---|---|
| What | | |
| Gain | | |
| Risk | a concrete bad outcome | a concrete bad outcome |
| Cost | | |
| Undo? | | |

**5. Your pick — and its downside.** One line each.

**6. What you need.** Exactly. A yes, a choice, a name. Or "nothing".

---
*They can stop here.*

---

**7. Detail.** Supporting evidence, numbers, and mechanism. Keep every fact that could change the choice above the stop line.

## Rules

- **Question first.** Never open with background.
- **Risks are outcomes, not labels.** Not "security risk" — "someone could read every password".
- **Keep the shortlist small.** Prefer two options, but include any materially different choice. Say what you ruled out and why.
- **Separate revocation from reversal.** Say whether you can stop future access and whether you can undo past effects. Irreversible choices earn a pause.
- **Name your own option's downside.** Otherwise you are steering, not informing.
- **Say how you know.** "I tested it", "I read it", or "I have not checked". Never "it should be fine".
- **Wrong earlier? Say so first.** Buried corrections cost trust.
- **No filler.** Cut any sentence whose removal does not change the choice or remove necessary context.
- **Short sentences. One idea each.** They may be reading on a phone.

## Example

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
