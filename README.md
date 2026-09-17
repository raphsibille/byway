# Byway route map

A single-page interactive map showing rights of way relevant to off-road cycle routes:

- **Bridleway**
- **Restricted byway**
- **Byway Open to All Traffic (BOAT)**
- **Track**

## How to use it

Open `index.html` in any browser — no install or server needed. It starts centred on BA15
(Bradford-on-Avon). Pan and zoom in (zoom 13+) to load route data for the area on screen.

## How it works

- Basemap: OpenStreetMap tiles.
- Overlay: fetched live from the [Overpass API](https://overpass-api.de), which queries
  OpenStreetMap for ways tagged `highway=bridleway`, `highway=track`, and the `designation`
  values `public_bridleway`, `restricted_byway`, and `byway_open_to_all_traffic`.

This is community-mapped OSM data, not the legal Definitive Map of Public Rights of Way — treat
it as a planning aid, not a legal source. Unlike the other three, `highway=track` isn't itself a
legal right of way — it just marks an unsurfaced route, and access varies (public, permissive,
or private), so check `access`/`designation` tags before assuming a track is rideable.

## Next steps (route planner)

This overlay is the first step towards a cycle route planner that builds GPX routes along roads
and these right-of-way types. Likely direction: keep OSM/Overpass as the data source, add a
routing engine (e.g. an OSRM or GraphHopper instance with a custom profile that favours
bridleways/byways) to generate routes, and add GPX export from the browser.
