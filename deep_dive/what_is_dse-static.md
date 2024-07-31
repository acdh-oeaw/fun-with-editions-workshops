# ACDH-CH Deep Dive: DSE-Static | Astro

## what does DSE stands for

DSE stands for **D**igital **S**cholarly **E**dition, which in the context of the ACDH-CH is understood as TEI/XML encoded texts.

## what is DSE-Static-Cookiecutter

DSE-Static-Cookiecutter is a **command line tool**, implemented with the [Python "cookiecutter" package](https://cookiecutter.readthedocs.io/en/stable/) to initialize a static site generator (DSE-Static) for TEI/XML encoded documents. 

## what is DSE-Static

DSE-Static is a **static site generator for TEI/XML** encoded documents
* TEI/XML documents are converted via XSLT into HTML documents, conversion/build process runs via ANT (Java) and Saxon (Java)
* HTML documents can than be served via simple web server (no application server/databse needed)
* Build process runs via Github Actions, the resulting HTML (and TEI/XML) documents are published via GitHub Pages.

## Technology choices / Motivation

* Keep things simple
* All code must run via GH-Action
* Could Martin Anton use it?

### Cookiecutter

* initializes default folder structure and starting scripts/templates;
* injects project specific elements like project-title, GitHub-Repo names, deployment-url...
* choose set up options (internatialisation; separation of code/data)
![cookiecutter_cli](https://github.com/user-attachments/assets/f028fbad-ae6a-42d2-81bc-2ec3d63b7d26)

=> uniform project architecture 

#### Dependencies:

* Python
* cookiecutter

### XSLT/ANT

* Conversion of TEI/XML documents to HTML via XSLT is the de facto standard approach in the DH-Community.
* DH-People (not developers) are familiar with XPath, XSLT, and Oxygen.
* Oxygen also supports/executes ANT (`build.xml` files)
----
* Though you find also some projects using mainly XQuery (still in the X-Family) 
* Also some using JavaScript ([CETEIcean](https://github.com/TEIC/CETEIcean))

#### Dependencies
* Java
* Saxon [install script provided by dse-static-cookiecutter]
* ANT

=> all included in Oxygen-XML-Editor

### GitHub

* its free
* well documented
* provides infrastructure to build and to deploy the static-site
* nice integration with VsCode

### Bootstrap 5
* already some design
* responsiv
* [JS-Components](https://getbootstrap.com/docs/5.3/getting-started/introduction/#js-components)
  * nav-bar + dropdowns
  * buttons
  * modals
  * ...

### [Tabulator](https://tabulator.info/)

implements dynamic tables (sort/filter)


## ~ 15 Projects from ~ 10 People

### Peter
* https://thun-korrespondenz.acdh.oeaw.ac.at/
* https://rita.acdh.oeaw.ac.at/
* https://kaiserin-eleonora.oeaw.ac.at/
* [https://wmp1.acdh.oeaw.ac.at/](https://donauhandel.github.io/wkfm-static/)
* https://schnitzler-tagebuch.acdh.oeaw.ac.at/ (mit Martin Anton)

### Barbara
* https://karl-kraus.github.io/legalkraus-static/
* https://kraus1933.ace.oeaw.ac.at/index.html (noch TEI-Publisher)

### Daniel E.
* https://amp.acdh.oeaw.ac.at/
* https://hanslick.acdh.oeaw.ac.at/index.html?lang=de
* https://freud.acdh-dev.oeaw.ac.at/ (crappy data)
* https://bruckner-kopisten.acdh.oeaw.ac.at/

### Fritz
* https://b-vg.acdh.oeaw.ac.at/

### Kinga (+ Thomas)
* https://akademieprotokolle.acdh.oeaw.ac.at/

### Fernando (+ Michaela)
* https://fun-with-editions.github.io/staribacher-static/
* https://ofmgraz.github.io/ofm-static/

### Martin Anton
* https://schnitzler-briefe.acdh.oeaw.ac.at/ (mit Laura)
* https://schnitzler-bahr.acdh.oeaw.ac.at/
* https://schnitzler-lektueren.acdh.oeaw.ac.at
* https://schnitzler-chronik.acdh.oeaw.ac.at
* ...

### Laura
* https://pollaczek.acdh.oeaw.ac.at/ (mit Martin Anton?)
* https://sappho-digital.com/

---

### Richard Hörmann
* [https://tillich-briefe.acdh.oeaw.ac.at/](https://github.com/TillichCorrespondence/tillich-briefe-static)
* (https://ferdinand-korrespondenz.acdh.oeaw.ac.at/)

---

# Peter Provaznik / Clemens Gubsch
* https://brahms-online.oeaw.ac.at/
* https://bruckner-kopisten.acdh.oeaw.ac.at/
* schubert-online
---
# Stephan Kurz
* https://maechtekongresse.acdh.oeaw.ac.at/index.html
