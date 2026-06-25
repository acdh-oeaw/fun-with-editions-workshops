# Österreichisches Musiklexikon (neu)

<https://oeml.acdh-dev.oeaw.ac.at/>

## Anmerkungen Timo

- Editor's choice u.a.: Links, die auf „In Vorbereitung“-Seiten zeigen, könnten markiert oder ausgegraut sein.
- Auf großen Bildschirmen liegt der Footer in der Seitenmitte, wenn `<main>` nur wenige Inhalte enthält, z. B. bei „In Vorbereitung“.
- Das Impressum hat ein anderes Layout.
- Personenregister: Da Namens- und Artikel-Links meistens denselben Text haben, wirkt die Tabelle nicht sehr intuitiv. (Vielleicht könnten die Artikel in Anführungszeichen gesetzt oder anderweitig differenziert werden?)
- zu geringer Farbkontrast bei Text in grauer Schriftfarbe (axe DevTools)
- fehlender Bild-`alt`-Text (axe DevTools)
- ich fände es super, wenn der Text, der erklärt, was für eine Website das ist (`Das oeml ist ...`), visuell zentraler wäre - er ist jetzt (wie bei der alten Seite auch) in den Peripherie-Bereich mit weiterführenden Links ausgegliedert (den ich persönlich kognitiv gleich einmal ausgeblendet habe)
- umgekehrt `Artikel der Woche` vielleicht zu zentral (im Vergleich zum eher geringen Stellenwert dieses Features gegenüber so zentralen Features wie `Artikel A–Z` oder `Detailsuche`)? Wirkt extra-prominent durch Schattierung um Rahmen, sodass es optisch quasi 3-dimensional heraussticht gegenüber sonst flachem Design ...
- komfortable sticky navigation sidebar in Artikel-Ansicht
- angenehm, dass Volltext- und Artikel-Suche (getrennt in alter Seite) jetzt in einem Tool vereint sind

## Anmkerungen Peter

## Datenzugang

- aktuelle kein Zugriff über Website auf TEI/XML Daten. Warum?
- [OAI-PMH](https://github.com/acdh-oeaw/dse-static-oai-pmh) Schnittstelle einbauen? -> Artikel-Volltexte in Unified Corpora integrieren
- Personendaten für PFP?

## Artikelübersicht

- Gesamtzahl der Artikel
- Gesamtliste, idealerweise als Tabelle die man in strukturierter Form (CSV, JSON) herunterladen kann, bzw. für das Personenregister
  - datatables/tabulator Version des Artikel/Personenverzeichnisses anbieten?
- `?` "Zufällige Auswahl" imho unnötig und wenig selbsterklärend

## Detailsuche

- styling der Facetten sieht unfertig aus
  - select-listen
  - paddding bei Ergebnissen
  - Facetten nicht wirklich als klickbar erkennbar

## Arikel-Detail-View

- Blättern super, aber ein bisschen zu klein, vielleicht vorigen/nächsten Artikel nicht erst bei hover-over zeigen
- sticky nav sidebar super, aber Punkte Orte und Online version deutlicher Trennen
- Dreiecksymbol als bullet-list nicht optimal da das symbol default für html-detail verwendet wird (accordion, collapsible), sprich ich will da immer draufdrücken
- Zitiervorschlag, Super!!!!!
- Lizenz, Super!!! (noch eine Überschrift "Lizenz" dazu, )
- bzw. Autor: vielleich mit einen Link hinterlegen und auf Suche mit voreingestellter Facette

## generell

- Wechsel des Farbschema zwischen Start/Suchseite und Detailansicht verwirrend
- [Das Projekt](https://oeml.acdh-dev.oeaw.ac.at/projekt.html) andere Schrift/Layout als Artikel
