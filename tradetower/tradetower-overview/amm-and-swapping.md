# AMM & Swapping

## What Is an AMM?

An Automated Market Maker (AMM) is a simple pricing formula instead of an order book.

Imagine a pool with 1000 RKL and 2000 USDT. If you want to buy RKL with USDT, the pool's price is determined by one rule:

```
(RKL in pool) * (USDT in pool) = constant
```

So if you buy 100 RKL, the pool adjusts:

```
(1000 - 100) * (2000 + X) = 1000 * 2000
900 * (2000 + X) = 2,000,000
X = 222.22 USDT
```

You pay 222.22 USDT to buy 100 RKL. The price increased because the pool now has less RKL, so RKL is more scarce.

This is the x \* y = k formula. It's simple, fair, and self-adjusting. No order book needed. No centralized exchange needed.

## Slippage & Price Impact

Because the AMM adjusts price based on pool depth, bigger trades have bigger impact.

If you sell 10 RKL, you might get back 20 USDT. But if you sell 500 RKL, the pool's reserve of USDT shrinks so much that you only get back 800 USDT (not 1000). This difference is slippage — the gap between your expected and actual fill price.

How to reduce slippage:

* Trade smaller amounts
* Use deep pools (more liquidity = less price movement)
* Trade in pairs with high volume (RKL/USDT is deeper than RKL/obscure-token)

TradeTower shows you the expected slippage before you confirm a trade. Check it. If it's high, maybe wait or break your trade into smaller pieces.

## The Fee: 3% On Every Swap

Every swap charges a 3% fee. You don't pay this directly — it comes out of the output you receive.

So if you sell 100 USDT expecting to get back 50 RKL:

* 3 USDT goes to the fee (3%)
* 97 USDT is used for the actual swap
* You get back about 48.5 RKL instead of 50 RKL

Where does the fee go? Into the pool's reserves. This means liquidity providers (people who added tokens to the pool) earn the fee over time. Their LP tokens represent a claim on growing reserves.

This fee is how Winston funds itself. See the economics explanation in Overview.

## How To Swap

Use the /swap command:

```
/swap RKL USDT 100
```

This sells 100 RKL and buys however much USDT you get back (after slippage and fees).

Or:

```
/swap USDT RKL 200
```

This buys as much RKL as 200 USDT will get you.

TradeTower will show you:

* Expected output (before fees)
* Fees you're paying
* Actual output (after fees and slippage)
* The exchange rate you're getting

Review it. If it looks good, confirm. The trade is instant.

## Check Price First: /quote

Before you commit to a swap, use /quote to see what you'd get:

```
/quote RKL USDT 100
```

This shows you the price, fees, and slippage — but doesn't execute the trade. Zero cost. Use it to plan your trades.

## Multi-Hop Swaps

Not all tokens have direct pools. If you want to swap from obscure-token-A to obscure-token-B, but there's no A/B pool, TradeTower can route through a common token:

```
A -> USDT -> B
```

This uses two pools instead of one. Each incurs a 3% fee (so 6% total). More slippage. But you can still execute the trade.

## Real-Time Pricing

Prices in TradeTower are real. They're not stale quotes from some external API. They're determined by the actual pool reserves at the moment you execute.

This means:

* No surprise slippage (you see it before confirming)
* No pricing lag (pools adjust instantly as trades execute)
* No oracle dependency (the AMM IS the oracle)

## Gas Station Model: ERC-20 Withdrawal Fees

When you withdraw tokens from an EVM chain (Ethereum, BSC, Arbitrum, etc.), someone has to pay on-chain gas.

TradeTower uses a gas station model: instead of charging you a flat fee, it estimates the actual gas cost and quotes it in the token you're withdrawing.

{% stepper %}
{% step %}
### How the gas station model works

1. TradeTower estimates: "This ERC-20 transfer costs 0.001 ETH in gas"
2. It quotes: "0.001 ETH = X units of your withdrawal token" (using a 2-hop AMM route: native -> USDT -> your token)
3. It deducts X from your withdrawal amount
4. You receive: withdrawAmount - X

This means you only pay for what gas actually costs. During high network congestion, you might pay more. During low congestion, you pay less. It's fair and transparent.

If gas costs more than your withdrawal amount, the system rejects the trade. You'd need to withdraw a larger amount or pick a cheaper chain.
{% endstep %}
{% endstepper %}

## Chain Fees

Each blockchain has different withdrawal minimums and costs:

* Bitcoin: Slower, costs vary by network congestion (SAT/byte)
* Ethereum: Higher gas costs, but final (1-min block time)
* BSC: Fast, low fees
* Pepecoin: Mempool mining, economical for L2 state anchoring
* Dogecoin: Fast, cheap, ASCII-encodable
* Tron: Very fast, variable energy costs

Check /cheatsheet to see current fees for your chosen withdrawal chain.

## Common Mistakes

1. Not checking slippage\
   If you're swapping 10% of a pool's reserves, expect 10%+ slippage. Check /quote first.
2. Swapping obscure tokens\
   Deep liquidity (RKL/USDT, RKL/USDC) has low slippage. New tokens with thin pools have high slippage.
3. Trying to withdraw less than the minimum\
   Every chain has a minWithdraw. Check it with /cheatsheet before you try.
4. Expecting zero fees\
   Every swap costs 3%. It's how the ecosystem funds itself. Don't be surprised.

## Advanced: Liquidity Pools & LP Tokens

If you want to earn yield (rather than just trade), you can add liquidity to a pool.

You deposit equal value of both tokens. You get back LP tokens. Over time, as people swap through your pool, the 3% fee accrues to your LP stake. Your LP tokens represent more and more of the pool's reserves.

See Liquidity Pools for the full guide.

## Next Steps

{% stepper %}
{% step %}
### 1. Use /quote to check a price
{% endstep %}

{% step %}
### 2. Try a small /swap
{% endstep %}

{% step %}
### 3. Check your /balance
{% endstep %}

{% step %}
### 4. If you want to earn fees, read Liquidity Pools
{% endstep %}
{% endstepper %}

Welcome to DeFi trading.
