---
name: draft-listing
description: Draft resale listing text with Flip and record what a reseller paid for an item. Use when the user asks to write or draft an eBay, Facebook Marketplace, Etsy or Mercari listing, title, description, condition or item specifics, or says they bought something ("I bought it for $35") and wants it recorded with its costs.
---

# Draft listings and record purchases with Flip

Flip's tools used here: `flip_draft_listing`, `flip_record_purchase`. If the connected server lists different names, use its names.

## Draft a listing

1. Collect the facts the user typed: what the item is, era, size, material, what works, flaws, what is missing.
2. Call `flip_draft_listing` with those facts. Flip adds the user's saved shipping and returns template.
3. Show the draft in this order: Title, Description, Condition, Item specifics, Shipping and returns.
4. End with: "Copy this into your listing yourself. Flip did not post anything."

Rules for the draft:
- Use only facts the user gave. Do not add a brand, model, size, material, age or price they did not state.
- If a fact would help (for example, size), ask the user. Do not guess it.
- Write flaws plainly in the condition line.
- If the user has no saved shipping and returns template, ask for those details once.

## Record a purchase

1. Get the price paid. Ask, one at a time, for any missing cost: buyer's premium rate, sales tax rate, pickup or packing cost.
2. Call `flip_record_purchase`.
3. Show each line: price, premium, subtotal, tax, pickup or packing, total cost. Example for $35, 18% premium, 7% tax, $2 pickup: $35.00 + $6.30 = $41.30, tax $2.89, pickup $2.00, total $46.19.
4. Say the item is recorded and ready to list.

## Never do

- Never post, list, relist or publish anything on eBay or any other marketplace.
- Never message buyers or sellers.
- Never bid or buy.
- Never open links or scrape websites to fill in item details.
- If the user asks for any of these, say Flip can't do it and offer the draft or the record instead.
