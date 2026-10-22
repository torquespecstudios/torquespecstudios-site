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
| Swervy | `torquespecstudios/swervy` | `play/index.html` (beta), `swervy/` (game page) |
| Swoopy Wings | `torquespecstudios/swoopy` | `swoopy-beta/` |
| Tuggy | `torquespecstudios/tuggy` | `tug/index.html` |
| Scoopy | `torquespecstudios/scoopy` | `scoopy-beta/` |

Notes:
- **Tuggy:** the private repo's `index.html` is the same file as `tug/index.html` here. Copy it across unchanged and use the same commit message (e.g. "Tuggy beta v36").
- **Scoopy:** the private repo holds the full project (`index.html`, README, icons, Capacitor files). `scoopy-beta/index.html` here is the same game with beta-only `<head>` tags added (noindex, Open Graph, manifest) and the offline `lib/three.min.js` fallback line removed. Make game changes in the private repo first, then copy them into `scoopy-beta/index.html`, keeping those head differences. Bump the version label in Settings ("Scoopy beta vN") in both.
- **Swervy and Swoopy:** mirror each change into the private repo the same way.
- If you can't push to a game's private repo (for example a cloud session without access to it), say so plainly to the user. Don't skip it silently, and don't push it to a different repo instead.
- Commit messages follow the existing style: "<Game> beta vN: what changed".
