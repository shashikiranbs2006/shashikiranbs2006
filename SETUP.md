# Setup — finishing this off

I generated the README, the skill/language radars, and the four project cards for real,
against your actual GitHub repos (`shashikiranbs2006`). Three things still need you:

## 1. Add your photo (optional)
Upload a photo and I'll run:
```
python scripts/dotify.py assets/photo.png -o assets/portrait --cols 100 --equalize --detail 0.5 --color
```
That writes `assets/portrait.svg` and I'll drop the `<img>` back into the top of README.md.

## 2. Push this as your profile repo
This has to live in a repo named **exactly** `shashikiranbs2006/shashikiranbs2006`, and it
must be **public** (the SVGs are loaded by relative path, so a private repo shows broken images).

```bash
git init && git branch -M main
git add -A && git commit -m "profile readme"
git remote add origin https://github.com/shashikiranbs2006/shashikiranbs2006.git
git push -u origin main
```

## 3. (Optional) turn on the live-updating widgets
The stat cards you have right now are a snapshot from today. If you want them — and the
3D contribution calendar / contribution snake, which I can't generate locally — to auto-refresh:

- Repo → **Settings → Actions → General → Workflow permissions** → set to **Read and write**
- Generate a classic token at https://github.com/settings/tokens with the `read:user` scope,
  then add it as a repo secret named **`METRICS_TOKEN`**
  (Settings → Secrets and variables → Actions → New repository secret)
- Repo → **Actions** tab → run "Metrics", "Charts and cards", and "Snake" once each manually

Without step 3 the README still works fine — the cards just won't auto-refresh, and the
isometric calendar/snake sections (which I removed since I can't generate those locally)
would need to be added back in once those workflows have run.

## Editing things later
- **Skill radar numbers** — `assets/skills.json` (edit values, then `python scripts/radar.py --data assets/skills.json -o assets/radar`)
- **Featured projects** — `assets/projects.json` (then `python scripts/cards.py --user shashikiranbs2006 --out assets`)
