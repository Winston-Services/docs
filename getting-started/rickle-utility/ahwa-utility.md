# AHWA Governance Token

AHWA is Winston's governance token on Binance Smart Chain (BSC). Hold AHWA to vote on how the platform evolves. Your voice shapes our future.

## What You Can Vote On

### 1. Variable Proposals

Change Winston's settings based on community input. Examples:

- **Swap fees** — Currently 3%, vote to raise/lower it
- **Quiz parameters** — Change WAC reward amounts, question difficulty
- **Revenue splits** — Adjust how the 3% fee is distributed between Academy, Dev, Rewards, etc.
- **Bridge fees** — Modify deposit/withdraw costs per blockchain

**How it works:** Anyone can submit a variable proposal. Community votes yes/no. If it passes, the setting changes automatically.

### 2. Disbursement Proposals

Move funds from revenue groups to specific providers. Examples:

- **Pay developers** — Group 2 (Development) sends 100,000 USDT to the dev multisig address
- **Fund educators** — Group 1 (Academy) sends 50,000 WIN to instructor payroll
- **Liquidity provision** — Group 4 sends funds to an exchange to add new trading pairs
- **Tron deployment** — Send 10,000 USDT from revenue to a Tron protocol provider

**How it works:** Treasury admins submit disbursement proposals with a recipient address and amount. Votes determine if funds transfer.

### 3. Content Proposals

Approve new quiz questions and educational facts before they go live. Examples:

- **New facts** — "Bitcoin has been around since 2009. True or False?"
- **New quiz questions** — "What is the 51% attack?" with multiple-choice answers
- **Deprecated content** — Remove outdated information

**How it works:** Pending content in the review queue (from WiseGuy auto-extraction or admin submissions) gets routed to a community vote. If approved, content goes live.

---

## How to Vote

Voting is **gasless** — no transaction fees needed.

### Step 1: Check You Hold AHWA

```
/balance
```

You need AHWA on BSC to vote.

### Step 2: View Proposals

```
/proposals          # See active proposals
/proposals passed   # See proposals that already passed
/proposals all      # See everything
```

### Step 3: Vote

When you find a proposal you care about:

```
/vote <proposalId> yes
```

Winston will ask you to **sign a message with your BSC wallet**. This proves you hold AHWA at the time of voting. No gas required.

**Voting power:** 1 AHWA = 1 vote. If you hold 100 AHWA, you have 100 votes per proposal.

### Step 4: Auto-Tally

Once the voting period ends, results are counted automatically. Proposals that pass go into effect immediately.

---

## Voting Rights & Timeline

- **Eligibility:** Must hold AHWA on BSC at the time you vote
- **Voting period:** Typically 48–72 hours per proposal
- **Pass threshold:** Simple majority (>50% of votes)
- **Execution:** Passed proposals execute immediately after voting ends
- **No gas costs:** Signing a message is free

---

## Why AHWA Matters

AHWA holders are **the community steering committee** of Winston. You decide:

1. **How we allocate revenue** — Should we spend more on education or development?
2. **What features we prioritize** — Should we add a new blockchain or improve the app?
3. **What we learn** — Which facts and quizzes represent our values?
4. **Who we partner with** — Which service providers get funded?

Without AHWA voting, these decisions would be made by a small group. With AHWA, they're made by you.

---

## AHWA Liquidity

AHWA is paired with WIN and stablecoins on major DEXes, ensuring:

- **Easy buying/selling** — Convert USDT or WIN to AHWA without slippage
- **Arbitrage opportunities** — AHWA-WIN pairing allows price convergence across chains
- **Stable value** — Large liquidity pools keep the token stable

---

## Getting AHWA

You can acquire AHWA by:

1. **Earning WIN** — Participating in quizzes, trading, or other ecosystem activities
2. **Buying on exchanges** — PancakeSwap (BSC), Uniswap (if available), other DEXes
3. **Staking or liquidity mining** — Check current rewards programs

Once you hold AHWA on BSC, you can immediately vote on proposals.

---

## Submit Your Own Proposal

Have an idea for the platform? Submit a proposal:

```
/propose governance <variable|disbursement|content> <details>
```

Explain your idea. If the community votes yes, it happens.

---

## Next Steps

- **[QuickStart Guide](../quickstart.md)** — Learn how to trade and earn
- **[RKL Utility](./README.md)** — Understand the cross-chain gateway token
- **[Join Discord](https://discord.gg/winston)** — Discuss proposals with the community

