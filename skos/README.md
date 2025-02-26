# SKOS - Simple Knowledge Organization System

## some definitions
adapted from https://www.dataversity.net/introduction-to-skos/

### controlled vocabulary
>  A **list of terms** which a community or organization has agreed upon. For example: Kleinauto, Zug, S-Bahn are all "Fahrzeuge".

### taxonomy 
>  A controlled vocabulary organized in a **hierarchy**. 

Fahrzeug
* Auto
  * Kleinauto
  * Limosine
* Zug
  * Güterzug
  * Personenzug
    * Fernzug
    * Regionalexpress
    * S-Bahn

### thesaurus
> is a taxonomy with **more information about each concept** including preferred and alternative terms (z.B.: Auto/PKW), translations or even descriptions. Additionally a thesaurus may contain relationships to related concepts. 


## what is it

> SKOS is a formalized, human and machine readable thesaurus expressed in RDF.

https://www.w3.org/TR/skos-primer/


## how can I create it
* with any editor
* script it
* some GUI/Web-Editor like 


## what can I do with it / why should I use it

### play/visualize
https://skos-play.sparna.fr/play/

### publish
https://vocabs.acdh.oeaw.ac.at/en/

### archiv
https://hdl.handle.net/21.11115/0000-000F-6A81-8


## do I have a use case in my project?

https://grocerist.acdh.oeaw.ac.at/categories.html
https://amp.acdh.oeaw.ac.at/amp-index-events.html (type/subtype)
https://b-vg.acdh.oeaw.ac.at/toc.html (Dokumenttyp, Materialart)


## can I do the same in TEI

### use native TEI elements
https://tei-c.org/release/doc/tei-p5-doc/en/html/ref-classDecl.html

### include SKOS RDF/XML via xenoData
see [tei-skos](tei-skos.xml)