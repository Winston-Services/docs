# ZK Proofs & Privacy

Zero-knowledge proofs allow you to prove something is true without revealing any underlying information. For example: prove you have 1000 tokens without showing your actual balance, or prove a transaction is valid without exposing all transaction details.

TradeTower uses zero-knowledge proofs to enable privacy-preserving operations while maintaining full auditability.

## Two Types of Proofs

### Merkle Inclusion Proofs

A Merkle inclusion proof proves that a specific entry exists in a tree of data without revealing all other entries. Example: prove your balance appears in the state root without revealing anyone else's balances.

This uses keccak hashing, the same hash function as Ethereum. The proof is compact — typically a few kilobytes — and anyone can verify it in milliseconds.

### Balance Proofs

A balance proof proves your balance meets a threshold without revealing the actual amount. Example: prove you have at least 1000 tokens without saying whether you have 1000 or 1 million.

This uses a specialized circuit compiled from Circom (a zero-knowledge circuit language) and verified using PLONK, a modern proving system. These proofs are more computationally intensive to generate (a few seconds) but are extremely efficient to verify (milliseconds).

The hash function used here is Poseidon, a cryptographic hash function designed specifically for zero-knowledge circuits. It's roughly 100 times cheaper (in terms of circuit constraints) than traditional hashing, making proofs practical.

## Use Cases in TradeTower

* **Solvency verification** — Prove the DEX has enough assets to cover all user balances without revealing individual holdings or the exact reserves.
* **Governance eligibility** — Prove you meet a minimum token balance to vote on proposals without disclosing your holdings.
* **Privacy-preserving balance checks** — Verify your balance without broadcasting it to the network.
* **Collateral verification** — Prove you have sufficient collateral for lending without revealing your balance (Phase 7 feature, coming later).

## How to Use

{% stepper %}
{% step %}
### prove

Generate a zero-knowledge proof of your balance. Prompts for a token name, amount threshold, and your Discord ID. Outputs a JSON proof file that can be shared or stored.
{% endstep %}

{% step %}
### verifyproof

Verify a proof from a JSON file. This command runs entirely offline and requires no network connection. Outputs whether the proof is valid.
{% endstep %}
{% endstepper %}

Both commands are available in Discord and via the CLI.

## The Math (Simple Version)

A zero-knowledge circuit is a program that transforms your private inputs (your actual balance) into public outputs (proof that balance >= threshold) without ever revealing the inputs.

The PLONK proving system then cryptographically certifies that the circuit ran correctly without allowing the prover to cheat. Anyone can verify this certification, but they learn nothing about your actual balance.

This is possible because of polynomial arithmetic. The full mathematics involves finite fields and polynomial commitments, but the result is simple: a proof that's impossible to forge and impossible to trace back to your actual values.

## Privacy Roadmap

Zero-knowledge proofs are Phase 3b of TradeTower's decentralization plan:

* **Phase 1–3a**: Consensus (P2P mesh, state anchoring, conflict resolution)
* **Phase 3b**: Privacy (ZK balance proofs, private transactions)
* **Phase 4**: On-chain verification (optional, advanced)

Currently, TradeTower is completing Phases 1–3a. Privacy features are active but not required. You can use the DEX normally without generating proofs.

## Performance Notes

{% hint style="info" %}
* **Prove time**: 2–5 seconds on a modern CPU
* **Proof size**: ~400 bytes
* **Verify time**: < 100ms
* **Verification**: runs completely offline

The first time you generate a proof, the system initializes the WASM (WebAssembly) version of the Poseidon hash function, which adds 1–2 seconds to startup. Subsequent proofs are faster.
{% endhint %}

## Security

Proofs use industry-standard PLONK with 128-bit security (equivalent to hashing a 128-bit random value). The circuits are verified in Circom and compiled with SnarkJS, both widely used in production systems.

If a proof fails verification, the system rejects it. There's no middle ground — proofs either prove the statement or they don't.
