# guzzle-boundaries

Neighbourhood boundary packs used by the [Guzzle](https://github.com/rodexyh/guzzle) iOS app.

Each pack is a small SQLite database describing the named areas of one city —
Vancouver's local areas, Calgary's communities, Toronto's neighbourhoods — plus a
precomputed hex-grid index that lets a phone answer "which area is this point in?"
without doing any geometry at runtime.

Two kinds of pack live here:

- **Per-province packs**, built from OpenStreetMap administrative relations. These
  are the ones the app downloads on demand: one file per province, containing every
  backbone city in it.
- **The bundled pack**, `packs/bundled/boundaries.sqlite`, built from three
  municipal open-data publishers (Calgary, Airdrie, London ON). This one ships
  inside the app itself; it is published here as well because the licences of the
  data in it are worth being able to check.

Generated from `index.json` of 2026-10-31T21:23:06Z.

## Licence

**The data in `packs/` and `index.json` is licensed under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/).**
The full text is in [`LICENSE`](LICENSE).

Some cities are not OSM-derived: Calgary, Airdrie and London ON (in the bundled
pack), and any city in a province pack whose `licenceKey` is not `osm`, come from
their municipalities' own open-data portals and are governed by **their publishers'
own terms**, not by the ODbL. Those terms are set out per source in
[`ATTRIBUTION.md`](ATTRIBUTION.md) — read that file before redistributing anything
here.

Photos inside the place-name tiles, where there are any, come from Wikimedia Commons
and stay under **their own licences**, not the ODbL; each photo's author, licence and
source are stored next to it, and `ATTRIBUTION.md` explains the columns.

The build pipeline that produces these packs is **not** in this repository and is
not covered by this licence. It lives in the Guzzle app repository; the ODbL
attaches to the database, not to the tools that made it.

## What is in a pack

One SQLite file per province. Every pack has the same shape:

- `meta` — how the pack was built: grid edge length (300 m), the simplification
  tolerance applied to the outlines (20 m), the schema version, the sha256 of the
  manifest it was built from.
- `cities` — one row per city, with its display name, its licence key, how many
  areas made it into the pack and how many were left out.
- `features` — the areas themselves: id, name, and a simplified outline.
- `feature_cells`, `feature_bbox`, `feature_rtree` — the precomputed hex-cell
  membership and spatial index. This is why the app never has to run a
  point-in-polygon test: the lookup is a hash of the cell the point falls in.

**Outlines are approximate.** Each area's boundary is simplified to roughly 20 m,
and neighbouring areas are simplified independently, so a shared edge becomes two
slightly different lines. These packs will tell you which neighbourhood you are in.
They will not tell you which side of a street a building is on.

## Region index

The app fetches `index.json` first, then the one pack it needs.

| Region | Cities | Pack size (gzipped) | Name tiles | Places (summed over tiles) | sha256 |
| --- | --- | --- | --- | --- | --- |
| `ca-ab` | Edmonton | 117,906 B | 171 | 6,727 | `bab727dfd2e3e516…` |
| `ca-bc` | Burnaby, Richmond, Saanich, Surrey, Vancouver, Victoria | 82,871 B | 317 | 18,446 | `86afeb02bd54bef9…` |
| `ca-mb` | Winnipeg | 71,886 B | 161 | 6,440 | `91d0214f204e98bf…` |
| `ca-nb` | — | — | 29 | 2,650 | — |
| `ca-nl` | — | — | 103 | 5,614 | — |
| `ca-ns` | — | — | 24 | 8,980 | — |
| `ca-nt` | — | — | 386 | 2,269 | — |
| `ca-nu` | — | — | 818 | 2,535 | — |
| `ca-on` | Hamilton, Kitchener, Oshawa, Ottawa, Toronto, Windsor | 371,816 B | 218 | 37,076 | `fba7b8402aa7cff0…` |
| `ca-pe` | — | — | 7 | 642 | — |
| `ca-qc` | Laval, Lévis, Montréal, Québec | 125,128 B | 278 | 38,100 | `68a24244a9ec5516…` |
| `ca-sk` | — | — | 172 | 4,893 | — |
| `ca-yt` | — | — | 246 | 1,437 | — |

## Same bytes as the CDN

Guzzle downloads these packs from a CDN, not from GitHub. **The files here are
byte-for-byte the files served there**, at matching paths:

| Here | Served as |
| --- | --- |
| `index.json` | `boundaries/v1/index.json` |
| `packs/regions/<code>-<sha16>.sqlite.gz` | `boundaries/v1/regions/<code>-<sha16>.sqlite.gz` |
| `packs/regions/<code>-names/<tile>-<sha16>.sqlite.gz` | `boundaries/v1/regions/<code>-names/<tile>-<sha16>.sqlite.gz` |

`<sha16>` is the first 16 hex digits of the file's own sha256, so a file name
never changes its contents: a rebuilt province gets a new name, and the old
object stays on the CDN for any phone still holding the previous index.
Older releases used fixed names (`<code>.sqlite.gz`); those objects are left in place.

`index.json` of this build has sha256 `0907387cbd8d495661aa715bac978cf762dd38db974914e3638a122f2c86b617`, and it carries the
sha256 of every pack. That one number is checked in three places: against the file
in this repository, against the object on the CDN right after it is uploaded, and
on the phone after the download. A pack whose bytes do not match its entry in the
index is discarded rather than used.

## Reproducing a pack

From a checkout of the Guzzle app repository:

```sh
# 1. Find and confirm the OSM admin level that actually has this city's
#    neighbourhoods in it. This prints a candidate report; a human picks.
tools/boundary-pack/osm/chooser.py --city "Vancouver"

# 2. Add the city to tools/boundary-pack/cities.json using the confirmed
#    relation id and admin level, then fetch its geometry from Overpass.
#    --refresh is what records the source fingerprints, the OSM base timestamp,
#    and how many relations could not be stitched into a closed ring.
tools/boundary-pack/osm/fetch-city.py --slot vancouver-osm --refresh

# 3. Build the province packs and the index.
tools/boundary-pack/build.sh
```

Step 3 verifies every source fingerprint before it builds anything, so a source
file that has changed upstream stops the build rather than silently producing a
different pack. `manifest/sources.sha256` in this repository is the record of what
those fingerprints were for this build — the raw GeoJSON itself is not committed
anywhere, so that file is how you check that your download matches ours.

`manifest/cities.json` is the manifest the packs were built from.
`manifest/bundled.lock.json` is the frozen copy of it that the bundled pack was
built from, which is what the app checks the bundled pack against.

## Reporting a wrong boundary

These outlines come from upstream data; we do not draw them. If an area is missing,
misnamed, or shaped wrong:

- For an OSM-derived city, fix it in [OpenStreetMap](https://www.openstreetmap.org/)
  — the correction reaches the next rebuild.
- For Calgary, Airdrie or London ON, report it to that city's open-data portal.

If a pack itself looks wrong — an area that exists upstream but is missing here —
open an issue in this repository.
