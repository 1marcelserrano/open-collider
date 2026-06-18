# Contributing to open-collider

Thanks for considering a contribution.

## What to edit

Single source of truth: `skills/open-collider/SKILL.md`. All behavior changes
go there first. The root `README.md` is the product front door and updates
after the skill body stabilizes. Mirror behavioral changes into
`skills/open-collider/SKILL.pt-BR.md` once the English body has settled.

## How to test locally

1. Clone the repo.
2. Copy `skills/open-collider/` into your Claude skills directory:
   - macOS/Linux: `~/.claude/skills/`
3. Restart Claude or open a new chat.
4. Trigger the skill with one of the phrases from the README and run it on a real brief.

## PR guidelines

- **Conventional Commits.** `feat:`, `fix:`, `docs:`, `refactor:`.
- **One concern per PR.** A docs fix and a behavior change go separately.
- **Show before/after** for any SKILL.md body change. One sentence on why the new wording is better.
- **Keep the install commands accurate.** A broken install costs real users.
- **New examples are welcome** — a worked run on a fresh brief, with named references and the falsifier checks, is the most useful contribution.

## A note on the protocol

The protocol itself comes from the research credited in the README (CL-ML,
Koestler). Improvements to *how the skill applies it* are in scope here;
changes to the underlying theory belong upstream.

## License

By contributing you agree your contributions are licensed under MIT.
