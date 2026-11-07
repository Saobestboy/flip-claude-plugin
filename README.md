# Flip for Resellers

> Status: pre-launch. Flip's server and web pages at flip.roshi.world are not live yet, so this plugin won't connect until they are.

Flip for Resellers helps people who buy at estate sales, online estate auctions, thrift stores and garage sales, and resell on eBay, Facebook Marketplace, Etsy or Mercari.

Tell Claude what you expect an item to sell for. Flip works out the most you can pay for the lot after selling fees, buyer's premium, sales tax, shipping, packing or pickup, and your target profit. It shows every cost line so you can check the math.

Flip is an AI helper and can make mistakes. Check its numbers before you bid.

## What's in this plugin

- **Flip connector** (in `.claude-plugin/plugin.json`): connects Claude to Flip's remote server at `https://flip.roshi.world/mcp` (not live yet). You sign in to your Flip account with OAuth.
- **max-bid-math skill**: teaches Claude to work out a pay-up-to price, ask for missing costs one at a time, show the cost breakdown, save and edit searches, and record keep or let-go picks against a budget.
- **draft-listing skill**: teaches Claude to draft listing text from only the details you type plus your saved shipping and returns template, and to record purchases with their real costs.

## Use it

1. Add the plugin from the directory (or in Claude Code: install from this repo, https://github.com/Saobestboy/flip-claude-plugin), then connect Flip from the plugin's **Connectors** tab and sign in.
2. Ask, for example: "What's the most I can pay for a lamp I expect to sell for $120? Fees 13%, premium 18%, tax 7%, $15 shipping, $2 packing, $30 profit." Flip answers $45.46 and shows each line.
3. Ask Claude to save a search, mark items keep or let go, draft a listing, or record what you paid.
4. Copy any listing draft into eBay or another marketplace yourself.

## What Flip does not do

Flip never bids, buys, posts or lists items, or messages sellers. It does not search live auctions or sales, scrape websites, or open links. It uses only the numbers and sold prices you give it.

## Data

When you use Flip, Claude sends Flip's server only what each tool needs: the numbers you give for cost math, your saved search details (keywords, budget, the place you type, radius, pickup or shipping), item decisions, listing facts, and purchase costs. Flip stores your saved searches, decisions, listing drafts, seller template and purchases in your Flip account. The plugin itself has no scripts and stores nothing on your computer. It sends nothing to any other service.

## Privacy Policy

Flip's privacy policy is at https://flip.roshi.world/privacy (goes live before launch).

It covers what data Flip collects, how it is used and stored, who it is shared with, how long it is kept, how to delete it, and how to contact us. Questions: see the support page.

## Support

https://flip.roshi.world/support (goes live before launch)

## Check the plugin before submitting

From this folder, run:

```bash
claude plugin validate .
```

It prints `✔ Validation passed` when the files are well formed. Then select **Validate** in the developer portal at claude.ai/directory/manage, which runs more checks (README, license, name). Docs: https://claude.com/docs/plugins/pre-submission-checklist.md

To try it locally in Claude Code: `claude --plugin-dir .`

## License

MIT. See LICENSE.
