# Schema
This is the official repository for schemas describing data contributed to [babylon-online.org](http://babylon-online.org).
**cf. https://json-schema.org**

# Excavation
* these are entities which form a group with a specific naming tradition over one or more seasons
* seasons happen over a specific range of time. Having people being participants over a specific range of time within this season.

---

# ExcavationUnit
* excavationUnits are by default geojson-objects (https://tools.ietf.org/html/rfc7946, http://wiki.geojson.org/GeoJSON_draft_version_6). The artefact while being in excavation is also an excavationUnit (somehow historic) - extending the understanding of a _Befund_ which normally only describes the context in which an artefact is found, -> artefacts can e.g. also contain other units. An array of excavationFeatures is a geojson-FeatureCollection.
* if the excavatedObject does not contain a reference at excavationUnitData it is most probably purchased.
* if an excavationUnit is missing a reference at excavatedObjectData it is not an artefact.
* an excavationUnit is not a stratigraphic unit. Stratigraphy has its own model with other dependencies pointing towards excavationUnits extending the graph of information.

---

# ExcavatedObject

---

# ArchivalResource

---

# Collection

---

# Holder

---

# Vocabulary scheme
See the files [`concept.json`, `concept_scheme.json`, `concept.jsonld`, `concept_scheme.jsonld`] for an outline of the schema.

We opted for using `json` as fileformat, while being conform with the _SKOS Simple Knowledge Organization System_ described [here](https://www.w3.org/TR/skos-primer/). For our usage as a lookup vocabulary, `json` fulfills the needs of being fast and easily usable. We extend our json with json-ld on the domain level for those applications which like to use it.
Because there is no _facet_ element in skos, this is the only element we declared and identified it as a skos:broaderTransitive.

* https://www.w3.org/TR/skos-primer/
* https://json-ld.org/spec/latest/json-ld/
* https://json-ld.org/playground/
* http://www.dublincore.org/specifications/dublin-core/dcmi-terms/
* Also [this gist](https://gist.github.com/jaw111/bbd1b00d656045ba8a2c) was very helpful understanding jsonld with skos.

See also JSKOS https://gbv.github.io/jskos/jskos.html and https://github.com/gbv/jskos for other implementations. We used our own implementation of `json` with `jsonld` because we thought we didn't need much of the odd keys and the overhead in jskos and wanted to keep it simple.

## Tools
There are other applications for managing controlled vocabularies:
* https://www.poolparty.biz/
* http://opaquenamespace.org/
* http://iqvoc.net/

Translators are available:
* https://rdf-translator.appspot.com/ RDF Translator is a multi-format conversion tool for structured markup. It provides translations between data formats ranging from RDF/XML to RDFa or Microdata (with API).
* http://www.easyrdf.org/converter A PHP library designed to make it easy to consume and produce RDF.

## Proposals
* Proposed specification for a REST API: https://www.w3.org/2001/sw/wiki/SKOS_Repository_REST_http_API
* Ruby gem https://github.com/ruby-rdf/json-ld/ (JSON-LD reader/writer)

## Discussions
* Very good posting on the origins of json-ld: http://manu.sporny.org/2014/json-ld-origins-2/
* https://www.w3.org/2013/dwbp/wiki/RDF_AND_JSON-LD_UseCases

## Todo
Facet for archaeological classes (e.g. "Stratigraphic (Erde, Kleinfund, Mauer, Gebäude, Fussboden, Interface)", "Artificial (Areal, Quadrant, Testschnitt)", "Site (Tell, City)").

---

# Texteditions
There are two major initiatives for digital-text-editions conventions.
* [Oracc](#Oracc)
* [EpiDoc](#EpiDoc)

## Oracc
http://oracc.museum.upenn.edu/doc/help/index.html

Description of json format http://oracc.museum.upenn.edu/doc/opendata/index.html

## EpiDoc
http://www.stoa.org/epidoc/gl/latest/intro-eps-de.html

siehe [Template](./ex-epidoctemplate.xml).


## Prosopography
Eine Attestation ist in zweifacher Form ein Event. Sie beschreibt das Ereignis des Forschers, als auch das Ereignis welches einer Person eine gewisse Eiegenschaft attestiert.

---

# CitationData scheme
Hierin wird die Struktur der bibliographischen Daten beschrieben. Siehe `citation_data_item.json`. `citation_data_analytics` beinhaltet Informationen welche nicht für eine Veröffentlichung gedacht sind, so z.B. Volltext und Verweise auf andere lizenzbeschränkte Daten.

Die Basisstruktur ist csl-json; Zusätze durch uns sind kompatibel im options hash enthalten (tags) - siehe `citation_data_item.json`
* https://citationstyles.org/
* https://github.com/citation-style-language/schema
* https://github.com/citation-style-language/schema/blob/master/csl-data.json
* http://docs.citationstyles.org/en/stable/specification.html#appendix-iv-variables
* http://docs.citationstyles.org/en/stable/primer.html
* https://citeproc-js.readthedocs.io/en/latest/csl-json/markup.html

Einträge in den Bibliograpiedateien sind folgendermaßen benannt/ haben folgende id: pedersen_2018_cut = Nachname erster Autor/Herausgeber, Jahr, erstes, aussagekräftiges Wort des Titels. Der Dateiname im Verzeichnis `data` ist entsprechend, ergänzt durch .json

### Offene Fragen
* Sollten die einzelnen json Objekte in einer Datei als Array gespeichert sein, wie im csl-data schema vorgesehen oder einzeln? => Aufgrund von options: :fulltext könnte eine einzelne Datei sehr groß werden.

### Eintragstypen
["article", "article-journal", "article-magazine", "article-newspaper", "bill", "book", "broadcast", "chapter", "dataset", "entry", "entry-dictionary", "entry-encyclopedia", "figure", "graphic", "interview", "legal_case", "legislation", "manuscript", "map", "motion_picture", "musical_score", "pamphlet", "paper-conference", "patent", "personal_communication", "post", "post-weblog", "report", "review", "review-book", "song", "speech", "thesis", "treaty", "webpage"] siehe auch [hier](https://github.com/citation-style-language/schema/blob/f01ba9c5ec2055e381a38598919a379255c496c5/csl-data.json#L12).

Achtung: Ein _Incollection_ ist vom Typ her ein _Chapter_. Eine _Collection_ ein _Book_ mit Editor.

### Locatortypen
["book", "chapter", "column", "figure", "folio", "issue", "line", "note", "opus", "page", "paragraph", "part", "section", "sub verbo", "verse", "volume"] siehe auch [hier](https://github.com/citation-style-language/schema/blob/f01ba9c5ec2055e381a38598919a379255c496c5/csl-citation.json#L47).

## Import
* Parse scholarly references, edit and save http://anystyle.io
* Convert references in various formats https://citation.js.org

---

# Person schema

---

# License
This repository is released under the [MIT license](LICENSE).

# Tools
* https://jsonschema.net/ zum Schema aus den Daten ableiten
* https://www.jsonschemavalidator.net/
* auch https://jsonschemalint.com/#/version/draft-07/markup/json
* automatische forms aus einem Schema generieren:
  * https://github.com/json-editor/json-editor
  * https://jsoneditoronline.org/

## Atom packages
* [Convert csv to json, json to csv, and more.](https://atom.io/packages/json-converter)
* [Creates UI in Atom for json files created along their schemes.](https://atom.io/packages/atom-json-editor)
