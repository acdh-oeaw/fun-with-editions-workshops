# ARCHE-LOCALHOST-UTILS & and ARCHE-MD with Baserow

2024-03-14, 13:30-15:00 D3

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