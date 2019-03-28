## CitationData scheme
Hierin wird die Struktur der bibliographischen Daten beschrieben. Siehe `citation_data_scheme.json`.

Die Basisstruktur ist csl-json; Zusätze durch uns sind kompatibel im options hash enthalten (tags, imagery, fullText) - siehe `citation_data_schema.json`
* https://citationstyles.org/
* https://github.com/citation-style-language/schema
* https://github.com/citation-style-language/schema/blob/master/csl-data.json
* http://docs.citationstyles.org/en/stable/specification.html#appendix-iv-variables
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
