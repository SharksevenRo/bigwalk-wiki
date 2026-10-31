# Big Walk Wiki — bigwalk.anydaykit.com

The community wiki for **Big Walk**, the 2–12 player co-op walking-and-talking puzzle game, built with the open-source [AnvilWiki](https://github.com/PNGTRID/AnvilWiki) template (Astro 7 + Cloudflare Pages).

**Live site:** [bigwalk.anydaykit.com](https://bigwalk.anydaykit.com/) (mirror: [bigwalk-wiki-7ln.pages.dev](https://bigwalk-wiki-7ln.pages.dev/))

## What's Here

- **Guides** — beginner's guide, puzzle families, all 7 purple challenges, both endings, achievements, proximity voice chat
- **Items** — every tool and toy: radio, flashlight, laser pointer, binoculars, megaphone, whiteboard, backpack
- **Maps** — the island, towers, cable cars, and how navigation works without a HUD

Content follows the AnvilWiki content format: every page carries a verified date, a direct-answer summary, and honest sourcing — unconfirmed details are marked for community verification instead of stated as fact. Pages reference game version **1.4.8** (the October 2026 voice-chat patch).

## Run Locally

```bash
npx -y pnpm@11.1.1 install
npx -y pnpm@11.1.1 dev        # http://localhost:4321
npx -y pnpm@11.1.1 build      # static output in dist/
npx -y pnpm@11.1.1 check-content
```

## Deploy

```bash
# Build with production origin + deploy marker, then deploy to Cloudflare Pages.
SITE_URL=https://bigwalk.anydaykit.com CF_PAGES_COMMIT_SHA=$(git rev-parse HEAD) \
  npx -y pnpm@11.1.1 build
npx -y wrangler@4 pages deploy dist --project-name=bigwalk-wiki --branch=main
```

After every push to `main`, CI runs the content gates and then a GitHub Actions
workflow (`.github/workflows/indexnow.yml`) verifies this exact commit is live
and submits the sitemap to IndexNow automatically.

## License

MIT (site content) — template code © the AnvilWiki authors, also MIT.
