## Vocabulary scheme
See the files [`concept.json`, `concept_scheme.json`, `concept.jsonld`, `concept_scheme.jsonld`] for an outline of the current structure.

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
