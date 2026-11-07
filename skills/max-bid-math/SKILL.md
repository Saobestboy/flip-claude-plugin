---
name: max-bid-math
description: Work out the most a reseller should pay or bid for an item or lot using Flip, after selling fees, buyer's premium, sales tax, shipping, packing or pickup, and target profit. Use when the user asks "what's my max bid", "how much can I pay", "is this lot worth it", gives an expected resale price for something at an estate sale, online estate auction, thrift store or garage sale, or wants to save a sourcing search or mark shortlisted items keep or let go against a budget.
---

# Max-bid math with Flip

Flip does cost math and keeps records. It does not find deals. Use only numbers the user gives you.

Tool names in this file are placeholders until the server is final: `calculate_max_bid`, `save_search`, `list_saved_searches`, `update_saved_search`, `record_item_decision`. If the connected Flip server names them differently, use its names.

## When to use which tool

- User wants a pay-up-to or max-bid price: call `calculate_max_bid`.
- User wants to save a search (keywords, budget, location radius, pickup or shipping): call `save_search`.
- User wants to change a saved search: call `list_saved_searches` if you need the ID, then `update_saved_search`.
- User says keep or let go on a shortlisted item: call `record_item_decision`, then report the budget left.

## Gather the inputs, one at a time

The max-bid tool needs seven numbers:

| Input | Symbol | Example |
|---|---|---|
| Expected sale price | P | $120 |
| Selling fee rate | f | 13% |
| Shipping cost | S | $15 |
| Packing or pickup cost | K | $2 |
| Target profit | T | $30 |
| Buyer's premium rate | b | 18% |
| Sales tax rate | t | 7% |

1. Pull every number the user already gave.
2. If one is missing, ask for that one only, in a short question. Wait for the answer. Then ask for the next missing one.
3. If the user says a cost does not apply (no premium at a garage sale, local pickup with no shipping), use 0.
4. Do not guess a rate. If the user asks you to "use the usual fee", ask what their fee rate is.
5. If the user does not know the sale price, ask for sold prices they found. Do not look prices up.

## The formula

Max bid = (P(1 − f) − S − K − T) / ((1 + b)(1 + t))

The tax is charged on the bid plus the premium, so both rates go in the bottom line.

If the top line is zero or less, say plainly that the item cannot reach the target profit at that sale price, and show the lines.

## Show the breakdown

Always show each cost line, then the result. Use this layout:

```
Sale price                    $120.00
Selling fees (13%)            −$15.60
Shipping                      −$15.00
Packing                        −$2.00
Target profit                 −$30.00
Left to spend, all-in          $57.40
÷ premium and tax (1.18 × 1.07 = 1.2626)
Pay up to                      $45.46
```

Then add one check line: "At $45.46 you pay $8.18 premium and $3.75 tax, $57.39 in all, which leaves about $30.01 profit."

End with: "Flip is an AI helper and can get things wrong, so check these numbers before you bid."

## Never do

- Never bid, buy, or say you placed a bid.
- Never post, list, or message a seller.
- Never scrape a website, open a link, or claim to search live auctions or sales.
- Never say Flip found a deal, or that a price is guaranteed.
- Never invent a sale price, fee, premium or tax rate.
- If the user asks for any of these, say Flip can't do it, then offer what it can do (for example, work out the pay-up-to price so they can bid themselves).
