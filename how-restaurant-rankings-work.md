---
title: "How IndiaRestros orders its restaurant lists (and why money is not in the formula)"
description: "The published ranking formula behind IndiaRestros lists, what each part means, and what owners can do to rank better."
---

# How IndiaRestros orders its restaurant lists

Most restaurant apps do not tell you why one place appears above another. Sponsored slots, commissions and opaque "relevance" scores all play a part. IndiaRestros takes the opposite approach: it publishes the formula, and **money is not part of it**. A restaurant cannot pay to move up, and paying for a future product will not change its position either.

## The formula

From the [IndiaRestros ranking page](https://indiarestros.com/ranking):

```
rank = 100 x ( 0.45 x confidence
             + 0.30 x completeness
             + 0.15 x (independent sources, up to 3) / 3
             + 0.10 x (has a phone number) )
```

So the maximum score is 100, and almost half of it comes from one thing: how sure the dataset is that the place exists as described.

## What each part means

### Confidence (45%)

How reliable the sources for a listing are and whether they agree with each other. A place seen in several sources with matching name, address and location scores higher than one that appears once with a vague pin.

### Completeness (30%)

How many basics are known: phone, website, timings, address, cuisine, pincode, menu and photos. A listing with all eight is more useful to a diner, and the formula rewards that directly.

### Independent sources (15%)

The number of separate sources that report the place, capped at three. Three agreeing sources earn the full 15 points; one source earns five.

### Phone number (10%)

A flat bonus for having a phone number on file, because a place you can call is a place you can actually confirm before you go.

## How search uses it

- A **word search** returns every place that contains all your words. Places whose name starts with your words come first, and each group is sorted by rank.
- A **search near a point** without words is sorted by distance, not rank.

## What is coming

Foodie ratings will be added to the formula once enough people rate places, and only ratings from people who were actually there will count.

## What owners can do

Because the formula is public, improving a listing is straightforward:

1. **Fill the gaps.** Add timings, a menu, photos, cuisine and a pincode. Each one raises completeness.
2. **Keep your phone number current.** It is worth a fixed 10 points on its own.
3. **Be consistent everywhere.** If your name and address match across your own website and other public listings, confidence goes up.
4. **Claim the page** so corrections are marked owner-verified.

## Where the data comes from

Every phone number, address, timing, menu and photo is recorded with its source and when it was last seen. The sources include Overture Maps, OpenStreetMap contributors, GeoNames, restaurants' own websites and owner submissions, listed on the [sources page](https://indiarestros.com/sources). The API and MCP server return the source with each fact, so an AI assistant can cite where an answer came from.

---
[Back to the IndiaRestros guide](./) · [Ask your AI where to eat](ask-your-ai-where-to-eat.html)
