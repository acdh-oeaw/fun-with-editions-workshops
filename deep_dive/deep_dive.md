# ACDH-CH Deep Dive: DSE-Static | Astro

## what does DSE stands for

DSE stands for Digital Scholarly Edition, which in the context of the ACDH-CH is understood as TEI/XML encoded texts.

## what is DSE-Static-Cookiecutter

DSE-Static-Cookiecutter is a command line tool, implemented with the [Python "cookiecutter" package](https://cookiecutter.readthedocs.io/en/stable/) to initialize a static site generator (DSE-Static) for TEI/XML encoded documents. 

## what is DSE-Static

DSE-Static is a static site generator for TEI/XML encoded documents
* TEI/XML documents are converted via XSLT into HTML Documents, conversion/build process run via ANT (Java) and Saxon (Java)
* HTML Documents can than be served via simple web server
* Build process congifured to run via Github Actions and to publish HTML (and TEI/XML) documents via GitHub Pages


## Motivation

### Cookiecutter

* initializes default folder structure and starting scripts/templates;
* injects project specific elements like project-title, GitHub-Repo names, deployment-url...
* choose set up options (internatialisation; separation of code/data)

![cookiecutter_cli.png](deep_dive/img/cookiecutter_cli.png)