## Egg3901

I build large simulation games and the tooling that keeps them running. Most of my work is
one long project: **A House Divided**, a browser-based multiplayer political and economic
simulation where the world advances one turn per real hour and AI politicians fill every
seat a player does not. It is built by two of us.

Play it at [ahousedividedgame.com](https://www.ahousedividedgame.com). The rest of the
studio is at [lakesidegames.net](https://lakesidegames.net). Design and engineering
docs at [docs.lakesidegames.net](https://docs.lakesidegames.net).

### Games

| Project | What it is |
| --- | --- |
| [**AHDGame**](https://github.com/Egg3901/AHDGame) | A House Divided. Persistent political MMO. Elections across seven electoral systems, full bill lifecycles, corporations competing for market share, central banks with rate corridors, per-country currencies, and a double-entry ledger reconciling all of it every turn. 24 countries in the world economy, hourly turns, 120+ turn phases. |
| [**metroforge-native**](https://github.com/Egg3901/metroforge-native) | MetroForge. Alpha 3D transit builder in Rust and Bevy. Lay track through ten real American cities at real scale. A demand model estimates ridership stop by stop, so a line only works if it goes where people travel. Simulation is in-process Rust. |
| [**ahd-sim**](https://github.com/Egg3901/ahd-sim) | Electioneer. Turn-based campaign simulator. 34 historical elections across six countries. You get a budget, a staff, and eleven actions a week. Spend them well until election night. Play at [lakesidegames.net/games/electioneer](https://lakesidegames.net/games/electioneer/). |
| [**grand-century**](https://github.com/Egg3901/grand-century) | Grand Century. Single-player browser grand strategy in the spirit of Victoria 2: take a nation in 1836 through a century of industry, reform, and conquest, on a world whose population and markets move without you. |
| [**Rialto**](https://lakesidegames.net/games/rialto/) | Tidal city builder, free in the browser. Build a canal town in a lagoon. Low water exposes flats you can build on. High water floods anything built too low. Source is not public. |
| [**verdigris**](https://github.com/Egg3901/verdigris) | Verdigris. A living 1890s district. You never place a building. Named residents walk a day you can follow; you get a few interventions, and the ledger judges what the city actually did. Play at [lakesidegames.net/games/verdigris](https://lakesidegames.net/games/verdigris/). |
| [**Ink & Influence**](https://lakesidegames.net/games/ink-and-influence/) | Pixel-art media empire prototype. Run a local newspaper in 1895, then grow it across print, radio, television, and the internet. Source is not public. |

A House Divided, Grand Century, and Electioneer are source-available under
[PolyForm Noncommercial](https://polyformproject.org/licenses/noncommercial/1.0.0).
Read them, learn from them, run them yourself. Do not sell them.

### Supporting repos

| Project | What it is |
| --- | --- |
| [**AHDClient**](https://github.com/Egg3901/AHDClient) | Native A House Divided client. Desktop (Windows, macOS, Linux) opens live multiplayer and runs the whole game locally for singleplayer. Android and iOS open the live game in-app, with briefing widgets. |
| [**ahd-docs**](https://github.com/Egg3901/ahd-docs) | Public design and engineering documentation for A House Divided, published at [docs.lakesidegames.net](https://docs.lakesidegames.net). |
| [**metroforge**](https://github.com/Egg3901/metroforge) | Storefront and download page for MetroForge. |
| [**adhd-bot**](https://github.com/Egg3901/adhd-bot) | Discord companion for A House Divided: look up politicians, track elections, read in-game news. |

### Stack

**Applications.** TypeScript, Next.js App Router, React, Tailwind, MongoDB. AHDGame is
1,200+ API route handlers over 100+ document types, with the hourly turn processor running
as a separate cron workload. The smaller games are React and Vite over a pure TypeScript
engine with no DOM dependencies, which keeps them testable and runnable headless.

**Systems and clients.** Rust and Bevy for MetroForge. Tauri for the A House Divided
desktop client, with Android and iOS shells in the same repo. Rust again for internal
services where a long-running process beats a request handler.

**Testing.** Vitest for unit and integration, Playwright for end to end, plus simulation
harnesses that run whole game worlds forward hundreds of turns to check economic and
electoral balance before a change ships.

**Infrastructure.** Railway, Docker, Cloudflare R2, self-hosted error tracking, and a
promotion pipeline of development to staging to production.

### Currently

A House Divided is live. The native client is [AHDClient](https://github.com/Egg3901/AHDClient):
desktop multiplayer and local singleplayer, plus Android and iOS for the live game.
MetroForge is in alpha. Grand Century and Ink & Influence are still in development.
Verdigris and Rialto are playable in the browser.

### Older work

Anything here from 2021 or earlier is archived PHP and Discord bot work, kept for history.
It is not maintained and it is not representative.
