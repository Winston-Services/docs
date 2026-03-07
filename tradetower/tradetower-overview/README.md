# TradeTower Overview

### What Is TradeTower?

TradeTower is a decentralized exchange (DEX) built into Discord. You swap tokens using simple commands. No web interface to log into. No self-custodial wallet to manage. Just type `/swap` and execute — the exchange handles everything on its side.

It's a real exchange, not a game or simulation. The tokens you trade have real value. The prices are determined by an Automated Market Maker (AMM) using the same math as Uniswap v2. Every trade is final and recorded.

### How It Works

TradeTower runs an internal ledger of token balances and liquidity pools. When you trade, you're moving tokens between your account and a pool's reserves. The pool's prices adjust based on supply and demand (constant-product formula). Every swap charges a 3% fee that stays in the pool — meaning liquidity providers earn it over time.

### Key Features

#### Multi-Chain Bridge

Your Discord account connects to real blockchains via a custodial bridge. Deposit tokens from Ethereum, BSC, Bitcoin, or 8 other chains. Trade on TradeTower. Withdraw back to the chain of your choice.

No private key management. No hardware wallet needed. Your deposits are secured through a hot wallet pool system — multiple wallets distributed across chains, so funds never sit in a single point of failure.

#### Community-Governed

Hold AHWA tokens? You can vote on:

* Platform setting changes
* New quiz content and educational materials
* Treasury spending and disbursements
* Future feature directions

Governance is simple. Sign a message from your wallet, broadcast your vote, and the community tallies results. No special permissions. No gatekeeping.

#### AI-Powered Education

Ask questions with `/ask`. Get answers from an AI trained on blockchain fundamentals, Winston ecosystem knowledge, and platform mechanics. Take quizzes with `/quiz`. Earn learn-to-earn credits (WAC) for correct answers.

All quiz content is community-vetted through governance proposals. Wrong answers don't ship.

#### No Smart Contract Risk

TradeTower doesn't rely on complex smart contracts. It's a custom-built AMM engine. The risk surface is smaller. The code is open and auditable. No flash loan attacks, no reentrancy bugs — because the attack surface doesn't exist.

The bridge uses standard protocols: ERC-20 transfers on EVM chains, UTXO spending on Bitcoin, TRC-20 on Tron. All tried-and-true.

### Revenue That Funds Everything

Every swap charges 3%. That fee is the entire revenue model:

* 20% funds learn-to-earn academy payouts
* 26% rewards asset holders with proportional distributions
* 28% pays for management, development, and marketing
* 18% pays eligible node operators
* 6.5% auto-recycles into liquidity pools
* 1.5% covers operational costs

No VC takes a cut. No founder dilution event. The platform funds itself from day one.

### Platforms

#### Discord

Type commands directly in Discord. Fastest for casual traders. Full feature set. Messages stay in your server history.

#### REST/Web API

Make programmatic trades. Build bots or integrate TradeTower into your app. Authenticate with JWT or API key. Same commands, different interface.

#### Coming Soon

Telegram bot and X integration — same exchange, anywhere you chat.

### The First Client of a Larger Platform

TradeTower is built on a platform-agnostic architecture. The core AMM engine, bridge, and education system are separate from the Discord/REST layer. This means:

* New platforms can be added without rewriting core logic
* Tokens and liquidity pools are shared across all clients
* Governance votes apply to the entire ecosystem
* State is synchronized in real-time via P2P

Today it's Discord + REST. Tomorrow it could be Telegram, X, and web. One exchange, many doors in.

### Security & Transparency

#### On-Chain Anchoring

L2 state commitments are anchored on-chain (Pepecoin OP\_RETURN) at regular intervals. Anyone can download and verify the entire transaction history using cryptographic proofs.

#### Node Operators

Community members run nodes that validate state and relay updates through a peer-to-peer mesh. Each node earns a share of the revenue generation pool if it stays honest and online.

#### Privacy Proofs

Users can prove their balance without revealing which tokens they own or how much. Zero-knowledge proofs keep trading activity private while maintaining audit-ability.

### Getting Started With TradeTower

```
/help                     See all commands
/swap <from> <to> <amount>   Trade tokens
/quote <from> <to> <amount>  Check price first
/addLiquidity <a> <b> <amt>  Earn LP fees
/balance                  See your holdings
/withdraw <token> <amount> <chain>  Get funds back
/ask <question>           Learn from AI
/quiz                     Earn learn-to-earn credits
/deposit <chain>          Get a wallet address
```

Start by checking your balance, then try a small swap. Everything is reversible — if you made a bad trade, you can swap back.

### What Makes This Different?

Traditional DEXes like Uniswap are smart-contract based. You approve contracts, they move funds, you hope they're audited. It's trustless but complex.

TradeTower is custodial. You trust the platform, but in exchange you get simplicity. No wallet management. No approval transactions. No gas fees (they're built into the bridge withdrawal cost). Type one command and you're done.

It's a different tradeoff: **custody + simplicity vs. self-custody + complexity**.

For everyday people who want to trade without becoming blockchain experts, TradeTower is the better choice.

### Next Steps

1. Join the Discord
2. Use `/help` to see all commands
3. Read AMM & Swapping to understand how trades work
4. Try a small `/swap` or deposit from another chain
5. Ask questions with `/ask` — no dumb questions

Welcome to Winston.
