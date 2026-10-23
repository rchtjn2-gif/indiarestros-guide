---
title: "IndiaRestros MCP server and API quickstart"
---

This page explains how to connect AI assistants to [IndiaRestros](https://indiarestros.com/). Source and issues: [indiarestros-mcp-server on GitHub](https://github.com/rchtjn2-gif/indiarestros-mcp-server). Back to the [IndiaRestros guide](./).

<p align="center"><img src="logo.png" alt="IndiaRestros MCP server logo" width="120"></p>

# IndiaRestros MCP Server: every restaurant, menu and dish in India for AI agents

> Find restaurants, cafes, dhabas and street stalls anywhere in India, read menus with rupee prices, and search dishes across cities, from Claude, ChatGPT, Cursor or any MCP client. Free, no key.

**MCP endpoint:** `https://indiarestros.com/mcp` · **Transport:** Streamable HTTP · **Tools:** 14 · **Website:** [indiarestros.com](https://indiarestros.com)

This repository is the public listing for the **hosted** IndiaRestros MCP server: connection instructions, the registry manifest (`server.json`) and client config files. There is nothing to install or self-host; the server runs at the URL above.

## Connect in one step

Add this URL to any MCP client that supports remote servers:

```
https://indiarestros.com/mcp
```

Optional foodie tools (OAuth): `https://indiarestros.com/mcp/agent`

### Claude (claude.ai, Claude Desktop, Claude mobile)
Settings → Connectors → **Add custom connector** → paste the URL above → Connect.

### Claude Code
```bash
claude mcp add --transport http indiarestros https://indiarestros.com/mcp
```

### ChatGPT
Settings → Apps & Connectors → Advanced → enable Developer mode → **Create** a connector → paste the URL above.

### Cursor, Windsurf, Cline and other JSON-config clients
```json
{
  "mcpServers": {
    "indiarestros": {
      "url": "https://indiarestros.com/mcp"
    }
  }
}
```

### VS Code (GitHub Copilot)
Add to `.vscode/mcp.json`:
```json
{
  "servers": {
    "indiarestros": {
      "type": "http",
      "url": "https://indiarestros.com/mcp"
    }
  }
}
```

### Gemini CLI
```bash
gemini extensions install https://github.com/rchtjn2-gif/indiarestros-mcp-server
```

## Authentication
None for reads: connect and use it. Optional foodie tools (save places, log visits) live at `https://indiarestros.com/mcp/agent` and use OAuth.

## What data it covers
- **5,12,770 restaurants**, cafes, bakeries, sweet shops, bars, dhabas, food courts, cloud kitchens and street stalls in **8,911 cities and towns**
- Permanent ID per restaurant (IRR-…), address and map point, **phone numbers, timings and open-now in IST**, cuisines, cost for two, amenities
- **Menus with rupee prices and veg marks** where known, plus a catalog of canonical Indian dishes linked across menus
- **Dish search across every menu**: 'veg thali under ₹250 in Pune'
- States, cities and areas with counts by cuisine and kind
- Every fact carries its source and observed date; a published, payment-free ranking formula

## Tools (14)
| Group | Tools |
|---|---|
| Restaurants | `search_restaurants`, `get_restaurant`, `get_menu` |
| Dishes | `search_dishes` |
| Places | `list_places`, `get_place` |
| Data quality | `report_correction`, `about_dataset` |
| Foodie account (OAuth, /mcp/agent) | `whoami`, `set_handle`, `save_restaurant`, `list_saved`, `log_visit`, `my_timeline` |

## Example prompts
- "Find a pure-veg South Indian restaurant open now in Indiranagar, Bengaluru, and give me its phone number."
- "Where can I get paneer butter masala under ₹300 in Pune?"
- "Show me the menu and prices at this restaurant."
- "Best-rated biryani places in Kondapur, Hyderabad, with cost for two."
- "Which dhabas are on the Delhi–Jaipur highway near Neemrana?"

## Pricing
Free. Reads are free with no key and no sign-up (120 requests a minute per IP). No paid rankings, no commissions.

## FAQ
### Is there a free MCP server for Indian restaurants?
Yes. IndiaRestros runs a free hosted MCP server at https://indiarestros.com/mcp with no key and no sign-up, covering 5 lakh+ restaurants in 8,911 Indian cities and towns.

### Does it have menus and prices?
Yes, where known: menu sections and items with rupee prices and veg marks, and dish search across all menus.

### Are rankings paid?
No. The ranking formula is published and payment never counts.

### Can I use the data commercially?
Reads are free; cite the restaurant URL and the source. Do not resell contact details in bulk. See https://indiarestros.com/terms.

## Links
- [For AI agents](https://indiarestros.com/for-agents)
- [API reference](https://indiarestros.com/api/docs)
- [OpenAPI](https://indiarestros.com/openapi.json)
- [llms.txt](https://indiarestros.com/llms.txt)
- [Server card](https://indiarestros.com/.well-known/mcp.json)
- [How we rank (payment never counts)](https://indiarestros.com/ranking)
- [Data sources and licences](https://indiarestros.com/sources)
- [Privacy](https://indiarestros.com/privacy)
- [Terms](https://indiarestros.com/terms)

## About this repository
This repo holds listing and configuration files only. The IndiaRestros MCP server is a hosted service operated by IndiaRestros; its use is governed by the terms linked above. The files in this repository are released under the MIT licence.
