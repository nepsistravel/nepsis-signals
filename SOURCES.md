# Sources: what this feed covers, and what is being added

The scanner itself lives in the private `nepsis-social` repo (`feeds/`). This
file is the shared record of what it reaches, so both the Nepsis and Contingent
sides can see the same picture.

## Counting rule
A number is only useful if it means something. We count a **source** as one
publisher we fetch from, not one URL and not one story. Where a single
publisher aggregates others, the aggregator counts as one and its constituents
are listed separately as **underlying authorities**, because that is what a
client actually wants to know: how many official bodies stand behind the feed.

## Down for want of a key (free to fix)
| Source | Secret to set | Where to get it |
|---|---|---|
| ReliefWeb | `RELIEFWEB_APPNAME` | Any identifying string, e.g. `contingentgroup` |
| URLhaus | `URLHAUS_KEY` | Free Auth-Key, abuse.ch account |
| Bluesky chatter | `BSKY_HANDLE`, `BSKY_APP_PASSWORD` | Created by hand in Bluesky settings |
| GDELT unrest and terrorism | none | Rate-limited on the shared runner: needs a longer retry window or its own schedule |

## Being added
| Source | Fills | Key | Notes |
|---|---|---|---|
| MeteoAlarm | Severe weather across Europe | `METEOALARM_UA` (contact string) | Aggregates 38 national meteorological and hydrological services. Confirm redistribution terms before going live. |
| NASA FIRMS | Wildfire outside the U.S. | `FIRMS_MAP_KEY` (free) | NIFC is U.S. only today. |
| Canada travel advisories | A third government's view | none | travel.gc.ca |
| Australia Smartraveller | A fourth government's view | none | Advisories that disagree are themselves a signal. |
| NOAA tsunami | Tsunami warnings | none | We have earthquakes but not tsunami. |
| NOAA SWPC | Space weather, GPS and HF disruption | none | Low volume, affects aviation. |

## Known holes, not yet scheduled
- **Ground transport and rail.** Nothing at all. Rail and metro strikes are the
  most common European trip disruptor.
- **Aviation beyond U.S. airport status.** No NOTAMs, no international airport
  disruption, no airline strikes. Most likely to need a paid feed.
- **Planned protests.** We see unrest after it is reported, never before.
  ACLED needs a licence.
- **Power and infrastructure outages.** Nothing.
- **Non-English sources.** We read English well and other languages poorly. A
  local-language warning may not reach us. Worth saying out loud rather than
  hiding.

## What stays on the Contingent side
Client-specific work never belongs in this repo: address-radius crime data,
sanctions and PEP screening, dark web monitoring and research, and anything
naming a client, a site or a person. This feed holds public data only, and the
flow to Contingent is one way.
