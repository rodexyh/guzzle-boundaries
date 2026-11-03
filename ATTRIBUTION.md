# Attribution

Every city in this repository and where its boundaries come from (the table first),
then every source whose data is in this repository, one section each.

This file is generated: a section appears here **if and only if** that source's data
is actually in one of the packs. A source that is not shipped does not get a
paragraph, and a source that is shipped cannot be missing one — the generator
refuses to write this file if it finds data it has no attribution text for.

## Every city and its source

One row per city in this repository (the bundled pack and every province pack). *Source* links to that source's attribution below; *Publisher* and *Licence* are the two attribution cells stored in the pack itself (— where the pack predates them).

| City | Pack | Publisher | Licence | Source |
|---|---|---|---|---|
| Airdrie | bundled | — | — | [City of Airdrie](#city-of-airdrie) |
| Calgary | bundled | — | — | [City of Calgary](#city-of-calgary) |
| London | bundled | — | — | [City of London, Ontario](#city-of-london-ontario) |
| Edmonton | ca-ab | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Burnaby | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Richmond | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Saanich | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Surrey | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Vancouver | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Victoria | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Winnipeg | ca-mb | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Hamilton | ca-on | City of Hamilton | City of Hamilton Open Data Licence (Version 1.1) | [City of Hamilton](#city-of-hamilton) |
| Kitchener | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Oshawa | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Ottawa | ca-on | City of Ottawa (Ottawa Neighbourhood Study) | Open Government Licence – City of Ottawa | [City of Ottawa](#city-of-ottawa) |
| Toronto | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Windsor | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Laval | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Lévis | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Montréal | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Québec | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |

## OpenStreetMap

© OpenStreetMap contributors. Data available under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/) —
see <https://www.openstreetmap.org/copyright>.

The cities in the per-province packs in `packs/regions/` whose `licenceKey` is `osm`
are derived from OpenStreetMap administrative relations (the `admin_level` that
carries a city's neighbourhoods, which differs by city and is confirmed by hand for
each one). That data is a derived database and is distributed under the ODbL;
`LICENSE` in this repository is that licence. A province pack can also hold cities
from a municipality's own open data (their `licenceKey` names the publisher); those
rows keep their publisher's licence, set out in that publisher's section below, and
the ODbL does not apply to them.

The place-name tiles in `packs/regions/<code>-names/` are derived from named
OpenStreetMap features (towns, lakes, parks, mountains and the like) and are part of
the same ODbL database. Where a feature carries a Wikidata ID, the ID is stored with
it (Wikidata is CC0).

The Guzzle app shows this as: *"Neighbourhood boundaries © OpenStreetMap
contributors, available under the Open Database License."*

## Wikimedia Commons photos

Some place-name tiles carry a photo for a place, in their `place_photos` table.
Every photo comes from [Wikimedia Commons](https://commons.wikimedia.org) and is used
under **its own licence** — public domain, CC0, CC BY or CC BY-SA, in whichever
version its Commons page states. **These photos are not covered by the ODbL**, and
redistributing one means following the licence recorded next to it.

Each photo's row records what its licence asks for: the author (`author`), the
licence and its URL (`license`, `licenseUrl`), the Commons file page it came from
(`source`), and what was changed from the original (`changes` — for example
scaled down and converted to HEIC). `credit` is the line the app shows with the photo.

## Place introductions

Some place-name tiles carry a short introduction for a place, in their
`place_intros` table. These were written for the Guzzle app in its own words; they
are not copied from Wikipedia or any other source. The facts in them were checked
against public references (Wikipedia, Wikidata, official sites) before they were
included.

## City of Hamilton

Contains public sector Data made available under the City of Hamilton’s Open Data Licence.

Neighbourhood (planning unit) boundaries and the city limit come from Open Hamilton,
<https://open.hamilton.ca> (service URLs in `manifest/cities.json`). Seven rural
planning units whose source names are numbers are shown under the name of the
community they belong to (Flamborough, Glanbrook), and two names cut short at 20
characters in the source are shown in full (`renames` in `manifest/cities.json`).

**Licence:** City of Hamilton Open Data Licence, Version 1.1,
<https://www.hamilton.ca/city-council/data-maps/open-data/open-data-licence-terms-and-conditions>.
This data is governed by that licence, **not** by the ODbL.

## City of Ottawa

Contains information licensed under the Open Government Licence – City of Ottawa.

Neighbourhood boundaries come from the **Ottawa Neighbourhood Study (ONS)**
neighbourhood boundaries (Gen 3), published by the City of Ottawa on
<https://open.ottawa.ca>; the city limit used to check coverage comes from the City
of Ottawa's public map services. Service URLs are in `manifest/cities.json`.
The source data stores neighbourhood names in capitals; they are shown in mixed
case with apostrophes and accents, following the Ottawa Neighbourhood Study's own
spelling where its website lists the same neighbourhood (`renames` in
`manifest/cities.json` lists every name as changed).

**Licence:** Open Data Licence Version 2.0 (Open Government Licence – City of Ottawa),
<https://open.ottawa.ca/pages/open-data-licence>.
This data is governed by that licence, **not** by the ODbL.

## City of Airdrie

Contains information provided by the **City of Airdrie GIS** department.

Neighbourhood boundaries and the city limit come from the City of Airdrie's public
ArcGIS feature services (the exact service URLs are recorded in
`manifest/cities.json`). This data is governed by the City of Airdrie's terms,
**not** by the ODbL.

> Note for the publisher: as with Calgary above, we were not able to retrieve the
> licence page as text to quote it literally, and no separate terms URL is recorded
> alongside the data. If this attribution is not what the City of Airdrie requires,
> please open an issue and we will correct it.

## City of Calgary

Contains information licensed under the **Open Government Licence – City of
Calgary**.

Community boundaries and the city limit come from Open Calgary,
<https://data.calgary.ca>. This data is governed by the City of Calgary's terms of
use, **not** by the ODbL that covers the OpenStreetMap-derived packs.

> Note for the publisher: the wording above follows the standard Open Government
> Licence form. We were not able to retrieve the licence page as text to quote it
> literally. If this attribution is not what the City of Calgary requires, please
> open an issue and we will correct it.

## City of London, Ontario

Planning district boundaries published by the **City of London, Ontario**.

Source: the City of London's open data services (service URLs in
`manifest/cities.json`).

**Terms of use:**
<https://london.maps.arcgis.com/sharing/rest/content/items/e31458fd0c7e41dd9f93144a9550781d/data>

Those terms permit modification, redistribution and commercial use, and make
attribution optional; we name the publisher anyway. **They are the terms that
govern that data** — nothing in this repository's own licence adds restrictions to
it, and the ODbL does not apply to it.
