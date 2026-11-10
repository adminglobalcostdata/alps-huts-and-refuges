# Alpine Huts & Refuges: DE AT CH FR (OSM)

> Search about 2,400 mountain huts and refuges in Germany, Austria, Switzerland and France from OpenStreetMap: coordinates, elevation, beds, winter room, water, food, reservation.

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-1f6feb)](https://apify.com/phonic_lily/alps-huts-and-refuges) ![Licence](https://img.shields.io/badge/licence-ODbL_1.0_-blue) ![Records](https://img.shields.io/badge/records-2%2C412-green)

Search about 2,400 mountain huts and refuges in Germany, Austria, Switzerland and France from OpenStreetMap: coordinates, elevation, beds, winter room, water, food, reservation. Embedded data, no scraping, pay per record.

## What you get
- **2,412 records**, each carrying its own `license` and `attribution` fields, ready to republish with the required credit.
- A **100-record free sample** in this repository: [`sample.jsonl`](sample.jsonl) and [`sample.csv`](sample.csv) (opens as a table on GitHub).
- The **full dataset** as a filterable API (JSON, CSV, Excel), no scraping, no login: [Alpine Huts & Refuges: DE AT CH FR (OSM) on Apify](https://apify.com/phonic_lily/alps-huts-and-refuges).

## One record
```json
{
  "id": "n316985701",
  "name": "Britanniahütte",
  "lat": 46.06006,
  "lon": 7.93502,
  "country": "CH",
  "elevation_m": 3030,
  "capacity": 101,
  "capacity_winter_room": 10,
  "website": "https://www.britannia.ch/",
  "reservation": null,
  "opening_hours": null,
  "drinking_water": "yes"
}
```

## Quick start
Python:
```python
from apify_client import ApifyClient
client = ApifyClient('<YOUR_APIFY_TOKEN>')
run = client.actor('phonic_lily/alps-huts-and-refuges').call(run_input={'maxResults': 10})
for item in client.dataset(run['defaultDatasetId']).iterate_items():
    print(item)
```
Or from the command line:
```bash
curl -X POST 'https://api.apify.com/v2/acts/phonic_lily~alps-huts-and-refuges/run-sync-get-dataset-items?token=<YOUR_APIFY_TOKEN>' \
  -H 'Content-Type: application/json' -d '{"maxResults": 10}'
```
Pricing is pay-per-record on Apify (see the Actor page); the sample here is free.

## Fields
| Field | Description |
|---|---|
| `id` | OpenStreetMap element id (n=node, w=way, r=relation) or slug; unique within kind. |
| `name` | Name as tagged in OpenStreetMap. |
| `lat` | Latitude, decimal degrees. |
| `lon` | Longitude, decimal degrees. |
| `country` | ISO country code when the source gives it (DE, AT, CH, BE); null for records from the French source sites, which carry no country field. |
| `elevation_m` | Elevation in metres as tagged in OSM, null if untagged. |
| `capacity` | Number of beds (OSM capacity tag). |
| `capacity_winter_room` | Beds in the winter room. |
| `website` | Website of the object or its organisation. |
| `reservation` | Reservation tag. |
| `opening_hours` | OSM opening_hours tag (free text). |
| `drinking_water` | Drinking water tag. |
| `food` | Food tag. |
| `cuisine` | Cuisine tag. |
| `internet_access` | Internet access tag. |
| `shower` | Shower tag. |
| `wheelchair` | Wheelchair tag. |
| `outdoor_seating` | Outdoor seating tag. |
| `winter_room` | Winter room tag. |
| `power_supply` | Power supply tag. |
| `built_year` | Year built (tag). |
| `wikidata` | Wikidata QID. |
| `wikipedia` | Wikipedia article tag (lang:title). |
| `alt_name` | Alternative name. |
| `commons` | Wikimedia Commons reference. |
| `refuges_info_id` | Id of the same hut on Refuges.info (link only; Refuges.info data are in a separate Actor). |
| `local_relief_m` | Local relief within about 2 km in metres (computed by atlas-montagne from a DEM). |
| `source_sites` | Source site(s) of the record, joined with +. |

## Data, licence and attribution
Extracted from OpenStreetMap (Overpass), licence ODbL 1.0, (c) OpenStreetMap contributors. This dataset is a derived database (Derivative Database under the ODbL): if you publish it or a database derived from it, you must credit OpenStreetMap and share it under ODbL 1.0. Personal data (phone numbers, e-mail addresses, operator names, memorial inscriptions) were removed. Null means the source gives no value; it is never 0. Coverage depends on the source sites: alpen-atlas = Germany, Austria, Switzerland; atlas-montagne and resurgence-atlas = France (including overseas), resurgence-atlas also a Belgium/Switzerland extension. Where the same OSM element appears in two source sites, fields are merged (first non-null wins, alpen-atlas first) and source_sites lists both. Phone numbers, e-mail addresses and operator names of huts were removed on purpose.

**Licence:** ODbL 1.0 ; (c) OpenStreetMap contributors

**Attribution:** Contains data from OpenStreetMap, (c) OpenStreetMap contributors, ODbL 1.0 (https://www.openstreetmap.org/copyright). This dataset is a derived database and must be shared under ODbL 1.0 when redistributed.

Share-alike: this sample is a derivative database. It stays under the licence above (ODbL 1.0 ; (c) OpenStreetMap contributors); any adapted copy must keep the same terms and credit the source.

Snapshot date: 2026-11. Empty values are `null`, never 0.

## Cite this dataset
GitHub's *Cite this repository* button reads [`CITATION.cff`](CITATION.cff).

## Related
Rankings of French mountain peaks, passes, climbing and via ferrata routes are browsable on [Arete Atlas (arete-atlas.com)](https://arete-atlas.com/).

## Feedback
Found an error or want a field added? Open an issue in this repository.
