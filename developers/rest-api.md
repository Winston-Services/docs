# REST API

TradeTower offers a REST API for programmatic access to the DEX. Everything you can do in Discord, you can do via HTTP.

## Getting Started

{% stepper %}
{% step %}
### Set Environment Variables

```bash
export WEB_PORT=8080           # HTTP server port
export WEB_SECRET=your-secret  # JWT signing secret (auto-generated if absent)
```

Start the bot with these variables set. The HTTP server listens at `http://localhost:8080`.
{% endstep %}

{% step %}
### Authenticate

TradeTower supports two authentication methods:

**OAuth2** — Link your Discord account (or Telegram/Google, coming soon):

```bash
GET /oauth2/discord
# Redirects to Discord login, returns JWT token in query parameter
```

**API Key** — Get a persistent key for automated access:

```bash
POST /api/v1/auth/key
# Returns ttk_* formatted API key
```

Both methods return a JWT token or API key valid for 24 hours.
{% endstep %}

{% step %}
### Make Requests

Include your token in the Authorization header:

```bash
curl -H "Authorization: Bearer <jwt-token>" \
     http://localhost:8080/api/v1/command
```

Or use an API key:

```bash
curl -H "Authorization: Bearer ttk_your_api_key" \
     http://localhost:8080/api/v1/command
```
{% endstep %}
{% endstepper %}

## API Endpoints

### Generic Command Endpoint

```
POST /api/v1/command
Content-Type: application/json

{
  "command": "swap",
  "args": {
    "from": "USDT",
    "to": "ETH",
    "amount": "1000"
  }
}
```

**Response:**

```json
{
  "success": true,
  "reply": "Swapped 1000 USDT for 0.45 ETH",
  "embeds": [
    {
      "title": "Swap Executed",
      "description": "Your swap is complete",
      "color": 3066993,
      "fields": [...]
    }
  ]
}
```

All TradeTower commands route through this endpoint. No need to learn command-specific URLs.

### RESTful Convenience Routes

For common operations, dedicated HTTP verbs are available:

**Get DEX Status**

```
GET /api/v1/status
```

**Swap Tokens**

```
POST /api/v1/swap
Content-Type: application/json

{
  "from": "USDT",
  "to": "ETH",
  "amount": "1000"
}
```

**Check Balance**

```
GET /api/v1/balance/:token
```

**Get Pair Info**

```
GET /api/v1/pair/:token0/:token1
```

**Add Liquidity**

```
POST /api/v1/liquidity/add
Content-Type: application/json

{
  "token0": "USDT",
  "token1": "ETH",
  "amount0": "1000",
  "amount1": "0.5"
}
```

**Deposit (Bridge)**

```
POST /api/v1/deposit
Content-Type: application/json

{
  "chain": "ethereum",
  "token": "USDT",
  "amount": "1000"
}
```

**Withdraw (Bridge)**

```
POST /api/v1/withdraw
Content-Type: application/json

{
  "chain": "ethereum",
  "token": "USDT",
  "amount": "500",
  "address": "0x..."
}
```

Full endpoint documentation is available at `/api/v1/docs` (auto-generated).

## Multi-Provider Identity

One identity can be linked to multiple accounts:

**Link Discord:**

```
GET /oauth2/discord
```

**Link Telegram:** (coming soon)

```
GET /oauth2/telegram
```

**Link Google:** (coming soon)

```
GET /oauth2/google
```

When you link a new provider, it's merged with your existing TradeTower identity. Commands use whichever provider authenticated the request.

## Response Format

All API responses are JSON with a consistent structure:

```json
{
  "success": true|false,
  "reply": "Human-readable message",
  "embeds": [
    {
      "title": "...",
      "description": "...",
      "color": 3066993,
      "fields": [
        {
          "name": "Field Name",
          "value": "Field Value",
          "inline": true
        }
      ]
    }
  ],
  "error": "Error message (if success === false)"
}
```

Discord embeds are converted to JSON. Markdown formatting in embeds is preserved.

## Rate Limiting

* **Per-user**: 30 requests/minute (higher than Discord due to API overhead)
* **Global**: Adaptive based on node capacity

Responses include rate limit headers:

```
X-RateLimit-Limit: 30
X-RateLimit-Remaining: 28
X-RateLimit-Reset: 1646659200
```

## Examples

### Swap 1000 USDT for ETH

```bash
curl -X POST http://localhost:8080/api/v1/command \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "command": "swap",
    "args": {
      "from": "USDT",
      "to": "ETH",
      "amount": "1000"
    }
  }'
```

### Check Your Balance

```bash
curl -X GET "http://localhost:8080/api/v1/balance/ETH" \
  -H "Authorization: Bearer <token>"
```

### Deposit from Ethereum

```bash
curl -X POST http://localhost:8080/api/v1/deposit \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "chain": "ethereum",
    "token": "USDT",
    "amount": "1000"
  }'
```

Response includes your deposit address and confirmation requirements.

### Generate a ZK Proof

```bash
curl -X POST http://localhost:8080/api/v1/command \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "command": "prove",
    "args": {
      "token": "ETH",
      "amount": "10"
    }
  }'
```

Response includes the proof JSON that can be verified with `/api/v1/verifyproof`.

## Error Handling

Failed requests return HTTP 4xx or 5xx with JSON error detail:

```json
{
  "success": false,
  "error": "Insufficient balance: have 100 USDT, need 1000",
  "code": "INSUFFICIENT_BALANCE"
}
```

Common error codes:

* `INSUFFICIENT_BALANCE` — Not enough tokens
* `PAIR_NOT_FOUND` — Trading pair doesn't exist
* `INVALID_ADDRESS` — Malformed chain address
* `RATE_LIMITED` — Too many requests
* `UNAUTHORIZED` — Invalid or expired token

## WebSocket (Streaming)

Coming soon: WebSocket support for real-time balance updates, swap notifications, and order book streams.

```
WS ws://localhost:8080/api/v1/stream
```

## SDK

Clients are available for common languages:

* **JavaScript/Node.js** — https://github.com/winston-services/tradetower-js
* **Python** — https://github.com/winston-services/tradetower-py
* **Go** — https://github.com/winston-services/tradetower-go

Install via npm/pip/go get. Each SDK provides typed methods matching the API spec.

## Security Notes

* **Tokens expire** after 24 hours. Refresh via the auth endpoint.
* **HTTPS required** in production (not localhost for development).
* **API keys** should be stored securely (not in version control).
* **Tokens contain user ID** but no private keys or passwords.
* **Signatures verified** on every request (no token forgery possible).

## CORS

API accepts cross-origin requests from any origin (configurable via `WEB_ORIGIN` env var). Browser-based clients can call the API directly.

## Support

Full API docs: https://docs.winston.services/rest-api

Questions: Discord #developers

Issues: https://github.com/winston-services/tradetower/issues
