---
description: >-
  WAC is the learn-to-earn token. Earned through quiz participation, maintaining
  streaks, accuracy milestones, and /ask engagement. Redeem for value at
  TradeTower AMM rates.
---

# Winston Academy Coin Utility

## What Is WAC?

Winston Academy Coin (WAC) is the learn-to-earn token of the Winston ecosystem. It rewards users for educational engagement and quiz participation on TradeTower, converting blockchain knowledge into redeemable value.

## How to Earn WAC

WAC credits are earned through several activities:

- **Quiz Participation** — Each `/quiz` attempt awards points based on correct answers
- **Streak Bonuses** — Maintain consecutive correct answers for a 1.5x multiplier on points
- **Accuracy Milestones** — Higher overall accuracy rates unlock bonus credit awards
- **/ask Engagement** — Using the `/ask` command for blockchain questions contributes to your learning score

All credits accumulate in your TradeTower account balance and are visible via the `/balance` command.

## Redeeming WAC

Convert your WAC credits to tradeable value using `/redeem`:

```
/redeem <amount>
```

Redemption converts your credits to RKL (or other tokens) at current TradeTower AMM rates. The treasury must have sufficient balance to process the redemption.

**Minimum Redemption:** 1,000,000 credits (1M credits = 1 WAC unit)

## Academy Funding

The Winston Academy treasury grows automatically from platform revenue:

- **20% of ALL swap fees** flow directly into the academy treasury
- **More trading volume** = larger academy treasury = higher WAC value at redemption
- The treasury is self-sustaining and grows with the platform

## Contract Details

**BSC Contract Address:** `0xc01e8687eE397106aCDd52BbCc9f2E1E0cEe2aC1`

WAC is managed internally on TradeTower's ledger and bridges to BSC for external integrations.

## The Economic Loop

1. Users trade on TradeTower (generating 3% swap fees)
2. 20% of fees fund the Academy treasury (growing WAC value)
3. Users earn WAC through quiz participation
4. Users redeem WAC to realize value
5. Platform growth increases treasury balance, benefiting all current and future learners
