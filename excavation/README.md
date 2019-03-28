## Excavation data schema
* excavationUnits are by default geojson-objects (https://tools.ietf.org/html/rfc7946, http://wiki.geojson.org/GeoJSON_draft_version_6). The artefact while being in excavation is also an excavationUnit (somehow historic) - extending the understanding of a _Befund_ which normally only describes the unit in which an artefact is found, -> artefacts can e.g. also contain other units. An array of excavationFeatures is a geojson-FeatureCollection.
* if the excavatedObject does not contain a reference at excavationUnitData it is probably purchased.
* if an excavationUnit is missing a reference at excavatedObjectData it is not an artefact.
