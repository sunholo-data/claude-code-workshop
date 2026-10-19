# Trust is earned per action

You don't trust Claude or distrust it as a whole. You trust it with particular actions: saving a
file, yes; committing, yes; publishing to everyone, not without a look. Each kind of action sits
on its own rung, and it climbs only on evidence from the rung below. This is the delegation ladder
from Sunholo's Decision Budget, and Claude Code's permission modes and rules map onto it directly.

| Rung | What it means | In Claude Code |
|---|---|---|
| ■□□□□ **held** | A person decides, every time, and it stays that way | A **deny** rule: Claude may never do it, in any mode |
| ■■□□□ **instrumented** | Nothing is decided yet, but you can see what would be | **Plan** mode: Claude shows what it would do and changes nothing |
| ■■■□□ **shadow** | It decides in private; nothing counts yet | Work on a **branch** or a copy: nothing counts until you merge it |
| ■■■■□ **proposing** | It acts; a person approves before it counts | **Manual** mode, and **ask** rules: you approve each action |
| ■■■■■ **automated** | Unattended inside stated limits; outside them it stops and asks | **Accept edits** or **Auto**, plus **allow** rules. Your ask and deny rules are the limits, and they still hold in Auto |

## Do

1. Ask Claude to copy `samples/` to a new folder called `ladder-practice` **next to** the workshop
   folder (not inside it), make it a git repository, and then open a **+ New session** on it. It has
   no rules yet, which is the point. You'll run the same task three times, so each run needs a fresh copy.
2. The task, each time: *"Sort the files in ladder-practice into folders by type, write a short
   README listing them, and commit."*
3. **Predict:** how many times will Claude stop and ask in **Manual**? In **Accept edits**? In
   **Auto**? Write your three numbers down.
4. Run it in **Manual** and count the prompts. Then reset the copy, switch to **Accept edits**,
   and run it again. Then **Auto**. (If Auto isn't in the mode selector, your plan or organisation
   hasn't enabled it; do the first two.)
5. Still in Auto, ask: *"Now push this to a new branch on GitHub."* **Predict** first: will it
   ask? With no rules yet, that depends on a background check, not on you. In the next node you add
   an ask rule for `git push`, and from then on it stops for you even in Auto. That is a ceiling:
   publishing stays at proposing, permanently.
6. In Manual mode, find a command you've approved several times without changing anything. Choose
   **Yes, and don't ask again**. You've just promoted one action from proposing to automated, on
   the evidence of how often you changed nothing.

## Proof

Your three predicted and three actual prompt counts, and the one action that still asked in Auto.

## Misconceptions this exposes

- *"Auto mode means I've stopped checking."* You've stopped checking the routine. The actions
  you've marked as ask still stop for you, every time.
- *"Trust is a setting for the whole session."* It's per action. The same session can commit
  freely and still ask before every push.
- *"Promotion only goes up."* If an allowed action lets a mistake through, move it back to ask.
  Down is a normal move.
