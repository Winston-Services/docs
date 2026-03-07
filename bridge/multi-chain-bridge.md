# Multi-Chain Bridge

The TradeTower bridge connects your real crypto wallets across 11 blockchains directly to your TradeTower account. Deposit crypto from anywhere, withdraw to anywhere — all verified on-chain, all private.

## How It Works

The bridge operates a custodial hot wallet pool on each supported blockchain. When you deposit, TradeTower monitors the blockchain and mints internal tokens representing your funds. When you withdraw, TradeTower sends from its pool and burns your internal balance. Your funds stay in a distributed network of addresses — never sitting in a single wallet.

## Supported Blockchains

### EVM Chains (Ethereum-Compatible)

* **Ethereum (ETH)** — Mainnet, gas-intensive, most liquid
* **BNB Smart Chain (BSC)** — Fast, low cost
* **Arbitrum (ARB)** — Layer 2, very low fees
* **Polygon (POL)** — Layer 2, fast and cheap
* **Gnosis (GNO)** — Experimental, DAO-focused

### UTXO Chains

* **Bitcoin (BTC)** — Native SegWit (bech32 addresses, bc1q...)
* **Litecoin (LTC)** — Native SegWit (bech32 addresses, ltc1q...)
* **Pepecoin (PEP)** — Smaller UTXO chain
* **Dogecoin (DOGE)** — Community-driven UTXO chain

### Account-Based

* **Tron (TRX)** — Fast, low cost, energy-based fees

## Supported Tokens

Each chain supports its native currency plus popular stablecoins and tokens:

* **EVM:** Native currencies (ETH, BNB, ARB, etc.) + ERC-20 tokens (USDT, USDC, etc.)
* **UTXO:** Native only (BTC, LTC, PEP, DOGE)
* **Tron:** Native TRX + TRC-20 tokens (USDT, etc.)

New token support is added continuously as trading demand grows.

## Deposits

### How It Works

{% stepper %}
{% step %}
Run the `/deposit <chain> <token>` command in Discord
{% endstep %}

{% step %}
TradeTower assigns you a temporary deposit address from its hot wallet pool
{% endstep %}

{% step %}
Send your crypto to that address from your real wallet
{% endstep %}

{% step %}
TradeTower monitors the blockchain for incoming transactions
{% endstep %}

{% step %}
Once confirmed on-chain, your balance appears in TradeTower automatically
{% endstep %}

{% step %}
You receive a private DM with confirmation, amount, and explorer link
{% endstep %}
{% endstepper %}

### Deposit Addresses

Each deposit address is assigned to you for 7 days. After 7 days, the address gets recycled and assigned to another user. TradeTower keeps track of which address belongs to whom, so receiving funds after expiration still works — the system verifies the transaction and credits you accordingly.

### Minimum Amounts

Minimum deposit varies by chain. Bitcoin requires more than Polygon. Check `/cheatsheet` to see current minimums.

## Withdrawals

### How It Works

{% stepper %}
{% step %}
Run the `/withdraw <amount> <token> <chain> <address>` command
{% endstep %}

{% step %}
Provide your destination wallet address on that chain
{% endstep %}

{% step %}
TradeTower sends from its hot wallet pool and burns your internal balance
{% endstep %}

{% step %}
Transaction broadcasts to the blockchain
{% endstep %}

{% step %}
You receive a private DM with the transaction hash and explorer link
{% endstep %}
{% endstepper %}

### Withdrawal Addresses

* **EVM:** Standard hex addresses (0x...)
* **Bitcoin/Litecoin:** Bech32 addresses (bc1q..., ltc1q...)
* **Pepecoin/Dogecoin:** Base58 addresses (P..., D...)
* **Tron:** T-addresses (T...)

### Withdrawal Fees

Fees vary by chain and token type:

**Native and UTXO:** Flat fee per withdrawal (displayed in `/cheatsheet`)

**ERC-20 and TRC-20:** Dynamic gas-station pricing. TradeTower estimates the network gas cost, converts it to the token you're withdrawing via the AMM pools, and quotes the exact fee in that token. This way, if you're withdrawing USDT, you pay the fee in USDT — no surprises.

All fees are deducted from your withdrawal amount. If gas prices spike, you may need to wait for them to drop or increase your withdrawal amount.

### Minimum Withdrawal Amounts

Each chain has a minimum withdrawal to prevent dust. See `/cheatsheet` for current limits.

## Security & Privacy

### On-Chain Verification

Every deposit is verified on-chain before being credited. TradeTower tracks the transaction hash and only mints tokens once the transaction is confirmed at the blockchain's finality point. Double deposits are blocked — the same transaction hash cannot be credited twice.

### Private by Default

Deposit and withdrawal confirmations are sent as private DMs to your Discord account, not posted in public channels. The channel receives only a "details sent to your DMs" notification. This keeps your transaction details private.

### No KYC

Bridge deposits and withdrawals are permissionless. No account verification required — just connect to Discord and send crypto.

## Commands

* `/deposit <chain> <token>` — Get a temporary deposit address
* `/withdraw <amount> <token> <chain> <address>` — Send crypto to an external wallet
* `/balance [token]` — Check your TradeTower balances
* `/cheatsheet` — See current fees, minimums, and supported chains

## Network Status

TradeTower monitors all blockchains for failed connections and displays health status. If a chain is down, deposits and withdrawals are paused until it comes back online. Run `/chainstatus` to see real-time connectivity.
