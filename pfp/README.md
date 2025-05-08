# PFP – Prosopographische Forschungsplattform Österreich

["Website"](https://www.oeaw.ac.at/de/acdh/forschung/dh-forschung-infrastruktur/aktivitaeten/dh-datenmodellierung/pfp-prosopographische-plattform-oesterreich)
["Presentation"](https://acdh-ch.pages.oeaw.ac.at/pfp/pfp-sab-2025/)

## relevant pointers

### ["PFP-Gitlab-Project"](https://gitlab.oeaw.ac.at/acdh-ch/pfp)
* we need GIT-LFS, not for free in GitHub

### [PFP API](https://gitlab.oeaw.ac.at/acdh-ch/pfp/pfp-api)
* RDF-Proxy provides a REST-Api to retrieve CIDCOC CRM Graph Data

### [Qlever](https://qlever-ui.acdh-ch-dev.oeaw.ac.at/)
* [Qlever](https://github.com/ad-freiburg/qlever) is a highly perfomant, low resources triplestore

### PFP-Schema(https://pfp-schema.acdh.oeaw.ac.at/)
* shacl file to validate data
* shared E55 Types
    Person Person Relations
    Person Work Relations
* mapping files from custom project to PFP-E55 Types

### [PFP Source Data](https://gitlab.oeaw.ac.at/acdh-ch/pfp/pfp-source-data)
* stores the data
* data validation/harmonisation/enrichment pipelines

### [PFP Data Providers](https://github.com/pfp-data-providers)
* GitHub repos to process data from different (digital-edition) projects
* [xyz2pfp-template](https://github.com/pfp-data-providers/xyz2pfp-template)