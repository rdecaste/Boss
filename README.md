# Boss

The boss battle card, at https://boss.quest-engine.workers.dev (Cloudflare,
behind Roy's Cloudflare Access login), from `index.html`.

It reads its state from the Quest Engine (Cloudflare Worker,
`rdecaste/quest-engine`) at `GET /boss` and sends taps, reverts and claims to
`POST /attack`, `/revert` and `/claim` (card passcode). The card still mirrors
a few rules for display (battlefield hash, streak chips, heal cap); the rules
themselves live in the Worker. How it works: `docs/quest-engine.md` in
rdecaste/quest-engine. The data (fights, events, habits, the hero) is in the
Quest Engine's D1 database; habits are edited in D1 Data Studio.

A push to `main` deploys it to Cloudflare (Workers Builds); by hand: `npx wrangler deploy`. Only the pages are published (`.assetsignore`). The old `rdecaste.github.io` address forwards here until GitHub Pages is switched off.
