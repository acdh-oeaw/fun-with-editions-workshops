# OAI-PMH

## What?

Open Archives Initiative - Protocol for Metadata Harvesting
[Specification](https://www.openarchives.org/OAI/openarchivesprotocol.html)
> Version 2.0 of the protocol was released in 2002
> -- <cite>[Wikipedia](https://en.wikipedia.org/wiki/Open_Archives_Initiative_Protocol_for_Metadata_Harvesting)</cite>

## Why?

* mainly used for data aggregation; e.g. [ARCHE](https://arche.acdh.oeaw.ac.at/browser/de/api-zugriff#oai-pmh) -> OAI-PMH -> [Kulturpool/Europeana](https://kulturpool.at/suche?refinementList=intermediateProvider%255B0%255D=ARCHE)
* in context of dse-static applications used an a simple API

## How?

The specification defines:
* one endpoint 
* six verbs (sent either as GET or POST requests)
  * Identify
  * ListIdentifiers
  * ListMetadataFormats
  * ListRecords
  * GetRecord
  * ListSets
* request and response formats

## dse-static and OAI-PMH

two components: 

### [oai-pmh-static](https://github.com/acdh-oeaw/dse-static-cookiecutter/tree/main/%7B%7Bcookiecutter.directory_name%7D%7D/oai-pmh)

Python code used to generate parts of the expected OAI-PMH response on build time and stores them as static XML files. The output of those XML files, read the metadata provided by each edition-project, can be customized.

### [dse-static-oai-pmh](https://github.com/acdh-oeaw/dse-static-oai-pmh)

A FastApi server which
* listens for OAI-PMH conform requets (GET and POST)
* fetches the requested information from the individuall digital-editions
* modifies the static respones from the digital-editions
* serves them to the client in OAI-PMH conform way

new entries can be registered in [this config file](https://github.com/acdh-oeaw/dse-static-oai-pmh/blob/main/app/config.py)

```python
ENDPOINTS = {
    "b-vg": {
        "title": "Die Entstehung des Bundes-Verfassungsgesetzes 1920.",
        "url": "https://b-vg.acdh.oeaw.ac.at/oai-pmh/",
    },
    "akademieprotokolle": {
        "title": "Sitzungsprotokolle der Österreichischen Akademie der Wissenschaften.",
        "url": "https://akademieprotokolle.acdh.oeaw.ac.at/oai-pmh/",
    },
}
```