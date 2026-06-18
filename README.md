# business-people-coding

Portfolio of the apps built by non-developers during the **"Faire une petite appli
avec une IA, sans coder"** workshop. Served as a static site on GitHub Pages.

**Live:** https://martinsson.github.io/business-people-coding/

## Layout

```
index.html              landing page linking every project
<session-date>/<entry>/  one folder per group/project, = that snapshot's site/
```

| Session | Source | Entries |
| ------- | ------ | ------- |
| `2026-06-16/` | `session-2026-06-16` tag on each group repo | group1–group5 |
| `2026-06-10/` | `solution/2026-06-10` branch on each group repo | group1–group5 |
| `2026-05-06/` | `recovered/*` tags (versions rescued from old resets) | absences, timer, inscriptions |

Every app is self-contained static HTML/CSS/JS with relative paths, so it runs as-is
under its subfolder. No build step.

## Adding a new session

Each app is just the `site/` directory from a preserved ref. To add a session:

```bash
# from the kata repo, for a given ref (tag/branch) and destination:
git archive <ref> site | tar -x --strip-components=1 -C <session-date>/<entry>
```

Then add a card to `index.html` and push. The original code stays in the group repos
under its session tag — this repo is the published showcase, decoupled from any resets.
