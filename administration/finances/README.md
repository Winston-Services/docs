---
description: Revenue distribution from TradeTower swap fees.
---

# Finances

All revenue comes from the 3% fee on every TradeTower swap. Periodically, 10% of treasury LP tokens are extracted and split across eight groups.

## Gross Revenue Split

### Group 1 — Winston Academy (20%)

Funds the learn-to-earn WAC credit system. Auto-sweeps to the treasury, which backs WAC redemptions.

### Group 2 — Management, Development, Marketing (28% combined)

* Management (8.4%) — Project leadership and operations
* Development (16.8%) — Engineering, bug fixes, features
* Marketing (2.8%) — Community outreach and partnerships

Outflow: Governance disbursement proposals (AHWA holders vote on recipients).

### Group 3 — Member Rewards (26%)

Distributed to asset holders proportionally based on 30-day rolling average balances. Hold any non-LP token, earn rewards automatically.

### Group 4 — Asset Management, Revenue Generation, Liquidity (26% combined)

* Asset Management (11.7%) — Strategic operations, governed by disbursement proposals
* Revenue Generation (7.8%) — Pays eligible node operators based on uptime and integrity scores
* Liquidity (6.5%) — Auto-recycles into LP pools, creating a compounding fee loop

## Distribution Frequency

Distribution adapts to trading volume:

* Low volume: up to 24 hours between cycles
* Normal volume: every 1–4 hours
* High volume: hourly or more

## Transparency

All distributions are recorded in LevelDB and auditable. No central treasury extraction — funds flow through automation and community governance (AHWA votes).

See the [Revenue Model](../revenue-model.md) page for the full breakdown with examples.
