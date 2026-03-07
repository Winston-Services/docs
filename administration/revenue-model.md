# Revenue Model

TradeTower has no external funding, no venture capital, and no initial coin offering. All revenue comes from trading activity within the DEX itself. This is a sustainable, community-driven economic model.

## The Source: Swap Fees

Every trade on TradeTower incurs a 3% fee, paid in the token being sold. These fees accumulate in the liquidity pools' reserves, benefiting liquidity providers.

But TradeTower also skims a portion of those accumulated fees for platform operations and community benefits. This happens periodically through the `distribute` command, which extracts 10% of the treasury's liquidity provider tokens and splits them across eight groups.

## The Eight Revenue Groups

Each group has a specific purpose, allocation, and outflow mechanism:

### Group 1: Winston Academy (20%)

Funds the learn-to-earn WAC credit system. Users earn WAC by taking quizzes, learning blockchain basics, and completing educational milestones. WAC can be redeemed for real value through the treasury. This is the community education fund.

**Outflow:** Automatic sweep to the treasury (which backs redemptions)

### Groups 2A–2C: Management, Development, Marketing (27.4% combined)

Project oversight, platform development, and community growth are funded by governance. These groups receive:

* Management (8.4%) — Project leadership, roadmap, operations
* Development (16.8%) — Engineering, bug fixes, feature development
* Marketing (2.8%) — Community outreach, partnerships, events

**Outflow:** Governance disbursement proposals (AHWA token holders vote on distribution to recipients)

### Group 3: Member Rewards (26%)

The largest group — distributed to users who hold TradeTower assets. Every 30 days, user holdings are averaged (weighted by days held), and rewards are distributed proportionally. Hold any non-LP token, earn rewards.

**Outflow:** Automatic daily, proportional to 30-day rolling average balance

### Group 4: Asset Management (11.7%)

Strategic token purchases, market-making, and ecosystem development are governed separately.

**Outflow:** Governance disbursement proposal to provider address

### Group 4: Revenue Generation (7.8%)

Funds for node operators — eligible nodes that maintain uptime and participate in state commitment earn payouts from this pool. A well-run node can generate meaningful income.

**Outflow:** Automatic payout based on node scorecard (uptime, code integrity, epoch participation)

### Group 4: Liquidity (6.5%)

The compounding loop. These funds are automatically re-invested back into liquidity pools, creating LP tokens that earn fees again. This creates a self-sustaining cycle: fees create liquidity, liquidity earns more fees, those fees generate more liquidity.

**Outflow:** Automatic daily, directly into LP pools (no human action needed)

## The Economic Cycle

{% stepper %}
{% step %}
### 1) User swap and fee collection

User swaps 1000 USDT for ETH. Pool charges 3% = 30 USDT fee.
{% endstep %}

{% step %}
### 2) Fee accrual

Fee accrues to the liquidity pool, increasing its reserves.
{% endstep %}

{% step %}
### 3) Periodic distribution

Periodically (typically daily or every few hours based on volume), the `distribute` command runs.
{% endstep %}

{% step %}
### 4) Treasury extraction

10% of treasury LP tokens are removed, generating the 8 groups' allocations.
{% endstep %}

{% step %}
### 5) Liquidity reinvestment

Group 4 Liquidity tokens are immediately re-deposited into LP pools.
{% endstep %}

{% step %}
### 6) Larger pools

More LP tokens = larger pools = more fee capture.
{% endstep %}

{% step %}
### 7) Compounding effect

This creates a compounding effect: fees → liquidity → more fees.
{% endstep %}
{% endstepper %}

Meanwhile:

* Group 1 funds learn-to-earn credits
* Groups 2 fund development and marketing via governance voting
* Group 3 rewards community members for holding
* Group 4 Revenue Gen pays node operators for securing the network
* Group 4 Asset Management handles strategic operations

All flows are transparent, on-chain, and governed by the AHWA token (one AHWA = one vote on disbursements).

## Adaptive Distribution Frequency

The `distribute` command doesn't run on a fixed schedule. Instead, it adapts to trading volume:

* **Low volume** (< 100 swaps/hour): waits up to 24 hours
* **Normal volume** (100–1000 swaps/hour): runs every 1–4 hours
* **High volume** (> 1000 swaps/hour): runs hourly or more frequently

This ensures the system doesn't over-commit governance resources during quiet periods, but remains responsive during trading booms.

## No Central Treasury Extraction

Unlike traditional platforms (which take a large percentage for founders), TradeTower has no central treasury. All funds flow through:

1. **Governance** — Community votes on disbursements (groups 2A–2C, 4A)
2. **Automation** — Learn-to-earn sweep, member rewards, node payouts, liquidity recycling

A founder or team cannot unilaterally withdraw funds. All money flows to the community, development, or back into liquidity.

## Self-Sustainability

The model is designed to self-sustain indefinitely:

* Transaction volume → fees → liquidity → more transactions
* Education → engaged users → more trading
* Node rewards → network security → user confidence → more trading
* Member rewards → user retention → consistent volume

No external capital is required. The platform grows organically from its own fee revenue.

## Examples

### Scenario 1: Small Community DEX

* Daily volume: 10,000 USDT
* Daily fees: 300 USDT
* Annual fees: \~109,500 USDT
* Annual group distributions:
  * Academy: 21,900 USDT
  * Development: 29,448 USDT
  * Member Rewards: 28,470 USDT
  * Liquidity (reinvested): 7,119 USDT
  * Node payouts: 8,541 USDT

### Scenario 2: Active Community DEX

* Daily volume: 100,000 USDT
* Daily fees: 3,000 USDT
* Annual fees: \~1,095,000 USDT
* Annual group distributions:
  * Academy: 219,000 USDT
  * Development: 294,480 USDT
  * Member Rewards: 284,700 USDT
  * Liquidity (reinvested): 71,190 USDT
  * Node payouts: 85,410 USDT

## Governance

AHWA token holders collectively decide:

* How development funds are spent
* Which providers receive asset management payouts
* The distribution amounts (via governance proposals)
* Epoch commitment frequency and other protocol parameters

One AHWA = one vote. Voting is via signed blockchain messages (verified on BSC) to prevent vote manipulation.

## Looking Forward

The revenue model is flexible. Via governance, the community can:

* Adjust group allocations
* Add new groups (e.g., insurance, liquidity mining bonuses)
* Change the core 3% fee (if the AHWA community votes)
* Direct funds to new initiatives (education, partnerships, etc.)

All without changing code. Just governance.
