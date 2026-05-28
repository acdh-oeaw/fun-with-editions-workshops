# From `<listEvent>` to affiliation network

A reusable workflow for making TEI-XML event-co-affiliation data (data on the shared connection of entities with events) accessible to network analysis. Creates affiliation networks from `<listEvent>`s through an XSLT-and-Python pipeline.

## Motivation

- utilize network analysis in DSE projects ...
  - tried-and-tested DH approach
  - [NetworkX](https://networkx.org/en/): implements conceptual and methodological toolkit of network research in Python library
- ... based on native (and slightly processed) TEI data
  - in addition to correspondence relations
  - without explicit relationship modeling
- find technological solution for answering [AAD](https://www.oeaw.ac.at/acdh/research/literary-studies/research/authors-editions/auden-in-austria-digital) research question "Who did British-American poet W. H. Auden have to do with during his Austrian period 1957-1973"

## Pipeline

TEI-XML `<listEvent>`

↓

[listEvent-to-json.xsl](https://github.com/timofruehwirth/event-network/tree/main/xslt) → JSON

↓

[affiliation-builder](https://pypi.org/project/affiliation-builder/) → NetworkX Graph (bipartite affiliation network)

↓

Python/NetworkX processing (analysis and visualization)

## Workflow components

### affiliation-builder (generic™, v0.2.0)

... constructs bipartite networks from JSON affiliation data using NetworkX.

... handles different JSON structures:

- top-level container of events:
  - direct array of events (`[ {...}, {...}, ...`)
  - **events wrapped in object (`{"listEvent": [ { ...`)**
- types of affiliated entities:
  - single type (`"listPerson"`)
  - multiple types (`["listPerson", "org"]`)
- structure of affiliated entities:
  - simple listed values (`"listPerson": ["Auden, W. H.", "Kallman, Chester", ...]`)
  - **listed objects (`"listPerson": [ { "persName": "Benning, Achim","sameAs": "amp_person_129" ... },`)**

... preserves JSON fields as node attributes.

### listEvent-to-json.xsl (TEI-specific, unreleased)

... transforms a TEI `<listEvent>` into wrapped-object JSON to be consumed by the affiliation-builder package.

... preserves XML structure as far as compatible with JSON formatting through recursive parsing and nested serialization.

... reconciles XML structure with JSON requirements where necessary:

- flattening: `list*`-type wrapper objects (`<listPerson>`, `<listPlace>` ...) become single JSON keys of wrappers' name with arrays of unnamed objects including child elements' sub-elements and attributes - the child elements' labels (`<person>`, `<place>` etc.) are dropped
- grouping: repeated TEI siblings of the same name (such as multiple `<org>`s) are grouped into an array of that key

## Example real-data demonstration

[AMP](https://www.oeaw.ac.at/acdh/research/literary-studies/research/authors-editions/auden-musulin-papers) `<listEvent>` was serialized with listEvent-to-json.xsl to [amp-events.json](https://github.com/timofruehwirth/event-network/blob/main/examples/json/amp-events.json). The [amp-affiliation-network.ipynb](https://github.com/timofruehwirth/event-network/blob/main/examples/notebooks/amp-affiliation-network.ipynb) Notebook calls `affiliation_builder.build()` and pilots network post-processing of NetworkX Graph (based on dataset focused on single highlighted relationship).

## Main challenges

- ⚠ **upstream**: data modeling (What is an `<event>`? What are its features?) and rigorous markup
- **midstream**: testing of XSLT and Python components
- **downstream**: specific (limited) explanatory power of affiliation networks

## Use cases

- Auden in Austria Digital (`<person>`s and `<org>`s co-affiliated with Auden through `<event>`s): tracing Auden's social environment 1957-1973
- The Minutes of the Austrian Cabinet Council 1919–1920 (`<person>`s co-affiliated through cabinet `<meeting>`s): networks of political decision-making (cabinet members and informants)
