---
name: find-properties
description: Find apartments, houses, land or commercial space for sale or rent in Romania on La Cheie. Use when the user is looking for a place to buy or rent ("caut apartament în Cluj", "chirie 2 camere Brașov", "case de vânzare sub 150.000 €"), wants to compare listings or prices in a Romanian city, or shares a lacheie.ro link.
---

# Find properties on La Cheie

La Cheie (lacheie.ro) is a Romanian real-estate marketplace. The `lacheie` connector searches its live listings.

## Search

1. Work out what the user needs: buy or rent, kind of property, place, budget, number of rooms. If the place or whether they buy or rent is missing, ask one short question; search with what you have for everything else.
2. Call `search_offers`. Useful conventions:
   - `transaction_type`: `sale` to buy, `rent` to rent.
   - Romanian listings count rooms ("camere") with the living room included: "apartament cu 2 camere" is `rooms_min: 2, rooms_max: 2` and has one bedroom. A "garsonieră" is `property_category: "studio"`.
   - Pass place names as the user said them (`city: "Cluj-Napoca"`, `county: "Cluj"`); diacritics are optional. If the tool reports several localities with that name, ask the user which county or pick the suggested one.
   - Prices are in each listing's own currency, mostly EUR; rents are per month.
   - For "near" a place (a station, a university, a mall, a street), pass that place's coordinates as `near_latitude` and `near_longitude`, with `radius_km` (about 1 is a walk). Each listing then comes with its `distance_km`.
3. One or two searches usually answer a question. Narrow with filters and `limit` instead of reading page after page.
4. If nothing matches, say so and widen one filter at a time (neighbourhood, then price, then the whole county), telling the user what you changed.

## Present the results

- The user does not see search results. Call `show_offers` once per answer with the id of every listing your answer will point to (at most 12) and a short `heading` in the user's language. The user then sees cards with photos, prices and a map, and under them a link to the site's page for that kind of property and place.
- Choose before you show. If you will mention the closest listings and the cheapest ones, both groups go into the same call. Do not link in your text to a listing that is not among the cards: the user looks for it there.
- Once the cards are shown, do not repeat them as a list: say in a sentence or two why these fit and how the search could be narrowed. If the app shows no cards (a terminal), list each one with its price, place, size and `url` instead.
- `site_page` is the site's page for that kind of property and place. It lists everything of that kind there and does not apply the price, rooms or distance of your search, so present it as that page and not as "all results".
- Reply in the user's language.
- Photos and the advertiser's contact options are on each listing's page; the tools never return phone numbers, so never write one.
- Say how many listings matched in total.
- Call `get_offer` when the user asks about one listing in detail (description, floor, heating, facilities).
- Report only what the tools returned. Listings change daily: search again rather than reuse earlier results, and do not estimate availability.
- `plus_agency` only means the agency subscribes to La Cheie Plus. Do not present it as a quality rating, and do not rank listings by it.

## Related

- To show the user what buyers and tenants are asking for in an area, use `search_requests`.
- If the user wants agents and owners to come to them instead, offer to publish a request (the `publish-property-request` skill).
