# La Cheie

Search Romanian property listings and publish property requests on [La Cheie](https://lacheie.ro) from a conversation with Claude.

La Cheie is a real-estate marketplace for Romania: apartments, houses, land and commercial space for sale or rent, published by owners and agencies, plus public requests from people looking to buy or rent.

## What you can ask

- "Caut apartament cu 2 camere în Cluj-Napoca, sub 120.000 €." Claude searches the live listings and answers with prices, locations and a link to each listing.
- "Ce chirii sunt în Timișoara pentru o garsonieră?" Claude compares what is on the market right now.
- "Ce caută cumpărătorii în Brașov?" Claude shows the public requests in that area, useful if you have a property to offer.
- "Publică o cerere: caut casă de închiriat în Sibiu, buget 800 €." Claude drafts the request, shows it to you, and publishes it under your La Cheie account once you confirm.

Searching needs no account. Publishing a request asks you to sign in to La Cheie the first time; publishing a request is free.

## What it includes

- The **La Cheie connector** (`https://api.lacheie.ro/mcp`), with tools to search listings and requests, read one in detail, publish a request and list your own requests.
- Two skills that tell Claude how to use it: `find-properties` and `publish-property-request`.

## Data

The plugin itself stores nothing and runs no code on your device. Through the connector, Claude sends La Cheie the search filters it chooses (place, price range, property type) and, when you publish a request, the text and details of that request. Signing in happens on lacheie.ro; Claude never sees your password. A connection can be ended at any time from your La Cheie profile settings ("Aplicații conectate") or from Claude's connector settings.

Phone numbers and other contact details are not available through the connector: each result links to its page on lacheie.ro.

Privacy policy: https://lacheie.ro/politica-confidentialitate

## Support

secretariat.lacheie@gmail.com

Guide to using La Cheie with Claude: https://lacheie.ro/asistenti-ai
