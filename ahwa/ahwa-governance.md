# Ahwa Governance

AHWA is the governance token for the Winston ecosystem. AHWA holders can create and vote on proposals that change how TradeTower operates — from adjusting fees to approving new quiz content to directing funds to development.

## How Governance Works

AHWA is held on BSC (BNB Smart Chain). Your voting power equals your AHWA balance at the time the proposal is voted on. More AHWA = more voting power. It's direct democracy: one token, one vote.

## Three Types of Proposals

### Variable Proposals

Change platform settings. Examples:

* Adjust the swap fee from 3% to 2.5%
* Change the hourly quiz channel
* Increase withdrawal minimums for a specific chain
* Adjust L2 epoch inscription frequency

Variable proposals can modify settings across any agent in TradeTower — governance is flexible. However, certain critical keys are blacklisted and cannot be changed: version, startup flags, and infrastructure parameters.

### Disbursement Proposals

Move funds from revenue groups to service providers. The platform earns revenue from swap fees. A portion is allocated to development, marketing, asset management, and other operational costs.

Examples:

* Pay a developer team 50,000 USDT on Ethereum
* Send a marketing agency 10,000 USDC on BSC
* Allocate 30,000 USDT for ecosystem development to a multisig address on Tron

Disbursements are transparent and community-approved. You know exactly where platform revenue goes.

### Content Proposals

Approve new quiz questions and facts from the WiseGuy pending queue. As the AI-generated content goes through review, candidates sit in a pending queue.

Instead of admins unilaterally deciding, AHWA holders vote on content. This ensures the academy reflects community values and priorities.

## Voting Process

{% stepper %}
{% step %}
### Proposal Creation

Admins or node operators create a proposal (variable, disbursement, or content).
{% endstep %}

{% step %}
### Discussion Period

AHWA holders see the proposal and discuss it in the community.
{% endstep %}

{% step %}
### Voting

You sign a message with your BSC wallet containing your AHWA balance. TradeTower verifies the signature on-chain and counts your vote based on your balance.
{% endstep %}

{% step %}
### Auto-Tally

After the voting period ends, votes are counted automatically.
{% endstep %}

{% step %}
### Execution

If approved, the proposal executes immediately (variable settings update, funds transfer, content goes live).
{% endstep %}
{% endstepper %}

### Signing a Vote

You don't need to spend gas. Voting is gasless — you just sign a message with your wallet. Here's how:

{% stepper %}
{% step %}
### Run the vote command

Run `/vote <proposalId> <yes|no>` in Discord.
{% endstep %}

{% step %}
### Verify and sign

Verify the proposal details and sign with your BSC wallet.
{% endstep %}

{% step %}
### Verification

TradeTower verifies your signature and checks your AHWA balance on BSC.
{% endstep %}

{% step %}
### Recording

Your vote is recorded.

Your vote weight = your AHWA balance at the time you vote. If you hold 1000 AHWA, that's 1000 votes.
{% endstep %}
{% endstepper %}

## P2P Relay

The Winston network is decentralized across multiple nodes running the same TradeTower software. Proposals relay across the P2P mesh so all nodes stay in sync. Your vote is recorded locally and propagated to peers. Even if the Discord bot goes down, your governance state is preserved.

## Governable Parameters

Settable via variable proposals:

* Swap fees (3% default)
* Withdrawal fees and minimums per chain
* Quiz parameters (hourly quiz channel, scoring rules)
* L2 inscription frequency and costs
* Bridge deposit/withdrawal limits
* Academy Treasury balance and redemption rates
* Many more agent-specific settings

Settings that cannot be changed (blacklisted):

* Version and deployment metadata
* Startup flags (P2P, encryption, worker thread configs)
* Core infrastructure parameters

Blacklisting protects system integrity — you can't vote to disable security or storage, only adjust operational parameters.

## Voting Power

Voting power is your AHWA balance on BSC at the exact moment you vote. This is checked on-chain via `eth_call` (no gas spent). If you buy AHWA after a proposal is live, you gain voting power immediately. If you sell, voting power decreases.

There are no voting weight caps or delegation mechanisms at present. Direct holding = direct power.

## Proposal Timeline

{% stepper %}
{% step %}
### Created

Proposal goes live, discussion opens.
{% endstep %}

{% step %}
### Voting Open

AHWA holders vote (3-7 days typical).
{% endstep %}

{% step %}
### Voting Closed

Auto-tally runs.
{% endstep %}

{% step %}
### Passed or Rejected

Outcome is announced.
{% endstep %}

{% step %}
### Executed

If passed, changes take effect immediately.

Failed proposals can be revised and resubmitted. Governance is iterative — if the community rejects a 3% fee, someone can propose 2.8% instead.
{% endstep %}
{% endstepper %}

## Community Control

Through AHWA governance, the community controls:

* Platform economics (fees, rewards, incentives)
* Resource allocation (where platform revenue flows)
* Content standards (what facts and quizzes are approved)
* Feature prioritization (which improvements get funded)

You have a direct voice in how TradeTower evolves. Not through forums or requests to admins, but through on-chain votes that execute automatically.

## Commands

* `/propose <type> <details>` — Create a new proposal (admin/operator only)
* `/vote <proposalId> <yes|no>` — Vote on an active proposal (requires AHWA balance on BSC)
* `/proposals [active|passed|all]` — List proposals with current vote counts
* `/proposal <id>` — View details of a specific proposal

Governance is real. Your AHWA is your voice.
