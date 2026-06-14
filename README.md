> [!WARNING]
> **Early prototype.** A personal experiment, shared rough — expect sharp edges and breaking changes.

# Squawk

A Claude skill that argues **against** your plan.

In aviation, a *squawk* is a logged defect on an aircraft. Pilots and mechanics squawk every fault they find, and nothing flies until the list is cleared. This skill does the same to a plan, app, feature, or decision: you point it at something, and it logs everything wrong with it.

Squawk is the inverse of a steelman. A steelman builds the strongest case *for* an idea. Squawk builds the strongest case *against* the thing you hand it — rigorously, fairly, but pointed at finding what breaks.

## Why

Most tools help you build. This one tries to kill what you've built, before reality does. Hand it a plan and it hands you back the holes — what won't work and why — so you can decide with your eyes open.

It is not a brainstorming partner and not a cheerleader. It will not tell you your idea is great. That's the point.

## How it behaves

- **It never infers.** It argues only against what you actually said — no invented market, no assumed scale, no guessed budget. Attack a plan it imagined instead of yours, and the critique is worthless.
- **It opens with one question:** *"What's the claim you want me to argue against?"* Your answer is the target, and it sets the angle — "is this the safest auth choice" aims it at safety; "will this scale to millions" aims it at the economics.
- **Gaps are holes.** If your plan leaves something material unstated, it names the omission as the vulnerability rather than guessing what fills it or interrogating you for it.
- **No verdict unless you ask.** It builds the case against and stops. You render the judgment — unless you explicitly ask "should I do this?", in which case it'll answer.
- **A filled hole is settled.** Close a hole — by answering it *or* by saying "don't care, here's why" — and it drops it and moves on. It won't relitigate a risk you've knowingly accepted.
- **It calibrates to your stakes.** A throwaway prototype gets proportionate critique; a bet-the-company plan gets the full teardown. It never guesses the stakes — your framing sets them.

## Install

Copy the skill into your Claude skills directory:

```
~/.claude/skills/squawk/SKILL.md
```

On Windows that's `C:\Users\<you>\.claude\skills\squawk\SKILL.md`.

Then invoke it with `/squawk`, or just ask Claude to "argue against" / "poke holes in" / "tear apart" a plan and it'll reach for it.

## Usage

```
/squawk
```

Then describe what you want attacked. Or hand it the target up front:

```
/squawk my plan to build a paid social network for 12 friends
```

## Design

See [PRD.md](PRD.md) for the full behavior spec and the reasoning behind each rule.

## License

MIT — see [LICENSE](LICENSE). Open source: fork it, rename it, bend it to your own workflow.
