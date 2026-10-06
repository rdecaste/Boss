# Boss

The boss battle card, at https://boss.quest-engine.workers.dev (Cloudflare,
behind Roy's Cloudflare Access login), from `index.html`.

It reads its state from the Quest Engine (Cloudflare Worker,
`rdecaste/quest-engine`) at `GET /boss` and sends taps, reverts and claims to
`POST /attack`, `/revert` and `/claim` (card passcode). The card still mirrors
a few rules for display (battlefield hash, streak chips, heal cap); the rules
themselves live in the Worker. The red "The boss's turn" box under today's win shows `boss_ai` from `/boss`: the coming 04:00 hit and what today blocked, the neglect strikes waiting, and the rage meter (the card adds the waking hours since `rage.since` itself). When a wish is granted, Shenron's clip (`shenron` from `/boss`, made once by the Quest Engine's ShenronVisual Workflow; a glowing 🐉 until it exists) plays with what the wish did, and the Loot tab shows the last wish and a wish log (`dragon_log`). How it works: `docs/quest-engine.md` in
rdecaste/quest-engine. The data (fights, events, habits, the hero) is in the
Quest Engine's D1 database; habits are edited in D1 Data Studio.

A push to `main` deploys it to Cloudflare (Workers Builds); by hand: `npx wrangler deploy`. Only the pages are published (`.assetsignore`). The old `rdecaste.github.io` address forwards here until GitHub Pages is switched off.
