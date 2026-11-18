---
name: publish-property-request
description: Publish a property request ("cerere") on La Cheie so agents and owners answer with matching listings. Use when the user wants to post what they are looking to buy or rent in Romania ("publică o cerere", "vreau să primesc oferte", "anunță că caut chirie"), or asks about the requests they already published.
---

# Publish a property request on La Cheie

A request is a public post on lacheie.ro saying what someone wants to buy or rent. Agents and owners reply with listings that match. Publishing a request is free.

## Before publishing

1. Collect what the request needs: buy or rent, kind of property (apartment, studio, house, land, commercial space), county and, if they have one, locality, maximum budget and currency. Ask only for what is missing. Rooms, minimum area and up to three short wishes are optional.
2. Draft a title (at most 80 characters) and a description in the user's language, using only what they told you. Do not add requirements they did not mention.
3. Show the user exactly what will be published: title, description, budget and place. Say that it becomes public on lacheie.ro under their account name, and wait for a clear yes. Change the draft if they ask.

## Publish

- Call `publish_request` only after that confirmation. The first time, Claude asks the user to sign in to their La Cheie account; the call continues by itself afterwards.
- The locality must be an exact name. If the tool reports an unknown or ambiguous place, show its suggestions and ask the user; do not guess.
- When it succeeds, give the user the request's `url` and tell them replies from agents and owners appear on that page. Do not promise that anyone will contact them or by when.
- If the result says `already_published`, the same request was sent a moment ago: give the existing link instead of trying again.

## Afterwards

- `list_my_requests` lists what the user has published and how many replies each has; `get_request` shows the replies and the listings attached to them.
- Editing or removing a request is done on lacheie.ro, from the user's profile.
- Listings of properties for sale or rent cannot be published through Claude. Owners publish them on lacheie.ro, from their account.
