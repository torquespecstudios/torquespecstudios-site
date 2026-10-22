# Torque Spec Studios website

This repo is the public website (GitHub Pages). It also holds the public beta copy of each game.
Each game also has its own **private** backup repo on GitHub.

## Rule: every game change goes to the game's own repo too

Whenever you change a game, commit and push the change to **both** places:

1. **The game's private repo** (its own backup and full history), and
2. **this site repo**, if the game has a public beta page here.

Never put one game's files into another game's repo.

| Game | Private repo | Beta copy in this site repo |
| --- | --- | --- |
| Swervy | `torquespecstudios/swervy` (game file `hairpin.html`) | `play/index.html` (beta), `swervy/` (game page) |
| Swoopy Wings | `torquespecstudios/swoopy` (game file `swoopy.html`) | `swoopy-beta/`, built with that repo's `web/build_beta.py` |
| Tuggy | `torquespecstudios/tuggy` | `tug/index.html` |
| Scoopy | `torquespecstudios/scoopy` | `scoopy-beta/` |

Notes:
- **Tuggy:** the private repo's `index.html` is the same file as `tug/index.html` here. Copy it across unchanged and use the same commit message (e.g. "Tuggy beta v36").
- **Scoopy:** the private repo holds the full project (`index.html`, README, icons, Capacitor files). `scoopy-beta/index.html` here is the same game with beta-only `<head>` tags added (noindex, Open Graph, manifest) and the offline `lib/three.min.js` fallback line removed. Make game changes in the private repo first, then copy them into `scoopy-beta/index.html`, keeping those head differences. Bump the version label in Settings ("Scoopy beta vN") in both.
- **Swervy:** `play/index.html` is the private repo's `hairpin.html` with beta-only `<head>` tags added; keep those when copying.
- **Swoopy:** rebuild `swoopy-beta/` from the private repo with `python3 web/build_beta.py <this repo>/swoopy-beta`.
- Each private repo also has its own `CLAUDE.md` with the same rule.
- If you can't push to a game's private repo (for example a cloud session without access to it), say so plainly to the user. Don't skip it silently, and don't push it to a different repo instead.
- Commit messages follow the existing style: "<Game> beta vN: what changed".

## Visit counting (GoatCounter)

Every page on this site has this line just before `</head>`:

```html
<script data-goatcounter="https://torquespecstudios.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>
```

It is a website-only addition. When you copy or rebuild a game's beta page from its private repo (Tuggy, Swervy, Swoopy, Scoopy), put this line back if the copy removed it. Any new page added to the site gets it too. Stats: torquespecstudios.goatcounter.com
