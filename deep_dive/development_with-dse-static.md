# How to develop with dse-static-cookiecutter

* follow [dse-static-cookiecutter Readme](https://github.com/acdh-oeaw/dse-static-cookiecutter/blob/main/README.md)

```bash
cookiecutter gh:acdh-oeaw/dse-static-cookiecutter
```

* follow Readme.md of the created code base
```bash
cd dse-static/
./shellscripts/script.sh
./fetch_data.sh
ant
```

* start dev-server to see the result
```bash
cd html/
python -m http.server
```
go to [http://0.0.0.0:8000/](http://0.0.0.0:8000/)


# fields of development

## data fetching preprocessing

copy data from some data-repo, usually some simple bash-script

## data processing

usually done with Python and [acdh-tei-pyutils](https://acdh-oeaw.github.io/acdh-tei-pyutils/)

* delete not well formed files;
* denormalizing indices; 
* adding XML-IDs;
* data conversion, e.g. extract Dates for some Calendar

## web development

### HTML generation
* writing/adapting XSLTs to convert TEI/XML into HTML; usually done within Oxygen
* dse-static provides basic XSLT as well as some primitiv templating system e.g. for footer, nav-bar, html-head

### styling
* Bootstrap 5
* custom CSS

### Javascript
writing Javascript for interactive parts
* Datatables for list-views like table of contents; index pages for persons, places, ... (implemented with [Tabulator](https://tabulator.info/))
* customizing presentation of textual features (show/hide entities, deletion, abbreviations, ...); implemented with [Digital Edition Micro-Editor](https://github.com/acdh-oeaw/de-micro-editor) e.g. [Auden-Musulin-Papers](https://amp.acdh.oeaw.ac.at/amp-transcript__0063.html?tab=1r&del=on&prs=on&plc=on&wrk=on&org=on&eve=on&udl=on&wsp=on&ucl=on&cho=on)
* visualisations like maps, charts, networks, ...
* text-image linking (https://b-vg.acdh.oeaw.ac.at/bv_doc_id__1.html)
