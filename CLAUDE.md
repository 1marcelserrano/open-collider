# CLAUDE.md — open-collider

## What this repo is

A single Claude skill distributed as a public GitHub repo. The single source
of truth is `skills/open-collider/SKILL.md`. Every behavioral change starts there.

The skill implements the Open Collider protocol (CL-ML, 2026) + Koestler's
bisociation — a controlled-collision ideation engine. The repo is a vitrine:
the README is a landing page, not just docs.

## What to edit

| File | What it controls |
|------|------------------|
| `skills/open-collider/SKILL.md` | Skill behavior — triggers, protocol, output format. The body the agent loads. English, canonical. |
| `skills/open-collider/SKILL.pt-BR.md` | Portuguese translation. Mirror behavioral changes here after SKILL.md stabilizes. |
| `skills/open-collider/README.md` | Per-skill human-facing summary. |
| `README.md` (root) | Product front door. Optimize for an open-ended-ideation reader. The proof line + Mermaid flow carry the pitch. |
| `examples/` | Worked runs. Keep named references intact — they're the mechanism, not decoration. |
| `templates/brief-template.md` | The Stage 1 briefing seed. |
| `assets/social-preview.html` | DS V3.0 source for the GitHub social card. |

## What NOT to edit

- Don't edit the canonical skill in the private `mscs-skills` monorepo from here — this repo is a published mirror. Behavioral changes flow through `skills-sync`.
- Keep the SKILL.md frontmatter (`name`, `description`) intact — `npx skills` and the Claude plugin loader both parse it.
- Don't fabricate benchmark numbers. The empirical proof comes from the cited paper.
- Never commit `.env`, tokens, or credentials.

## Conventions

- Idioma: README/skill em EN; voz direta, frases curtas, zero floreio. Sem léxico inflado, sem paralelismo negativo.
- Commits: Conventional Commits. Push só com SHA verificado (local = remote).
- `open-collider.skill` na raiz: empacotado via `skills-sync`, não editar à mão.

## License

MIT. Contributions welcome. See CONTRIBUTING.md.
