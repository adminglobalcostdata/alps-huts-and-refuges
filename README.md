# Alpine Huts & Refuges: DE AT CH FR (OSM)

Search about 2,400 mountain huts and refuges in Germany, Austria, Switzerland and France from OpenStreetMap: coordinates, elevation, beds, winter room, water, food, reservation. Embedded data, no scraping, pay per record.

This repository holds a **100-record sample** of the dataset (`sample.jsonl`) and its schema. The full dataset (2412 records), searchable with filters and returned as JSON/CSV/Excel through the Apify API, is the Actor: **[Alpine Huts & Refuges: DE AT CH FR (OSM)](https://apify.com/phonic_lily/alps-huts-and-refuges)**

## Fields
- `id` : OpenStreetMap element id (n=node, w=way, r=relation) or slug; unique within kind.
- `name` : Name as tagged in OpenStreetMap.
- `lat` : Latitude, decimal degrees.
- `lon` : Longitude, decimal degrees.
- `country` : ISO country code when the source gives it (DE, AT, CH, BE); null for records from the French source sites, which carry no country field.
- `elevation_m` : Elevation in metres as tagged in OSM, null if untagged.
- `capacity` : Number of beds (OSM capacity tag).
- `capacity_winter_room` : Beds in the winter room.
- `website` : Website of the object or its organisation.
- `reservation` : Reservation tag.
- `opening_hours` : OSM opening_hours tag (free text).
- `drinking_water` : Drinking water tag.
- `food` : Food tag.
- `cuisine` : Cuisine tag.
- `internet_access` : Internet access tag.
- `shower` : Shower tag.
- `wheelchair` : Wheelchair tag.
- `outdoor_seating` : Outdoor seating tag.
- `winter_room` : Winter room tag.
- `power_supply` : Power supply tag.
- `built_year` : Year built (tag).
- `wikidata` : Wikidata QID.
- `wikipedia` : Wikipedia article tag (lang:title).
- `alt_name` : Alternative name.
- `commons` : Wikimedia Commons reference.
- `refuges_info_id` : Id of the same hut on Refuges.info (link only; Refuges.info data are in a separate Actor).
- `local_relief_m` : Local relief within about 2 km in metres (computed by atlas-montagne from a DEM).
- `source_sites` : Source site(s) of the record, joined with +.

## Data and licence
Extracted from OpenStreetMap (Overpass), licence ODbL 1.0, (c) OpenStreetMap contributors. This dataset is a derived database (Derivative Database under the ODbL): if you publish it or a database derived from it, you must credit OpenStreetMap and share it under ODbL 1.0. Personal data (phone numbers, e-mail addresses, operator names, memorial inscriptions) were removed. Null means the source gives no value; it is never 0. Coverage depends on the source sites: alpen-atlas = Germany, Austria, Switzerland; atlas-montagne and resurgence-atlas = France (including overseas), resurgence-atlas also a Belgium/Switzerland extension. Where the same OSM element appears in two source sites, fields are merged (first non-null wins, alpen-atlas first) and source_sites lists both. Phone numbers, e-mail addresses and operator names of huts were removed on purpose.

Licence: ODbL 1.0 ; (c) OpenStreetMap contributors

Attribution: Contains data from OpenStreetMap, (c) OpenStreetMap contributors, ODbL 1.0 (https://www.openstreetmap.org/copyright). This dataset is a derived database and must be shared under ODbL 1.0 when redistributed.

Snapshot date: 2026-11. Empty values are `null`, never 0.
## Related
Rankings of French mountain peaks, passes, climbing and via ferrata routes are browsable on [Arete Atlas (arete-atlas.com)](https://arete-atlas.com/).
