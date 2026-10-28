---
layout: page
title: "Log mileage and reimbursements with an AI assistant"
description: "how do I track mileage with Claude"
permalink: /mcp/guides/track-mileage-ai-assistant/
date: 2026-10-28
---

To track mileage from chat, connect an MCP mileage-log server: you state the trip in plain language, the server stores dated entries with distance and purpose, and the assistant totals them for a reimbursement claim or expense report.

## Procedure

1. Mint a token at https://mcp.zovo.one/mcp/connect.
2. Connect to `https://mcp.zovo.one/mcp/mileage-log/t/<token>`:

```json
{
  "mcpServers": {
    "mileage-log": {
      "url": "https://mcp.zovo.one/mcp/mileage-log/t/<token>"
    }
  }
}
```

3. Log a trip: "Add trip 2026-10-28, office to Northwind site and back, 46 miles, client visit."
4. Reconcile weekly: "List trips 20-26 October, total the miles, and flag any date with more than one entry."
5. For the claim, ask for a CSV export or hand the totals to the expense-tracker server; state the rate (for example 0.45 per mile) in the reimbursement request rather than letting the assistant assume one.

## When this does not work

- **Distance guesses.** The assistant may estimate a distance from map knowledge instead of your figure. Always state the miles in the request; if it invents one, delete the entry by id and re-add.
- **Return trips double-counted.** Decide a convention ("and back" means round trip in one entry) and use it every time, then spot-check one week's totals against your odometer.
- **Duplicate dates.** Multiple entries on one date are legitimate (several trips) but easy to duplicate; the weekly flag listing is the check.

## Note

The [mileage log MCP server](https://mcp.zovo.one) is hosted free at mcp.zovo.one (anonymous tier; Pro $19 single, $39 bundle). Related: expense-tracker, per-diem, hourly-rate.

## Verify the connection with curl

Before blaming the assistant, confirm the server answers a real call. Discovery alone is not proof — `initialize` and `tools/list` answer 200 even with a bad token, but this is the exact request shape to start from:

```bash
curl -s https://mcp.zovo.one/mcp/mileage-log/t/<token> \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

If this returns a tool list, the token and URL are good and any remaining problem is in the client's connector settings.

## What the server actually does

A mileage server stores trips with date, from, to, distance and purpose, and totals by date range or purpose. Business vs private use is a label you control; the tool cannot infer it, so include the purpose on every entry even when it feels obvious.
## Rates

Mileage rates change by tax year and by country, and the tool does not keep a rate table. Ask for raw distance totals and apply your own rate at claim time, printing the rate into the claim document. That keeps a rate change from silently repricing historical trips.

---

**The server that does this:** [Mileage Log](https://theluckystrike.github.io/mcp/mileage-log/) — 7 tools, free locally (MIT), $19 one-time for the hosted endpoint. [Read the server page](https://theluckystrike.github.io/mcp/mileage-log/) · [Buy the licence](https://mcp.zovo.one/buy/mileage-log).
