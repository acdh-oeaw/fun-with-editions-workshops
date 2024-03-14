# Typesense

2024-03-14, 13:30-15:00 E3

## What to bring

* a laptop with docker installed

## What to prepare 

### Install Typesense
* install Typesense via docker following the [official typesense docu](https://typesense.org/docs/guide/install-typesense.html#docker) (i.e. copy & paste the code snippet)

### Install Typesense Dashboard
* install [Typesense Dashboard](https://github.com/bfritscher/typesense-dashboard) via Docker following the [Readme](https://github.com/bfritscher/typesense-dashboard?tab=readme-ov-file#docker)


## AGENDA

### What is typesense and how do we use it at the ACDH-CH

* a very **fast**, **easy** to set up/maintain and **easy** to work with **search engine**

* comes with a very robust JavaScript library [InstantSearch.js](https://www.algolia.com/doc/guides/building-search-ui/what-is-instantsearch/js/) to build search interfaces

* used in several (digital-edition) projects
  * https://thun-korrespondenz.acdh.oeaw.ac.at/search.html
  * https://amp.acdh.oeaw.ac.at/search.html?amp%5Bquery%5D=K%C3%B6nig
  * https://b-vg.acdh.oeaw.ac.at/search.html
  * https://emt.acdh-dev.oeaw.ac.at/search.html
  * ...

### check local setup

`docker container ps` should show at least two containers running

### build and populate an index

have look at [build_index.ipynb](build_index.ipynb)

### build a search interface

* have a look into the `app` folder
* create a search token (via the Typesense Dashboard) and add it to `app/search.js`
* start a server in the `app` directory: e.g. `python -m http.server`

## aims

At the end you should be able have Typesense and Typesense Dashboard running locally, create a collection, populate it and build a search interface

## special guests
[Stephan Kurz](https://www.oeaw.ac.at/ihb/personen/kurz-stephan) from the IHB who currently works on transforming https://maechtekongresse.acdh.oeaw.ac.at/pages/index.html (eXist-db) into a cookiecutter based version

## super surprise

well, its a surprise
