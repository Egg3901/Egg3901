## Egg3901

I build large simulation games and the tooling that keeps them running. Most of my work is
one long project: **A House Divided**, a browser-based multiplayer political and economic
simulation where the world advances one turn per real hour and AI politicians fill every
seat a player does not. It is built by two of us.

Play it at [ahousedividedgame.com](https://www.ahousedividedgame.com). Design and
engineering docs at [docs.lakesidegames.net](https://docs.lakesidegames.net).

### Games

| Project | What it is |
| --- | --- |
| [**AHDGame**](https://github.com/Egg3901/AHDGame) | A House Divided. Elections across seven electoral systems, full bill lifecycles, corporations competing for market share, central banks with rate corridors, per-country currencies, and a double-entry ledger reconciling all of it every turn. 24 countries, hourly turns, 120+ turn phases. |
| [**grand-century**](https://github.com/Egg3901/grand-century) | Grand Century. Single-player browser grand strategy in the spirit of Victoria 2: take a nation in 1836 and carry it through a century of industry, reform, and conquest, on a world whose population and markets move without you. |
| [**ahd-sim**](https://github.com/Egg3901/ahd-sim) | Electioneer. Turn-based election campaign simulator. 20 historical elections across six countries, 1974 to 2027. Read the map, allocate finite resources each week, rewrite the result. |
| [**metroforge-native**](https://github.com/Egg3901/metroforge-native) | MetroForge desktop client. A single-player transit network builder in Rust and Bevy: place stations, draw track, run routes, balance a budget, and watch the city grow around the network. Deterministic TypeScript sim sidecar. |

A House Divided, Grand Century, and Electioneer are source-available under
[PolyForm Noncommercial](https://polyformproject.org/licenses/noncommercial/1.0.0).
Read them, learn from them, run them yourself. Do not sell them.

### Supporting repos

| Project | What it is |
| --- | --- |
| [**ahd-docs**](https://github.com/Egg3901/ahd-docs) | The public design and engineering documentation site for A House Divided. |
| [**ahd-client**](https://github.com/Egg3901/ahd-client) | Electron desktop client for A House Divided. Windows, macOS, and Linux. |
| [**discord-agent**](https://github.com/Egg3901/discord-agent) | Discord bot that runs threaded coding sessions against the Anthropic API, with multi-key pooling, health tracking, automatic failover, and per-user rate limits. |
| [**metroforge**](https://github.com/Egg3901/metroforge) | Storefront and download page for MetroForge. |

### Stack

**Applications.** TypeScript, Next.js App Router, React, Tailwind, MongoDB. AHDGame is
400+ API route handlers over 100+ document types, with the hourly turn processor running
as a separate cron workload. The smaller games are React and Vite over a pure TypeScript
engine with no DOM dependencies, which keeps them testable and runnable headless.

**Systems and clients.** Rust, for the MetroForge native client and for internal services
where a long-running process beats a request handler.

**Testing.** Vitest for unit and integration, Playwright for end to end, plus simulation
harnesses that run whole game worlds forward hundreds of turns to check economic and
electoral balance before a change ships.

**Infrastructure.** Railway, Docker, Cloudflare R2, self-hosted error tracking, and a
promotion pipeline of development to staging to production.

### Currently

Working through A House Divided 1.2: supply and trade dislocation, corporate financials on
a realized basis, and central bank behaviour. Most of the open work is economic
calibration rather than new surface area, which means measuring the live world first and
changing constants second.

MetroForge is moving from 0.6 toward 1.0 on the native client.

### Older work

Anything here from 2021 or earlier is archived PHP and Discord bot work, kept for history.
It is not maintained and it is not representative.
