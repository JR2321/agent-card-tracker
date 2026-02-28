# Agent Card Tracker - Scan Prompt

You are scanning for NEW products that give AI agents access to cards or payment capabilities.

## Steps

1. Read `agent-card-tracker/products.json` to see what's already tracked.
2. Search X/Twitter and the web for new products giving agents card access. Use queries like:
   - "agent card" OR "agent virtual card" OR "card for AI agents"
   - "agentic payments" new product launch
   - "agent wallet" card issuing
3. For any NEW product not in products.json:
   - Research it: website, X handle, description, funding, usage data
   - Add it to products.json
   - Update index.html with the new data
   - Send an email alert to csheffield02009@gmail.com using the Resend API (see send-email.mjs for pattern)
   - Post a summary to Discord channel 1477328591015641272
4. If nothing new found, reply HEARTBEAT_OK.

## Email format
Subject: "🃏 New Agent Card Product: [Name]"
Body: Product name, description, website, X link, funding, usage data, why it matters.
Signature: "Drafted by Cuy's OpenClaw Research Agent | github.com/openclaw/openclaw"

## What counts as "agent card access"
- Virtual cards issued to AI agents
- Payment infrastructure specifically for agent-initiated transactions
- Agent wallet products with card issuance
- Network-level agent payment protocols (Visa, MC, etc.)
- Checkout APIs that give agents card-like purchasing ability

Do NOT include: generic payment APIs, regular virtual card products not targeting agents, identity-only products without payment.
