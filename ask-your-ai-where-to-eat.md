---
title: "Ask your AI where to eat: connecting an assistant to real restaurant data"
description: "Why chatbots give stale restaurant answers, what an MCP server is, and how to connect Claude, ChatGPT or Cursor to live Indian restaurant data."
---

# Ask your AI where to eat: connecting an assistant to real restaurant data

Ask a general chatbot for "a good masala dosa near HSR Layout that's open now" and you often get confident but stale answers: places that closed, prices from years ago, timings it cannot actually know. The model is guessing from its training data. The fix is to give the assistant a live data source it can query and cite.

## Why AI restaurant answers go stale

- Training data has a cut-off date; restaurants open, close and change menus constantly.
- Models rarely know opening hours, current prices or whether a place is pure veg.
- Without a source, the assistant cannot tell you where a fact came from.

## What an MCP server is, in plain words

The Model Context Protocol (MCP) is a standard way for an AI assistant to call outside tools. An MCP server is a web address that offers a set of tools, such as "search restaurants" or "get menu". When you add it to your assistant, the assistant can call those tools mid-conversation and answer from real data instead of memory.

## A free restaurant MCP server for India

IndiaRestros runs a free MCP server and REST API over the same data as its website. Reads need no key and no sign-up, and every answer says where each fact came from.

- **MCP server (Streamable HTTP):** `https://indiarestros.com/mcp`
- **Tools:** `search_restaurants`, `search_dishes`, `get_restaurant`, `get_menu`, `list_places`, `get_place`, `report_correction`, `about_dataset`
- **REST example:** `GET https://indiarestros.com/api/v1/restaurants?q=dosa&city=bengaluru`
- **Limits:** 120 requests a minute per IP without a key.

Restaurant records include name, kind, cuisines, address, phones, hours (with an `open_now` flag in IST), price band, cost for two, photos, a menu summary, sources and a permanent IRR- id. Menus include items with rupee prices and veg marks.

## Connecting your assistant

1. Open your assistant's settings for connectors, integrations or MCP servers (Claude, ChatGPT, Cursor and other MCP clients support remote servers).
2. Add a remote server with the URL `https://indiarestros.com/mcp`.
3. Start a new chat and ask a food question. The assistant should show that it is calling a tool such as `search_dishes`.

Full, current instructions are on the [IndiaRestros page for AI agents](https://indiarestros.com/for-agents).

## Prompts that work well

- "Find veg thali under ₹250 in Pune and show the restaurant links."
- "Which places in Bengaluru list masala dosa, and what's the typical price?"
- "Show me dhabas in Punjab with a menu on file."
- "Is this restaurant open now? Give me its phone number and the source."
- "Compare biryani prices at three places in Hyderabad."

Tip: ask the assistant to include the restaurant URL and the source for each fact. The IndiaRestros rules ask agents to cite both, which also lets you check the answer yourself.

## Freshness and corrections

No dataset is perfect. Before a long trip, call ahead to confirm timings. If you find something wrong, the `report_correction` tool sends a fix back to the dataset, so the next person gets a better answer.

## Good manners for builders

If you build an app on this data: cite sources, let users contact restaurants directly, do not resell contact details in bulk, and report errors. That keeps the service free and useful.

---
[Back to the IndiaRestros guide](./) · [Masala dosa in Bengaluru](masala-dosa-bengaluru.html)
