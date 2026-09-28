# Boss

The boss battle card, served by GitHub Pages from `index.html`.

It reads its state from the Quest Engine (Cloudflare Worker, `rdecaste/quest-engine`) at `GET /boss` and sends taps, reverts and claims to `POST /attack`, `/revert` and `/claim`. `data.json` here is the last file Make published (27 Sep 2026) and is no longer updated. The card still mirrors a few rules for display (battlefield hash, streak chips, heal cap); the rules themselves live in the Worker. How it works: Notion page "⚙️ Quest Engine (Cloudflare Worker)" under Quest log.
