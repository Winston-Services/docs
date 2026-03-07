# L2 State Commitments

TradeTower operates as a Layer 2 system where all trading happens internally on a fast, free ledger. But unlike traditional L2s that roll up to Ethereum, TradeTower anchors its state to the Pepecoin blockchain — a simpler, more accessible chain that any node operator can monitor and verify.

## How It Works

Every trade, deposit, and withdrawal updates the internal state. Instead of waiting for slow blockchain confirmations, TradeTower commits these changes instantly. But periodically — typically every few hours or more frequently during high trading volume — the system captures a snapshot of this state and writes a compact proof to the Pepecoin blockchain.

This proof is an 80-byte message called an epoch commit, written as an OP_RETURN transaction on the Pepecoin blockchain. It contains a single hash: the state root. Think of this like taking a fingerprint of the entire system's state at one moment in time.

## Three Roots, One Truth

TradeTower tracks state using three independent Merkle trees (a cryptographic data structure that produces a single hash representing an entire dataset):

{% stepper %}
{% step %}
#### StateTree

Hash of all token balances and liquidity pool reserves using keccak hashing.
{% endstep %}

{% step %}
#### ZKTree

Hash of the same data using Poseidon hashing, a special hash function optimized for zero-knowledge proofs.
{% endstep %}

{% step %}
#### BalanceTree

Hash of user balances with privacy commitments, also using Poseidon.
{% endstep %}
{% endstepper %}

All three roots are committed to the blockchain at every epoch. This redundancy ensures that:

* Any node can verify the complete state by checking these roots
* Different nodes computing the same state will produce identical roots
* If a node's state diverges, it becomes immediately obvious

## Bootstrap & Recovery

Normally, a new node joins the P2P mesh and receives the current state from peers. But what if all nodes go offline? The blockchain becomes the source of truth.

Every N epochs (configurable via governance), TradeTower writes full state deltas to the Pepecoin blockchain using inscriptions — a method similar to Bitcoin Ordinals or Doginals. These full snapshots, called Pepinals, contain enough data for any node to reconstruct the entire state from scratch by reading the chain.

This means TradeTower state is resilient to total network failure. The blockchain is the ultimate backup.

## Adaptive Epoch Frequency

Epoch commits are not fixed in timing. Instead, they adapt to trading activity:

* During slow periods: commits every 24 hours
* During normal trading: commits every 1–4 hours
* During high volume: commits every 1 hour or more frequently

This is governance-tunable. More frequent commits = higher blockchain overhead but lower data loss in case of failure. The network collectively decides the trade-off.

## Why This Matters

Traditional DEXs rely on a central database. If the operator disappears, funds may be lost. TradeTower stores the source of truth on an immutable blockchain. Even if every TradeTower node disappears, state can be recovered from the blockchain and verified by anyone.

This is decentralization without requiring massive computation or expensive rollups. State commitments cost fractions of a cent. Full inscriptions cost a few dollars per month. The entire system is audit-able and verifiable on a public blockchain.

## Implementation Details

* **Chain**: Pepecoin (merged-mined with Bitcoin, highly secure)
* **Commitment method**: OP_RETURN for epochs, P2SH inscriptions for full snapshots
* **Hash functions**: keccak (StateTree), Poseidon (ZKTree/BalanceTree)
* **Frequency**: 1–24 hours, adapts to volume
* **Cost**: ~0.02 PEP per epoch (~$0.0001 USD), ~$0.50 for monthly full snapshot

No staking. No complex consensus. Just immutable, auditable state on a blockchain.
