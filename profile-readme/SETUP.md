# How to install this profile README

This folder holds a ready-to-use **GitHub profile README** for `Swaroop192005`.
GitHub renders a special repo — one named exactly after your username — on your profile page.

That repo already exists: **https://github.com/Swaroop192005/Swaroop192005**
(it currently holds the older README). These files replace it.

## What's in here

| File | Goes to | Purpose |
|---|---|---|
| `README.md` | `Swaroop192005/Swaroop192005` → `README.md` | the profile page itself |
| `.github/workflows/snake.yml` | `Swaroop192005/Swaroop192005` → `.github/workflows/snake.yml` | generates the contribution-snake animation |

## Option A — GitHub web UI (no terminal)

1. Open https://github.com/Swaroop192005/Swaroop192005/edit/main/README.md
2. Select all, paste the contents of `README.md` from this folder, commit.
3. Go to **Add file → Create new file**, name it `.github/workflows/snake.yml`,
   paste the contents of `snake.yml`, commit.
4. Open the **Actions** tab → *Generate contribution snake* → **Run workflow**.
   The first run creates the `output` branch holding the snake SVGs.

## Option B — git

```bash
git clone https://github.com/Swaroop192005/Swaroop192005
cd Swaroop192005

# from a checkout of the portfolio repo:
cp /path/to/portfolio/profile-readme/README.md .
mkdir -p .github/workflows
cp /path/to/portfolio/profile-readme/.github/workflows/snake.yml .github/workflows/

git add -A
git commit -m "Refresh profile README"
git push origin main
```

Then trigger the workflow once from the **Actions** tab.

## What makes it interactive

| Element | How it works | Needs setup? |
|---|---|---|
| **Collapsible sections** (`<details>`) | Native GitHub markdown — every study and project expands on click | no |
| **Animated typing header** | `readme-typing-svg.demolab.com` renders an animated SVG | no |
| **Light/dark adaptive cards** | `<picture>` + `prefers-color-scheme`, so stats match the viewer's GitHub theme | no |
| **Live GitHub stats / top languages / streak** | `github-readme-stats` + `github-readme-streak-stats`, re-rendered on every page load | no |
| **Profile view counter** | `komarev.com/ghpvc` | no |
| **Contribution snake** | the GitHub Action above, committed to the `output` branch | **yes** — run the workflow once |
| **Tech badges** | `shields.io` | no |

GitHub strips `<script>` and CSS from READMEs, so genuine interactivity comes from
`<details>` toggles, links, and server-rendered SVGs that respond to theme and live data.
Everything here works within those limits — no JavaScript required.

## Notes

- **Streak stats** (`herokuapp.com`) is the least reliable of the third-party services.
  If it ever stops rendering, delete that one `<picture>` block — nothing else depends on it.
- The snake `<picture>` shows a broken image until the workflow has run once and
  created the `output` branch.
- The RAG study links to `Robustness-Evaluation-of-Retrieval-Augmented-Generation-RAG-Systems-under-Noisy-Context`,
  taken from your portfolio page. That repo wasn't visible in this session's repo list —
  if it's private or renamed, update the link in `README.md`.
- To avoid depending on external services entirely, replace the typing header with a plain
  heading and drop the stats cards; the `<details>` structure still carries the page.
