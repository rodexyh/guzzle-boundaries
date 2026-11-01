# Attribution

Every source whose data is in this repository, one section each.

This file is generated: a section appears here **if and only if** that source's data
is actually in one of the packs. A source that is not shipped does not get a
paragraph, and a source that is shipped cannot be missing one — the generator
refuses to write this file if it finds data it has no attribution text for.

## OpenStreetMap

© OpenStreetMap contributors. Data available under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/) —
see <https://www.openstreetmap.org/copyright>.

The per-province packs in `packs/regions/` are derived from OpenStreetMap
administrative relations (the `admin_level` that carries a city's neighbourhoods,
which differs by city and is confirmed by hand for each one). They are a derived
database and are therefore themselves distributed under the ODbL; `LICENSE` in this
repository is that licence.

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
