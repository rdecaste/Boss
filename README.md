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

**💬 Trash talk** (front of the card, since 8 Oct 2026): a speech bubble under the boss's name. The boss on the card taunts you about the fight as it stands (its HP, your hits today, your own bad habits, its 04:00 strike, the rage meter, the battlefield, the Dragon Balls, today's win, the hour), and Goku's allies chime in. A new line comes every 40 s, when you flip back to the front or when you tap the bubble; after attacking, the front shows the reaction to your last tap (hit, crit, heal, a bad habit, a Dragon Ball). Allies follow the story: each speaks only once the hero's level reaches the part of the story they join. Only the boss on the card speaks as a villain; no line names another boss (`commsLines()` in `index.html`; own lines for bosses already met in `BOSS_VOICE`).
