# 🃏 Agent Card Tracker

**Track every product giving AI agents access to cards and payment infrastructure.**

The agent card space is exploding. New startups, network launches, and infrastructure plays ship weekly. This tracker monitors the landscape so you don't miss what matters.

## Quick Start

Open the dashboard:

```bash
# Clone and open locally
git clone https://github.com/JR2321/agent-card-tracker.git
open agent-card-tracker/index.html
```

That's it. No build step, no dependencies, no server. One HTML file with everything embedded.

## What's Tracked

Every product is categorized and includes:

| Field | Description |
|-------|-------------|
| `name` | Product name |
| `description` | What it does, how it works |
| `website` | Product URL |
| `twitter` | X/Twitter account |
| `category` | Agent Card Issuer, Network/Platform, Identity, etc. |
| `status` | Live, Beta, Pilot |
| `funding` | Known funding rounds and investors |
| `usage_data` | Waitlist size, transaction counts, partnerships |
| `notes` | Analysis and competitive context |

## Current Landscape (9 products)

**Agent Card Issuers** (direct card access for agents):
- **CreditClaw** — Self-hosted cards with spending controls. 14K waitlist.
- **Proxy** — Dedicated virtual card per agent/workflow. MCP integration.
- **Crossmint** — Full stack: virtual cards, stablecoin wallets, checkout API.

**Infrastructure / Identity:**
- **Skyfire** — KYA (Know Your Agent) protocol + wallets. a16z backed.
- **Nekuda** — Mandate model for agent checkout. $5M from Visa Ventures.
- **PayOS** — Network-issued Agent Tokens. First live MC transaction.
- **Prava** — Multi-agent prepaid wallets. Visa Intelligent Commerce partner.

**Network Platforms:**
- **Visa Intelligent Commerce** — TAP protocol, network tokenization.
- **Mastercard Agent Pay** — Live for all US cardholders.

## Data Format

Products live in `products.json`. Each entry:

```json
{
  "id": "proxy",
  "name": "Proxy",
  "description": "Virtual cards and payment infrastructure for AI agents...",
  "website": "https://www.useproxy.ai",
  "twitter": "https://x.com/useproxy_ai",
  "category": "Agent Card Issuer",
  "status": "Live",
  "funding": null,
  "usage_data": null,
  "added": "2026-02-28",
  "notes": "Published comprehensive agent payments landscape report."
}
```

## Add a Product

1. Add an entry to `products.json`
2. The dashboard (`index.html`) reads from an embedded copy of the data, so update the `products` array in the `<script>` tag as well
3. Submit a PR

### What qualifies?

**Include:**
- Virtual cards issued to AI agents
- Payment infrastructure for agent-initiated transactions
- Agent wallet products with card issuance
- Network-level agent payment protocols
- Checkout APIs giving agents card-like purchasing ability

**Exclude:**
- Generic payment APIs not targeting agents
- Regular virtual card products
- Identity-only products without payment capability

## Automated Monitoring

This tracker is monitored by an AI agent (JR) that scans X/Twitter and the web every ~12 hours for new products. When a new product is found:

1. Added to `products.json` and the dashboard
2. Email alert sent with product summary
3. Update posted to Discord

See `SCAN_PROMPT.md` for the full scanning methodology.

## Project Structure

```
agent-card-tracker/
├── README.md          # You're here
├── index.html         # Interactive dashboard (standalone, no deps)
├── products.json      # Structured product data
└── SCAN_PROMPT.md     # Instructions for automated scanning
```

## Dashboard Features

- **Dark theme** with category-based filtering
- **Status badges**: Live (green), Beta (yellow), Pilot (purple)
- **Product cards** with website links, X accounts, funding, usage data
- **Responsive** layout (works on mobile)
- **Zero dependencies** — single HTML file, opens anywhere

## License

MIT

## Contributing

PRs welcome. If you know of a product giving agents card access that isn't listed, open an issue or submit a PR adding it to `products.json`.
