# Project presentation and publishing notes

Prepared on October 1, 2026 against `1f67a6b5272c9e51de7ca169ea8c18109faa62e3` on the current `main` branch. Public copy is in English. These notes distinguish proposed settings from published settings.

## Canonical identity

- Display name: **DEX Swap Tracker & Telegram Bot**.
- Repository: [Lukecele/Telegram-bsc-buy-sell-bot](https://github.com/Lukecele/Telegram-bsc-buy-sell-bot).
- npm package name: `telegram-bsc-buy-sell-bot` (local manifest identity; no npm publication claimed).
- Author: Luca Celebrano (@Lukecele), founder and sole member of arbincept, as supplied by the owner.
- Purpose: monitor pool-related token transfers and send Telegram alerts. No trade execution or wallet management.
- Entry points: `server.ts` for Express and workers; `src/main.tsx` for React; `dist/server.cjs` after building.
- Runtime services: DexScreener, public BSC/Ethereum RPCs, Telegram Bot API. Birdeye is a historical name, not a current runtime dependency. The GeckoTerminal script is an exploratory script, not the server's data source.

## Deployment and link audit

Read-only HTTP checks on October 1, 2026:

| Address | Observed result | Visitor use |
| --- | --- | --- |
| [Former GitHub slug](https://github.com/Lukecele/birdeye-dex-tracker) | Redirected to the current repository, HTTP 200. | Normalize links; the old slug is not broken. |
| [Vercel host previously in About](https://birdeye-dex-tracker.vercel.app) | Root HTTP 200, no redirect; deployed JavaScript contains admin configuration calls and start/stop UI. | Not verified as a public read-only demo. |
| [Cloud Run host previously in README](https://birdeye-telegram-bot-697887897331.europe-west2.run.app) | Root HTTP 200, no redirect; deployed JavaScript contains admin configuration calls and start/stop UI. | Not verified as a public read-only demo. |
| [@ArbincMoon_bot](https://t.me/ArbincMoon_bot) | HTTP 200; Telegram landing identifies Arb Inc Moon and the bot handle. | Proposed public homepage. Live responses/delivery untested. |
| [Community alert topic](https://t.me/arbitrageinception/80770) | HTTP 200; Telegram post landing. | Optional community link; post contents/access not verified. |

No production controls were invoked, no credentials were used, and no Telegram messages were sent. Root availability and bundle inspection do not establish backend health, access control, or continuous monitoring. There is no reproducible deployment configuration in this checkout. The screenshot is from a local instance, not either hosted service.

## Repository settings

**Status: prepared, not applied.** The available GitHub API access reports no admin, maintain, or push permission. Remote settings were left unchanged; the README and assets are repository changes pending publication.

| Setting | Exact proposed value | Remaining manual action |
| --- | --- | --- |
| About description | DEX swap monitoring and Telegram alerts with a React dashboard. Built by Luca Celebrano (@Lukecele). | On the repository home page, open the About gear, paste the description, and save. |
| Homepage / Website | `https://t.me/ArbincMoon_bot` | Replace the Vercel URL in the same About dialog and save. This aligns the homepage with the public README entry point. |
| Topics | See the replacement list below. | Replace the existing topics in About; save. |
| Social preview | `docs/assets/social-card.png` | Open repository Settings → General → Social preview → Edit → Upload an image, select the PNG, and save. |

Replacement topics (11):

```text
telegram-bot dex-tracker on-chain-analytics bnb-chain ethereum typescript react ethers dexscreener token-tracker express
```

Each topic maps to the current runtime or product. `liquidity-tracker` is omitted because the implementation tracks pool-related transfers rather than liquidity positions or reserve changes. `trading-bot`, `birdeye-api`, `solana`, `jupiter`, and `raydium` would overstate the current implementation; `docker` and `cloud-run` are omitted because there is no deployment configuration to reproduce those claims.

The replacement list respects [GitHub's topic rules](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/classifying-your-repository-with-topics): at most 20 topics, each at most 50 characters, using lowercase letters, numbers, and hyphens. The [social preview guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview) recommends 1280×640 and a file under 1 MB. A README banner does not configure that setting.

## Assets and provenance

- [Social card SVG](assets/social-card.svg): editable original artwork, using the dashboard's zinc and blue palette and a simple activity trace; no external images, logos, or fonts are bundled.
- [Social card PNG](assets/social-card.png): opaque 1280×640 export, under 1 MB; intended for GitHub Social preview and sharing.
- [Dashboard screenshot](assets/dashboard-local.png): actual locally running React UI, in English, with an empty Telegram token, monitoring stopped, zero chats, and no trades. No fixtures representing live activity were inserted.

To reproduce the screenshot, follow the README quick start with the empty token, select English in the local UI, and capture at 1440×1080. To reproduce the card, open the SVG at its native 1280×640 size in a browser and export/capture a PNG without browser chrome. Both assets have opaque backgrounds and work within light and dark Markdown themes.

## Technical introduction

DEX Swap Tracker & Telegram Bot is an open-source monitoring tool by Luca Celebrano (@Lukecele). A Node.js and Express worker uses ethers to poll BNB Smart Chain or Ethereum token-transfer logs, matches transfers against pools discovered through DexScreener, and sends estimated buy/sell activity to Telegram. A React, Vite, and Tailwind administration dashboard exposes worker status, token settings, language selection, and recent events. State is stored in local JSON files. The tool monitors activity without executing trades or managing wallets.

## Short post draft

> I built DEX Swap Tracker & Telegram Bot to follow DEX activity through Telegram alerts and a React administration dashboard. It combines public EVM RPCs, DexScreener, Node.js, and TypeScript, with English and Italian notifications. It monitors activity without executing trades.
>
> Explore the source and local quick start: https://github.com/Lukecele/Telegram-bsc-buy-sell-bot
>
> Open the bot: https://t.me/ArbincMoon_bot
>
> If useful, star the repository and follow @Lukecele for more projects.

Draft only: no social post or external message has been published.
