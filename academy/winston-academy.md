# Winston Academy

Winston Academy is the learn-to-earn platform built into TradeTower. Learn about blockchain and crypto, earn WAC (Winston Academy Coin), redeem credits from the treasury.

## WiseGuy — Your AI Teacher

WiseGuy is an AI assistant powered by Claude (Anthropic) with deep, up-to-date knowledge of blockchain, cryptocurrency, DeFi, and the Winston ecosystem. WiseGuy is available 24/7 to help you understand the tech, answer questions, and suggest learning paths based on your progress.

## Features

### /ask — Ask Anything

Start a conversation with WiseGuy about any blockchain or crypto topic. Ask follow-up questions — WiseGuy remembers the last 30 minutes of conversation, so context carries forward.

Example:

* "What's an AMM?"
* "How does slippage work on Uniswap?"
* "Can I use an AMM for stable pair trading?"

Responses are personalized. If you've earned quiz points, taken the hourly quiz consistently, or reached a high rank, WiseGuy knows this and tailors responses to your experience level.

Rate limit: 3 questions per minute per user

### /fact — Random Knowledge

Get a curated blockchain fact from the Winston knowledge base. Facts cover blockchain history, DeFi mechanics, crypto economics, security best practices, and the Winston ecosystem.

Example facts:

* Bitcoin's genesis block was mined on January 3, 2009
* Constant-product AMMs maintain the invariant x * y = k to prevent arbitrage
* Merkle trees allow efficient verification of large datasets

### /quiz — Test Your Knowledge

Take a multiple-choice quiz to test what you've learned. Questions are shuffled at display time — answers are also randomized so you can't memorize order.

Scoring:

* 1 point per correct answer
* Streak counter — consecutive correct answers grant a 1.5x multiplier on the next point
* Leaderboard ranking based on total points
* Accuracy percentage tracked over time

No time limit. No penalties for wrong answers. Just learning.

### Hourly Quiz — Automatic Challenges

Every hour, TradeTower posts a fresh quiz question to a configured channel. Answer in the thread. Correct answers earn points and count toward your streak. Community leaderboard updates in real-time.

Optional — you can ignore it and just use /quiz on demand.

## WAC (Winston Academy Coin)

WAC is earned through participation:

* Completing quizzes
* Maintaining streaks
* Reaching accuracy milestones
* Asking high-value questions via /ask

WAC credits sit in your TradeTower account. Once you've earned enough, you can redeem them from the academy treasury: `/redeem <credits>`.

Redeemed credits convert to USDT or other tokens at current AMM rates. Treasury must have sufficient balance to honor redemptions — if it's depleted, redemptions may be queued.

## Knowledge Base

WiseGuy's knowledge comes from curated markdown files covering:

* **Winston Ecosystem** — Tokenomics, contracts, team, community, roadmap
* **TradeTower Platform** — DEX mechanics, bridge workflow, quiz system, governance
* **Blockchain Architecture** — Layer 2 commitments, Merkle trees, zero-knowledge proofs, P2P mesh concepts

New knowledge is added continuously. WiseGuy learns from the latest updates without requiring any code changes.

## Content Governance

Quiz questions and facts don't go live automatically. AI can make mistakes, so every new fact and quiz candidate goes through a review queue:

{% stepper %}
{% step %}
### AI generates quiz/fact candidates

The system produces candidate content (facts and quiz questions) using AI.
{% endstep %}

{% step %}
### Admins review and approve/reject the content

Human administrators review generated candidates and either approve or reject them.
{% endstep %}

{% step %}
### Community can also vote on pending content via governance proposals

Community members may participate in governance to vote on pending content.
{% endstep %}

{% step %}
### Once approved, content appears in rotation

Approved content is added to the active rotation of facts and quiz questions.
{% endstep %}
{% endstepper %}

This ensures quality and accuracy across the academy. If you spot an error in any fact or quiz, report it — content can be deprecated and replaced.

## Academy Funding

Winston Academy is funded by 20% of all swap fee revenue. The more trading happens on TradeTower, the more the academy treasury grows and the more credits you can earn and redeem.

This creates a positive loop: better education → better traders → more trading → more academy funding → more learning → healthier community.

## Mission

Winston Academy's mission is simple: make blockchain education accessible and rewarding. You shouldn't need a computer science degree to understand cryptocurrency. You shouldn't need to spend months reading whitepapers. Ask questions. Take quizzes. Learn at your own pace. Earn as you go.

## Commands

* `/ask <question>` — Ask WiseGuy anything about blockchain or crypto
* `/fact` — Get a random blockchain fact
* `/quiz` — Take a multiple-choice quiz
* `/redeem <amount>` — Redeem WAC credits from the treasury
* `/scores` — Check your quiz points, streak, and leaderboard rank

The academy is open to everyone. No signup required — just start asking questions.
