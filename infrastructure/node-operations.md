# Node Operations

TradeTower is designed to run as a decentralized network of independent nodes connected via a P2P WebSocket mesh. Anyone can run a node and help secure the network.

## What a Node Does

A TradeTower node:

* Maintains a full copy of the trading state (token balances, liquidity pools, user deposits)
* Processes incoming transactions (swaps, deposits, withdrawals)
* Validates state consistency with peer nodes
* Anchors state epochs to the Pepecoin blockchain for immutable verification
* Relays transactions and state updates across the mesh to other nodes
* Earns revenue from the trading fees it helps collect

Nodes do not need to stake tokens or compete in consensus. Instead, they earn by being honest: maintaining uptime, validating correctly, and participating in epoch commitments.

## Deployment Tiers

TradeTower uses a single Docker image, with environment variables controlling which features activate:

### Headless (Minimal)

No `DISCORD_TOKEN` or `ENCRYPTION_KEY`. Runs the DEX engine and operator console only.

* Use case: Testing, backend infrastructure, automated traders

### Lite

Add `DISCORD_TOKEN`. Enables Discord bot with commands, WiseGuy AI education features, and quizzes.

* Use case: Community-run Discord bot

### Lite + REST

Add `WEB_PORT` and `WEB_SECRET`. Enables HTTP REST API for programmatic access.

* Use case: Web integrations, third-party apps, automated trading via API

### Bridge

Add `ENCRYPTION_KEY`. Unlocks the custodial wallet bridge, allowing users to deposit and withdraw from real blockchains.

* Use case: Full node with on-chain connectivity

### Full

Add `P2P_BOOTSTRAP` and `P2P_PORT`. Activates the P2P WebSocket mesh, state sync, and epoch commitment to Pepecoin.

* Use case: Decentralized network node, revenue generation

Start at whichever tier matches your goals. Add capabilities incrementally as infrastructure matures.

## P2P Mesh Network

Nodes connect to each other via WebSocket, forming a mesh where each node talks to multiple peers. Messages are signed with ed25519 keys (derived from the encrypted mnemonic) to prevent forgery.

Heartbeats broadcast every 30 seconds, including the node's ID, current epoch, and treasury balance. This allows peer discovery and liveness tracking.

## Conflict Resolution

In a distributed system, nodes sometimes disagree. When that happens, TradeTower uses a deterministic tiebreaker chain:

1. **Epoch number** — The node with the higher epoch is correct
2. **Consecutive epochs** — If tied, the node with a longer streak is correct
3. **Treasury balance** — If still tied, the node with higher balance is correct
4. **Node ID** — If all else fails, lexicographic comparison of node IDs

Both nodes see the same peer broadcast values, so both compute the same conclusion. No voting required. No randomness. Just math.

If a node diverges 3 times in a row, it gets temporarily excluded from payouts and asked to re-sync. After re-sync, it gets a 2-epoch grace period before challenges resume.

## Code Integrity

Every epoch, nodes challenge each other with file hash verifications. A random file from the codebase (deterministically selected based on epoch number and node ID) is hashed and compared across peers.

The goal: detect code corruption or malicious modifications. Nodes that fail integrity checks accumulate strikes:

* 0–1 failures: forgiven (1.0x payout multiplier)
* 2 failures: multiplier becomes 0.67x
* 3+ failures: excluded from payouts (0.0x multiplier)

After reconnecting to the mesh, a node gets a 2-epoch grace period before new challenges begin. This prevents false exclusions during temporary network issues.

## Node Payout Eligibility (NodeScorecard)

Nodes earn from the Revenue Generation pool (7.8% of gross swap fees) only if they meet eligibility criteria:

**Required:**

* At least 90% uptime (heartbeats received / expected)
* At least 3 consecutive epochs committed
* Code integrity multiplier > 0 (not excluded)

**Payout calculation:**

* Base score = uptime% × code integrity multiplier
* Node payout share = base score / sum of all eligible nodes' scores × revenue pool

High-uptime nodes earn more. Nodes with integrity strikes earn less. Excluded nodes earn nothing until they sync and re-establish trust.

Scorecard resets every payout period (typically daily). Historical records are stored in LevelDB for auditing.

## Deployment

### Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/winston-services/tradetower.git
cd tradetower

# 2. Set environment variables
export DISCORD_TOKEN=your_token_here
export ENCRYPTION_KEY=your_hex_key_here
export P2P_BOOTSTRAP=ws://node1:9000,ws://node2:9000
export P2P_PORT=9000

# 3. Run with Docker
docker compose up -d
```

### First Boot (Bridge Node)

{% stepper %}
{% step %}
### Generate mnemonic

The system generates a new BIP39 mnemonic.
{% endstep %}

{% step %}
### Encrypt mnemonic

Encrypts it with AES-256-GCM.
{% endstep %}

{% step %}
### Print encryption key

Prints the encryption key to the console (capture this!).
{% endstep %}

{% step %}
### Generate custodial wallets

Generates custodial wallets on all configured blockchains.
{% endstep %}

{% step %}
### Print Pepecoin address

Prints the Pepecoin deposit address (fund this to pay for epoch commits).
{% endstep %}
{% endstepper %}

Save the encryption key in a secure location. It's needed for every subsequent boot.

### Environment Variables

**Required for tier:**

* `DISCORD_TOKEN` — Discord bot token (Lite+)
* `ENCRYPTION_KEY` — Hex key for mnemonic decryption (Bridge+)
* `P2P_BOOTSTRAP` — Comma-separated bootstrap node URLs (Full)
* `P2P_PORT` — WebSocket listen port, default 9000 (Full)
* `WEB_PORT` — HTTP server port (REST API)

**Optional:**

* `ANTHROPIC_API_KEY` — For WiseGuy AI features
* `RPC_ETH`, `RPC_BSC`, etc. — Custom RPC endpoints for chains
* `STORE_BACKEND` — `leveldb` (default) or `postgres` for state storage

### Resource Requirements

* **CPU**: 1–4 cores (depends on tier and trading volume)
* **RAM**: 512MB (Headless) to 2GB (Full with all features)
* **Disk**: 10GB for LevelDB state + circuit artifacts
* **Network**: 100Mbps+ sufficient, typical bandwidth ~1–10Mbps

## Monitoring

Use the `chainstatus` admin command (Discord or operator console) to check:

* WebSocket connection health per blockchain
* HTTP fallback polling status
* Last block verified per chain
* Last P2P heartbeat and peer count

The `integrity` command shows code integrity challenge status per connected peer.

## Rewards

Node operators earn from three sources:

1. **Revenue Generation pool** (7.8% of swap fees) — Proportional to eligibility score
2. **Code integrity challenges** (bonus multiplier) — Honest nodes get higher payouts
3. **Epoch participation** (streak bonus) — Nodes maintaining long uptime streaks earn more

A well-maintained node running continuously can expect steady rewards from trading volume.

## Support

Documentation: https://docs.winston.services

Node operator issues: Discord #node-operators

GitHub: https://github.com/winston-services/tradetower
