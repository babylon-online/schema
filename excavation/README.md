# Excavation data schema

## Excavation
* these are entities which form a group with a specific naming tradition over one or more seasons
* seasons happen over a specific range of time. Having people being participants over a specific range of time within this season. 

## ExcavationUnits
* excavationUnits are by default geojson-objects (https://tools.ietf.org/html/rfc7946, http://wiki.geojson.org/GeoJSON_draft_version_6). The artefact while being in excavation is also an excavationUnit (somehow historic) - extending the understanding of a _Befund_ which normally only describes the context in which an artefact is found, -> artefacts can e.g. also contain other units. An array of excavationFeatures is a geojson-FeatureCollection.
* if the excavatedObject does not contain a reference at excavationUnitData it is most probably purchased.
* if an excavationUnit is missing a reference at excavatedObjectData it is not an artefact.
* an excavationUnit is not a stratigraphic unit. Stratigraphy has its own model with other dependencies pointing towards excavationUnits extending the graph of information.

## ExcavatedObjects


## ArchivalResources


## Collection

## Holder
