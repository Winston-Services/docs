# Liquidity Pools

## What Is a Liquidity Pool?

A liquidity pool is like a shared pot of money that traders can buy from and sell to. If you put your tokens into the pool, you own a share of it. As traders swap through the pool, they pay a 3% fee. That fee accumulates in the pool. Over time, your share of the pool grows.

**Example:** You own 10% of a RKL/USDT pool. The pool has 1000 RKL and 2000 USDT. You own 100 RKL and 200 USDT.

Traders make 100 swaps through the pool. The pool now has 1050 RKL and 2100 USDT (the fees accumulated as reserves grew). You still own 10%. Now you own 105 RKL and 210 USDT.

You earned 5 RKL and 10 USDT just by letting your tokens sit in the pool.

## Why Does This Matter?

Traditional savings accounts give you 3-4% annual yield if you're lucky. AMM liquidity pools earn you the **3% fee on every single swap that goes through the pool**.

If a pool is busy (high volume), you earn more. This creates incentive: if you think a token will be popular, add liquidity and earn as it trades.

It's how Winston's ecosystem sustains itself **without VC funding**. People add liquidity. People trade. Traders pay fees. Fee accumulate to liquidity providers. Everyone wins.

## How To Add Liquidity

Use the `/addLiquidity` command:

```
/addLiquidity RKL USDT 1000
```

This says: "I want to add liquidity to the RKL/USDT pool. I'll put in 1000 RKL."

TradeTower calculates how much USDT you need to match (1000 RKL = X USDT based on current pool price). You confirm. Both tokens are deposited. You receive LP tokens in return.

The LP tokens represent your **ownership stake** in the pool.

## LP Tokens: Your Proof of Ownership

When you add liquidity to a RKL/USDT pool, you get back RKL-USDT LP tokens. These tokens represent your share of the pool.

If the RKL-USDT pool has 10,000 RKL and 20,000 USDT, and you add 1000 RKL + 2000 USDT, you own 10% of the pool. You get 10% of all LP tokens.

Over time:

* Traders pay fees. The pool's reserves grow.
* Your LP tokens still represent 10%. But 10% of bigger reserves = more tokens.
* To cash out, you `/removeLiquidity` and burn your LP tokens. You get back your share of the grown reserves.

## How Fees Accumulate

Every swap costs 3%. That 3% stays in the pool.

```
Swap: Sell 100 USDT for RKL
- 3 USDT is the fee
- 97 USDT is used for the actual swap
- 3 USDT added to pool reserves
```

If 1000 swaps happen per week in the RKL/USDT pool, that's 30,000 USDT worth of fees per week (assuming average trade size). All liquidity providers split that 30,000 USDT proportional to their ownership.

The more volume, the more fees. The more you own, the more you earn.

## How To Remove Liquidity

When you want to cash out:

```
/removeLiquidity RKL-USDT LP 50
```

This burns 50 RKL-USDT LP tokens and returns your proportional share of the pool's reserves.

Since the pool has grown (from fees), you probably get back more tokens than you put in.

```
You put in:   1000 RKL + 2000 USDT
You get back: 1050 RKL + 2100 USDT (after earning 50 swaps worth of fees)
```

You can remove all your liquidity anytime. No lockup. No vesting. Your tokens are always yours.

## Impermanent Loss: The Catch

There's one risk: **impermanent loss**.

If you add equal value of two tokens to a pool, and one token's price shoots up way faster than the other, you're in a weird position.

**Example:**

* Pool: 1000 RKL (worth $1 each) + 1000 USDT
* You add 100 RKL + 100 USDT
* Later: RKL price is $2, USDT is still $1
* If you had just held: 100 RKL = $200, 100 USDT = $100. Total = $300
* If you had stayed in the pool: You'd have maybe 70 RKL + 130 USDT. Worth ~$280

You made less money by being in the pool than if you'd just held. This is impermanent loss — the AMM automatically rebalanced as the price moved, and you ended up on the wrong side.

**But:** If the pool was high-volume, the 3% fees might have made up the difference. It depends on the fee intensity vs. price volatility.

**How to manage it:**

* Add liquidity to stable pairs (RKL/USDT has less volatility than RKL/new-token)
* Choose pairs with high volume (more fees = better compensation)
* Don't add liquidity to brand-new tokens that might 10x
* Accept that some IL is normal — fees usually make up for it over time

## The Revenue Cycle: How Winston Sustains Itself

{% stepper %}
{% step %}
### You add liquidity

You add liquidity to earn yield.
{% endstep %}

{% step %}
### People trade

People trade and pay 3% fees.
{% endstep %}

{% step %}
### Fees accumulate in your LP pool

Fees accumulate to liquidity providers' pools.
{% endstep %}

