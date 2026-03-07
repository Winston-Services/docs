# Getting Started with Winston

Welcome to Winston! Whether you're brand new to crypto or a seasoned trader, this 5-minute quickstart will get you trading, learning, and earning right away.

## Step 1: Join the Winston Discord

Head to the [Winston Discord server](https://discord.gg/winston) and accept the server rules. This is your hub for all Winston features, updates, and community support.

## Step 2: Check Available Commands

Type `/help` in any Discord channel to see all Winston commands and what they do.

## Step 3: Check Your Balance

Type `/balance` to see all tokens you currently hold in your Winston wallet.

```
/balance
```

Your balance updates automatically every time you swap, deposit, or trade.

## Step 4: Make Your First Swap

Ready to trade? Here's how to swap 100 RKL for USDT:

```
/swap RKL USDT 100
```

Winston will show you exactly how much USDT you'll receive before you confirm the swap. Choose your slippage tolerance and complete the trade in seconds.

## Step 5: Ask WiseGuy (Our AI Teacher)

Curious about DeFi concepts but don't want to read a textbook? Ask WiseGuy:

```
/ask "What is an AMM?"
```

WiseGuy uses Claude AI to give beginner-friendly explanations. You can ask follow-up questions and build on previous answers for multi-turn conversations.

## Step 6: Take a Quiz and Earn WAC

Build your knowledge and earn rewards at the same time:

```
/quiz
```

Answer blockchain and Winston questions. Get them right and earn WAC credits. Accumulate points toward your next reward level.

## Step 7: Deposit Crypto from a Blockchain

Ready to move funds into Winston? Let's say you have Bitcoin and want to deposit 0.1 BTC:

```
/deposit BTC 0.1
```

Replace `BTC` with your blockchain (ETH, BSC, Polygon, Tron, etc.). Winston gives you a deposit address. Send your funds there, and they'll appear in your wallet within minutes.

**Privacy note:** Deposit confirmations are sent to your DMs, not the public channel.

## Step 8: Add Liquidity and Earn Fees

Want to earn passive income? Add liquidity to a trading pool:

```
/addLiquidity RKL USDT 100 50
```

This adds 100 RKL and 50 USDT to the RKL/USDT pool. You get LP tokens representing your share. Every time someone swaps in that pool, you earn 3% of the fee.

## Step 9: Withdraw Back to Your Blockchain

When you're ready to move funds out:

```
/withdraw BTC 0.05
```

Specify the blockchain and amount. Winston deducts a small network fee and sends it to your on-chain address.

## Step 10: Check the Cheatsheet for Current Rates

Want to know current swap rates and withdraw fees for all chains?

```
/cheatsheet
```

This shows you all trading pairs, liquidity pool status, and per-chain withdrawal costs.

---

## Prefer REST API?

Developers and advanced users: Winston has a full REST API at `https://api.winston.services/api/v1/command`. All Discord commands work the same way over HTTP with JWT or API key authentication. See the [Developers](../developers/api.md) section for details.

---

**Next steps:**
- Explore the [Winston Services Overview](./publish-your-docs.md) to understand the full ecosystem
- Learn about [RKL Utility](./rickle-utility/README.md) and [AHWA Governance](./rickle-utility/ahwa-utility.md)
- Check out [TradeTower DEX](../tradetower/) for advanced trading features
