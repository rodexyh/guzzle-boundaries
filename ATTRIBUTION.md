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
| Abbotsford | ca-bc | City of Abbotsford | Open Government Licence – City of Abbotsford | [City of Abbotsford](#city-of-abbotsford) |
| Burnaby | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Coquitlam | ca-bc | City of Coquitlam | Open Government Licence – Coquitlam | [City of Coquitlam](#city-of-coquitlam) |
| Richmond | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Saanich | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Surrey | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Vancouver | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Victoria | ca-bc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Winnipeg | ca-mb | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Ajax | ca-on | Town of Ajax | Town of Ajax Open Data Licence | [Town of Ajax](#town-of-ajax) |
| Cambridge | ca-on | City of Cambridge | Open Government Licence – City of Cambridge | [City of Cambridge](#city-of-cambridge) |
| Guelph | ca-on | City of Guelph | Open Government Licence – City of Guelph | [City of Guelph](#city-of-guelph) |
| Hamilton | ca-on | City of Hamilton | City of Hamilton Open Data Licence (Version 1.1) | [City of Hamilton](#city-of-hamilton) |
| Kingston | ca-on | City of Kingston | Open Data Licence – City of Kingston | [City of Kingston](#city-of-kingston) |
| Kitchener | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Milton | ca-on | Town of Milton | Open Government Licence – Milton | [Town of Milton](#town-of-milton) |
| Oshawa | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Ottawa | ca-on | City of Ottawa (Ottawa Neighbourhood Study) | Open Government Licence – City of Ottawa | [City of Ottawa](#city-of-ottawa) |
| St. Catharines | ca-on | Niagara Region | Open Government Licence – Niagara Region | [Niagara Region](#niagara-region) |
| Toronto | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Waterloo | ca-on | City of Waterloo | Waterloo Open Data User Licence | [City of Waterloo](#city-of-waterloo) |
| Whitby | ca-on | The Regional Municipality of Durham | Region of Durham Open Data Licence | [Region of Durham](#region-of-durham) |
| Windsor | ca-on | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Laval | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Longueuil | ca-qc | Ville de Longueuil | Creative Commons Attribution 4.0 | [Ville de Longueuil](#ville-de-longueuil) |
| Lévis | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Montréal | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Québec | ca-qc | OpenStreetMap contributors | Open Database License (ODbL) 1.0 | [OpenStreetMap](#openstreetmap) |
| Trois-Rivières | ca-qc | Ville de Trois-Rivières | Creative Commons Attribution 4.0 | [Ville de Trois-Rivières](#ville-de-trois-rivières) |

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

## City of Abbotsford

Contains information licenced under the Open Government Licence – City of Abbotsford.

Neighbourhood boundaries come from the City of Abbotsford's "Community Boundaries"
data on its open data site; the city limit used to check coverage comes from the
City's own boundary layer. Service URLs are in `manifest/cities.json`.

**Licence:** Open Government Licence – City of Abbotsford, Version 2,
<https://opendata-abbotsford.hub.arcgis.com/pages/city-of-abbotsford-open-data-licence>.
This data is governed by that licence, **not** by the ODbL.

## Town of Ajax

Contains public sector Information made available under The Corporation of the Town
of Ajax's Open Data Licence.

Neighbourhood boundaries come from the Town of Ajax's "Ajax Neighbourhoods" dataset,
<https://opendata.ajax.ca/datasets/ac85c5244bc8409c9a657004a5abcdd7>. One record's
name field holds a paragraph of local history instead of a name; it is shown as
"Pickering Village", the neighbourhood that paragraph describes (`renames` in
`manifest/cities.json`). The area named "Central Employment Area" is left out. The
town limit used to check coverage comes from the Region of Durham's open data (see
that section).

**Licence:** Town of Ajax – Open Data Licence v.1.0,
<https://townofajax.maps.arcgis.com/sharing/rest/content/items/22e2d8e248724d7cb0310dc2db675abd/data>.
It does not require credit; we give it in the wording the licence asks for when
credit is given. This data is governed by that licence, **not** by the ODbL.

## City of Cambridge

Contains information licensed under the Open Government Licence – City of Cambridge.

Neighbourhood boundaries come from the City of Cambridge's "Planning Neighbourhoods"
dataset, <https://geohub.cambridge.ca/datasets/37355aacc1f54584879e14dc0cfd67ee>;
the city limit used to check coverage comes from the municipal boundary layer on
the City's open data site. The source stores neighbourhood names in capitals; they
are shown in mixed case (`renames` in `manifest/cities.json` lists every name as
changed), and the area named "Industrial Park" is left out.

**Licence:** Open Government Licence – City of Cambridge, Version 2.0,
<https://maps.cambridge.ca/images/opendata/Open%20data%20licence.pdf>.
This data is governed by that licence, **not** by the ODbL.

## City of Coquitlam

Contains information licensed under the Open Government Licence – Coquitlam.

Neighbourhood boundaries come from the "Community Profile Boundaries" layer of the
City of Coquitlam's "Planning and Development" data on the Coquitlam Open Data
Portal, <https://data.coquitlam.ca/>; the city limit used to check coverage comes
from the City's cadastral data. The source stores names in capitals; they are shown
in mixed case (`renames` in `manifest/cities.json` lists every name as changed).

**Licence:** Open Government Licence – Coquitlam,
<https://www.coquitlam.ca/894/Open-Government-Licence>.
This data is governed by that licence, **not** by the ODbL.

## Region of Durham

Contains public sector information made available under The Regional Municipality of
Durham's Open Data Licence.

Neighbourhood boundaries for Whitby are the ten Whitby areas of the Region of
Durham's "Health Neighbourhoods" dataset, <https://opendata.durham.ca/datasets/7267d01b1348498694d887b091d735c7>,
named by their common names. The town limits used to check coverage for Whitby and
Ajax come from the Region's municipal boundary layer. Service URLs are in
`manifest/cities.json`. Two Whitby areas are drawn along opposite sides of
Cochrane Street and overlap by a strip under 10 m wide; this is allowed for that
one pair of areas and that exact source file (`overlapExceptions` in
`manifest/cities.json`).

**Licence:** Region of Durham – Open Data Licence v.1.0,
<https://durham.ca/en/regional-government/open-data.aspx>. It does not require
credit; we give it in the wording the licence asks for when credit is given.
This data is governed by that licence, **not** by the ODbL.

## City of Guelph

Contains information licensed under the Open Government Licence – City of Guelph.

Neighbourhood boundaries come from the City of Guelph's "Guelph Areas" dataset on
Guelph Open Data, <https://explore.guelph.ca/datasets/7d40590c50774e709d3487edbb031547>;
the city limit used to check coverage comes from the City of Guelph's public map
services. Three areas named "Non-Residential" are left out (they are not
neighbourhood names). Service URLs are in `manifest/cities.json`.

**Licence:** Open Government Licence – City of Guelph, Version 2.0,
<https://explore.guelph.ca/pages/open-data-license>. The dataset record names no
other licence, and Guelph Open Data's terms of use
(<https://explore.guelph.ca/pages/terms-of-use>) state that its data is under the
Open Government Licence except where otherwise noted.
This data is governed by that licence, **not** by the ODbL.

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

## City of Kingston

Contains information licensed under the Open Data Licence – City of Kingston.

Neighbourhood boundaries come from the City of Kingston's "Neighbourhood Boundaries"
dataset, <https://opendatakingston.cityofkingston.ca/datasets/29cc78eb658641588b3d15fabc600902>;
the city limit used to check coverage comes from the City's own boundary layer.
Service URLs are in `manifest/cities.json`.

**Licence:** City of Kingston Open Data Licence, Version 1.0,
<https://www.cityofkingston.ca/media/wtpgpkb0/gis_license_opendata.pdf>.
This data is governed by that licence, **not** by the ODbL.

## Ville de Longueuil

Neighbourhood boundaries: « Quartiers (anciens) », by the **Ville de Longueuil**,
published on Données Québec,
<https://www.donneesquebec.ca/recherche/dataset/quartiers-anciens>, under the
[Creative Commons Attribution 4.0 International licence (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

**Changes:** outlines simplified to about 20 m and stored as grid cells for on-device matching; the area named « Zone Aéroportuaire » left out; other names as published; areas checked against the city limit in the Gouvernement du Québec's « Découpages administratifs » (<https://www.donneesquebec.ca/recherche/dataset/decoupages-administratifs>, also CC BY 4.0), which is not part of this city's data and is not included in the packs.

This data is governed by CC BY 4.0, **not** by the ODbL. No endorsement by the
Ville de Longueuil is implied.

## Town of Milton

Contains information licensed under the Open Government Licence – Milton.

Neighbourhood boundaries come from the Town of Milton's "Neighbourhoods" dataset,
<https://discover-milton.hub.arcgis.com/datasets/6c26ff98c86c48e38a01860c264b4eab>;
the town limit used to check coverage comes from the Town of Milton's public map
services. Service URLs are in `manifest/cities.json`.

**Licence:** Open Government Licence – Milton, Version 2.0,
<https://discover-milton.hub.arcgis.com/pages/disclaimer-and-terms-of-use>.
This data is governed by that licence, **not** by the ODbL.

## Niagara Region

Contains information licensed under the Open Government Licence - Niagara Region

Neighbourhood boundaries for St. Catharines come from Niagara Region's
"Neighbourhood Boundaries 2011" dataset on Niagara Open Data,
<https://niagaraopendata.ca>; only the neighbourhoods in St. Catharines are used.
The city limit used to check coverage comes from Niagara Region's municipal
boundaries layer. Service URLs are in `manifest/cities.json`.

**Licence:** Open Government Licence 2.0 – Niagara Region,
<https://niagaraopendata.ca/pages/open-government-license-2-0-niagara-region>.
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

## Ville de Trois-Rivières

Neighbourhood boundaries: « Quartier (nom populaire) », by the **Ville de
Trois-Rivières**, published on Données Québec,
<https://www.donneesquebec.ca/recherche/dataset/quartier-nom-populaire-v3r>, under
the [Creative Commons Attribution 4.0 International licence (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

**Changes:** outlines simplified to about 20 m and stored as grid cells for on-device matching; names as published; areas checked against the city limit in the Gouvernement du Québec's « Découpages administratifs » (<https://www.donneesquebec.ca/recherche/dataset/decoupages-administratifs>, also CC BY 4.0), which is not part of this city's data and is not included in the packs.

This data is governed by CC BY 4.0, **not** by the ODbL. No endorsement by the
Ville de Trois-Rivières is implied.

## City of Waterloo

Contains information provided by the City of Waterloo under licence.

Neighbourhood boundaries come from the City of Waterloo's "District Plans" dataset,
<https://data.waterloo.ca/datasets/2fb4cc862830455eb02a8fdd2f03d2b8>; the city limit
used to check coverage comes from the City's own boundary layer. The area named
"Rural East" is left out (it is not a neighbourhood name). Service URLs are in
`manifest/cities.json`.

**Licence:** Waterloo Open Data User Licence,
<https://data.waterloo.ca/pages/open-data-licence> — the one licence published on
the City of Waterloo's open data site. It does not require credit; we give it in
the wording the licence asks for when credit is given.
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
