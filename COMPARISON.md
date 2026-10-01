# Shopify versus the catalog

The shop was built twice: first as a Shopify store, then as a static catalog. This page compares the two against what the shop needs. Shopify is a good product; it solves a larger problem than this shop has.

## What the shop needs

- Every piece is handmade and one of a kind.
- Buyers message the owner on Instagram or Facebook to buy.
- Each piece should keep its details and photos online, including after it sells.
- The owner updates the shop from a phone.
- The running cost should be close to zero.

## Side by side

| | Shopify store | Catalog |
|---|---|---|
| What it is | A hosted online store | A static website with an admin page |
| Monthly cost | A subscription once the store goes live | None on the free tiers of GitHub and Cloudflare |
| Buying | Cart, checkout and payments | "Message on Instagram" and "Message on Facebook" buttons |
| Inventory | Stock counts per product | Not needed: a piece is Available, Sold or Hidden |
| A piece after it sells | Shown as sold out, as long as the owner keeps it listed | Stays by design, with a Sold badge, its photos and its description |
| Photos per piece | Many | As many as the owner adds |
| Missing price | A product needs a price; the imported ones without one showed as blank or zero | Shows "Message for price" |
| Adding a piece | Shopify admin or app | A form at `/admin/` in the phone's browser |
| Where content lives | Shopify's database | Text files and photos in a private Git repository |
| History and undo | Handled inside Shopify | Every save is a commit; any change can be reverted |
| Design | A theme in Liquid, Shopify's template language | Plain HTML and CSS built by Astro |
| Hosting | Shopify | Cloudflare Workers, rebuilt on every commit in about a minute |
| If the shop outgrows it | Already a store | Would need a checkout added, or a move to a store platform |

## What the Shopify build looked like

- Dawn, Shopify's stock theme, on a development store.
- 239 products imported from the shop's Instagram post history through the Admin API.
- A standard category on each product and five automatic collections.
- Prices found in Instagram captions for 79 products. The other 160 had none.

That last number is the comparison in miniature. A store wants a price on every product. The catalog treats a missing price as normal and shows "Message for price".

## What moved across, and what did not

- **Carried over:** the category list (Bracelets, Necklaces, Earrings, Rings, Jewelry Sets, Charms & Pendants, Beads & Strands) and the lesson about prices.
- **Left behind:** the imported products. The owner chose to start fresh and add pieces by hand through the admin.

## The trade-off

The catalog cannot take a payment. If the shop one day wants customers to pay on the site, this design is the wrong one and a store platform is the right one. For a seller of one-of-a-kind pieces who closes every sale in a chat, that is a trade worth making.

---

The source code and the shop's content are kept in a private repository. Back to the [README](README.md).
