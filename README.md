# Nepsis signals

Public-source travel and security signals gathered by Nepsis Travel: official advisories, embassy alerts,
severe weather, earthquakes, storms, wildfires, terrorism advisories, plus unverified news and social leads.

- Feed: `data` branch → `signals.json` (rolling 7 days; cyber 30 days) and `health.json` (per-source status).
- Each signal: title, link, source, tier (Official / Lead / Chatter), topic, published, country, lat/lon when known.
- Lead and Chatter items are pointers to check, never confirmed facts.
- No personal or client data is ever stored here.
