# Supported Chains

TradeTower supports deposits and withdrawals across 11 blockchains spanning three major network types. More chains are added regularly as the network grows.

## EVM Chains (Ethereum-Compatible)

EVM chains run the Ethereum Virtual Machine and support smart contracts. All EVM chains in TradeTower share the same wallet derivation path for simplicity.

### Ethereum (ETH)

* **Native currency:** ETH
* **Network ID:** 1
* **Wallet format:** Hex (0x...)
* **Supported tokens:** ETH + ERC-20 (USDT, USDC, DAI, and others)
* **Characteristics:** Highest liquidity, highest gas fees, most established
* **Finality:** \~12 seconds

### BNB Smart Chain (BSC)

* **Native currency:** BNB
* **Network ID:** 56
* **Wallet format:** Hex (0x...) — same as Ethereum
* **Supported tokens:** BNB + BEP-20 (USDT, USDC, DAI, and others)
* **Characteristics:** Low fees, fast blocks, strong DeFi ecosystem
* **Finality:** \~3 seconds
* **Governance:** AHWA token lives on BSC

### Arbitrum (ARB)

* **Native currency:** ETH (wrapped from Ethereum)
* **Network ID:** 42161
* **Wallet format:** Hex (0x...)
* **Supported tokens:** ETH + ERC-20 (USDT, USDC, and others)
* **Characteristics:** Layer 2 rollup, very low fees, fast finality
* **Finality:** \~1 second

### Polygon (POL)

* **Native currency:** MATIC → POL (rebranded)
* **Network ID:** 137
* **Wallet format:** Hex (0x...)
* **Supported tokens:** POL + ERC-20 (USDT, USDC, and others)
* **Characteristics:** Sidechain/plasma, low fees, high throughput
* **Finality:** \~2 seconds

### Gnosis (GNO)

* **Native currency:** xDAI
* **Network ID:** 100
* **Wallet format:** Hex (0x...)
* **Supported tokens:** xDAI + ERC-20 (limited ecosystem)
* **Characteristics:** DAO-focused, extremely low fees, niche adoption
* **Finality:** \~5 seconds

EVM Derivation: All EVM chains use BIP44 path `m/44'/60'/0'/0/{index}`. This means your Ethereum address is the same format as your BSC, Arbitrum, Polygon, and Gnosis addresses — same private key, same address on all five chains.

## UTXO Chains (Bitcoin-Compatible)

UTXO chains use an unspent transaction output model. Each withdrawal consumes outputs and creates new ones. UTXO chains have higher security (longer history) but slower confirmation times.

### Bitcoin (BTC)

* **Native currency:** BTC (21 million cap)
* **Wallet format:** Bech32 SegWit (bc1q...)
* **Derivation path:** BIP84 (m/84'/0'/0'/0/{index})
* **Characteristics:** Most secure, most recognized, highest value
* **Confirmation time:** \~10 minutes, \~6 confirmations finality (\~60 min)
* **Block size:** 4 MB with SegWit

### Litecoin (LTC)

* **Native currency:** LTC (84 million cap)
* **Wallet format:** Bech32 SegWit (ltc1q...)
* **Derivation path:** BIP84 (m/84'/2'/0'/0/{index})
* **Characteristics:** Faster than Bitcoin, more affordable fees
* **Confirmation time:** \~2.5 minutes, \~6 confirmations (\~15 min)
* **Block size:** 4 MB with SegWit

### Pepecoin (PEP)

* **Native currency:** PEPE
* **Wallet format:** Base58 (P...)
* **Derivation path:** BIP44 (m/44'/3434'/0'/0/{index})
* **Characteristics:** Community-driven, meme coin, small but active ecosystem
* **Confirmation time:** \~1 minute
* **L2 Anchoring:** TradeTower uses Pepecoin OP\_RETURN transactions to anchor L2 state on-chain (write-only, no read costs)

### Dogecoin (DOGE)

* **Native currency:** DOGE (unlimited supply)
* **Wallet format:** Base58 (D...)
* **Derivation path:** BIP44 (m/44'/3'/0'/0/{index})
* **Characteristics:** Oldest meme coin, strong community, robust infrastructure
* **Confirmation time:** \~1 minute
* **Block size:** 1 MB

UTXO Notes: Bitcoin and Litecoin use BIP84 native SegWit for lower fees and smaller transactions. Pepecoin and Dogecoin use BIP44 P2PKH for broader compatibility.

## Account-Based Chains

Account-based chains use smart contract accounts with nonces instead of UTXOs.

### Tron (TRX)

* **Native currency:** TRX
* **Wallet format:** T-address (T...)
* **Derivation path:** BIP44 (m/44'/195'/0'/0/{index})
* **Supported tokens:** TRX + TRC-20 (USDT, USDC, and others)
* **Characteristics:** Fast, low cost, energy-based fee model
* **Finality:** \~3 seconds
* **Energy:** TRC-20 transfers use ENERGY instead of gas (faster, cheaper)

## Choosing a Chain

* **Fast and cheap?** Use Arbitrum, Polygon, or Tron
* **Most secure?** Use Bitcoin or Ethereum
* **Low fees, stable?** Use BSC or Litecoin
* **Community vibes?** Use Pepecoin or Dogecoin

TradeTower displays current fees, minimums, and confirmation times in /cheatsheet. Pick the chain that matches your needs.

## Token Support

Native tokens (ETH, BNB, MATIC, TRX, BTC, LTC, PEP, DOGE) are always available.

Popular stablecoins and tokens are supported on each chain:

* **EVM:** USDT, USDC, DAI, USDT-e, and others
* **UTXO:** Native only
* **Tron:** USDT, USDC, and others (TRC-20)

If you don't see a token, request it — new token support is added as trading demand grows.

## Wallet Address Formats at a Glance

| Chain                                    | Format    | Example           |
| ---------------------------------------- | --------- | ----------------- |
| Ethereum, BSC, Arbitrum, Polygon, Gnosis | Hex       | 0x1234...abcd     |
| Bitcoin, Litecoin                        | Bech32    | bc1q..., ltc1q... |
| Pepecoin, Dogecoin                       | Base58    | P..., D...        |
| Tron                                     | T-address | T...              |

When you deposit or withdraw, TradeTower will validate the address format for the chain you select. Invalid addresses are rejected before any transaction is sent.

## Deposit & Withdrawal Limits

Each chain has minimum and maximum amounts to prevent dust and manage risk. Limits vary by token. Check /cheatsheet for current limits.

Example minimums:

* Bitcoin: 0.001 BTC (\~$40)
* Ethereum: 0.1 ETH (\~$200)
* USDT on Polygon: 50 USDT

Maxima prevent TradeTower from holding too much on any single wallet. If you need to move more, split into multiple transactions.

## Future Chains

TradeTower's architecture supports any blockchain. The roadmap includes:

* More EVM chains (Optimism, Base, Linea, zkSync, and others)
* More UTXO chains (if demand grows)
* Cosmos and IBC-enabled chains
* Solana, Sui, and Move-based blockchains

As adoption grows, more chains will be added. The network is designed to scale to 50+ chains without compromising security or performance.