{% step %}
### 20% to the Academy

Every 24 hours (or when needed), Winston distributes 20% of trading fees to its Academy (for learn-to-earn payouts).
{% endstep %}

{% step %}
### 26% to member rewards

26% goes to member rewards (proportional share based on what you hold).
{% endstep %}

{% step %}
### 18% to node operators

18% goes to eligible node operators (who run the P2P network).
{% endstep %}

{% step %}
### 28% to development/management/marketing

28% goes to development, management, marketing (via community governance).
{% endstep %}

{% step %}
### 6.5% auto-recycles into liquidity

6.5% auto-recycles into liquidity pools (keeps pools deep and fees flowing).
{% endstep %}

{% step %}
### Back to step 1

People see liquidity is good, they add their own liquidity, and the cycle repeats.
{% endstep %}
{% endstepper %}

**No VC. No founder premine. No ICO pump-and-dump.**

Winston funds itself from day one through the 3% swap fee. Everyone who participates earns. No one subsidizes anyone else.

## Slippage vs. Depth

Liquidity pools need depth. A pool with 100 RKL and 100 USDT is shallow. Traders moving large amounts will face huge slippage. Few traders = few fees.

A pool with 100,000 RKL and 100,000 USDT is deep. Traders can move large amounts with low slippage. High volume = high fees.

This creates natural incentive: **If Winston's most important pairs (RKL/USDT, WIN/USDT) are deep, everyone earns more.**

The 6.5% liquidity auto-recycling keeps this flywheel spinning.

## Which Pools Should You Add To?

**Best choices:**

* **Established pairs** (RKL/USDT, WIN/USDT) — high volume, low impermanent loss risk
* **Stable pairs** (USDT/USDC, etc.) — almost zero impermanent loss, reliable fees
* **Hyped pairs** (if you want to gamble) — huge potential fees if volume explodes, but huge impermanent loss if hype dies

**Avoid:**

* Pair with brand new tokens (high impermanent loss if they dump)
* Pairs with zero volume (you earn nothing)
* Pairs with huge price volatility and low volume (worst of both worlds)

Start with the main pairs: RKL/USDT and WIN/USDT. Build from there as you understand the dynamics.

## Advanced: LP Fee Tiers

In future versions of Winston, different pool pairs might have different fee tiers (0.1%, 0.3%, 1%, 5%). Higher fees compensate for riskier pairs. This is how Uniswap v3 works. TradeTower currently uses 3% across the board, but this can be governed into changes.

## Getting Started

{% stepper %}
{% step %}
### Check which pools exist

Use `/pools` or check TradeTower's UI.
{% endstep %}

{% step %}
### Review volume and depth

Busier pools = better returns.
{% endstep %}

{% step %}
### Use `/quote`

Use `/quote` to see slippage at your desired liquidity size.
{% endstep %}

{% step %}
### Add to a deep, high-volume pair first

Start with a deep, high-volume pair.
{% endstep %}

{% step %}
### Monitor your LP tokens and earnings

Watch your LP tokens and earnings over time.
{% endstep %}

{% step %}
### Remove liquidity whenever needed

Remove liquidity whenever you need your money.
{% endstep %}
{% endstepper %}

## FAQ

<details>

<summary>Q: Can I lose my tokens in a liquidity pool?</summary>

A: No. Your LP tokens can only increase in value (more fees) or stay the same (no activity). The only risk is impermanent loss (worse return than if you'd held the tokens outright).

</details>

<details>

<summary>Q: How often do I earn fees?</summary>

A: Continuously. Every swap contributes to your pool. Your LP tokens' value grows in real-time as fees accumulate.

</details>

<details>

<summary>Q: What if I want to add more liquidity later?</summary>

A: Use `/addLiquidity` again. It calculates the current pool ratio and adjusts. You get more LP tokens added to your stake.

</details>

<details>

<summary>Q: What if the price ratio changes?</summary>

A: The AMM automatically rebalances. If RKL price doubles, the pool will have fewer RKL and more USDT. Your LP tokens still represent the same ownership percentage, but now of rebalanced reserves.

</details>

<details>

<summary>Q: When should I remove liquidity?</summary>

A: Only when you need the money or want to take profits. There's no time pressure. Fees accumulate forever as long as the pool is active.

</details>

## Next Steps

{% stepper %}
{% step %}
Pick a stable, high-volume pair.
{% endstep %}

{% step %}
Start with a small `/addLiquidity` to learn.
{% endstep %}

{% step %}
Monitor your LP tokens and watch fees accumulate.
{% endstep %}

{% step %}
Come back to `/removeLiquidity` when you want to cash out.
{% endstep %}
{% endstepper %}

Welcome to yield farming.
