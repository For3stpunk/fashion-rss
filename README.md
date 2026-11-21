# Front Row: Fashion RSS

A GitHub Pages site that pulls every fashion feed in the directory into one reader and republishes them as combined RSS feeds. A GitHub Action fetches all ~885 source feeds every three hours.

**What's here**
- `sources.json`: 2,363 sources (885 with native RSS/Atom feeds, plus Instagram handles)
- `scripts/build.py`: fetches every feed and writes the site
- `site/`: the published page, `feeds/*.xml` combined feeds, `fashion-feeds.opml`, `directory.csv`

**Combined feeds** (under `https://<user>.github.io/<repo>/feeds/`): `all.xml`, `editions.xml`, `publications.xml`, `independent.xml`, `industry.xml`, `streetwear.xml`, `menswear.xml`, `blogs.xml`, `newsletters.xml`, `youtube.xml`, `instagram.xml`.

**Setup (once)**
1. Settings → Pages → Build and deployment → Source: **GitHub Actions**.
2. Actions tab → "Update feeds and publish" → **Run workflow**.

**Instagram (optional).** Instagram has no RSS. To include the ~1,480 Instagram accounts, run an [RSSHub](https://docs.rsshub.app/) instance with an Instagram login cookie and add a repository variable `RSSHUB_BASE` (Settings → Secrets and variables → Actions → Variables), e.g. `https://rsshub.example.com`.

**Edit sources.** Add or remove entries in `sources.json` (`feed` is the RSS URL). Pushing the change triggers a rebuild.
