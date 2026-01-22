# Karl Kraus 1933

## Feedback Kinga

### Menü
* grau zu hell
* Struktur etwas unklar, warum sind 2 Punkte extra und der Rest zusammengefasst
* Menü items und die Kacheln auf der Startseite z.T. unterschiedlich
* vielleicht auch Präferenz, aber ich finde es störend, dass man das Menü nur wieder zumachen kann wenn man auf den Button klickt, ich schaue mir z.B. auch gerne an was im Menü ist, und schaue dann was auf der Startseite noch ist, aber das aufgeklappte Menü blockiert auch das Scrollen und einfach woanders klicken funktioniert auch nicht.

### Topographische Umschrift
* Legende sehr klein
* bei den Buttons: warum ist der graue Kasten beim aktivierten Button plötzlich größer?
  <img width="450" height="203" alt="image" src="https://github.com/user-attachments/assets/db8ad2c2-0cf6-4db1-aeca-23f966987ce9" />
  <img width="448" height="203" alt="image" src="https://github.com/user-attachments/assets/0face75d-f6f2-45a5-96c1-f0efc079fdbb" />

* die Buttons für die 3 Sichten haben keine Tooltips, ich finde gerade die sind erklärungsbedürftig
* auf den Seiten, die ich ausprobiert habe hat der Highligting Mechanismus super funktioniert

### Notizen
* Bilder fangen mit nur 1 Seite an, da sind die Navigationsbuttons genau in der Mitte, danach wird das doppelseitig und die Navigation ist dann in der Mitte der linken Seite
  <img width="945" height="751" alt="image" src="https://github.com/user-attachments/assets/bffae0bb-508e-4fe9-ad2c-5663a26e5471" />

* feature oder bug? die Bilder der Notizen lassen sich in dem Kasten komplett frei rumschieben
  <img width="945" height="455" alt="image" src="https://github.com/user-attachments/assets/5cce2b7e-1977-4b5a-852b-900cd2c18d0a" />


### Personenregister
* Registereintrag sehr klein
* Textstellen im Registereintrag noch kleiner und viel zu hell, kaum lesbar
<img width="728" height="405" alt="image" src="https://github.com/user-attachments/assets/88e68d2b-3b18-4492-8fdf-05711a7787b7" />

### Responsiveness
* auf größeren Bildschirmen könnte der Platz bessser ausgenutzt werden
<img width="945" height="514" alt="image" src="https://github.com/user-attachments/assets/8b7b9361-f972-49ef-b5d1-eebc0b9d8f5f" />

### Annotierte Lesefassung
* andere Schalter + Fackel Nr. F890 canceln sich gegenseitig? z.B. Personen an, dann Fackel, Personen schaltet sich aus


## Feedback Fernando

### Allgemeines
## Struktur
* Ich finde es etwas verwirrend, dass aufgrund der Struktur der Website der Editionsapparat als Hauptinhalt und der Text selbst als Nebensache erscheint.
  
## Layout
* Jede von „Annotierte Lesefassung“, „Topographische Umschrift“ und „Notizen“ hat ihre eigene Textdarstellung. Das wirkt etwas unzusammenhängend. 

### Footer
* Die Logos wiederholen sich. Mit den Logos der Stadt Wien kann man wenig machen, aber das ACDH-Logo sollte weniger problematisch sein.
  <img width="1804" height="780" alt="pic02" src="https://github.com/user-attachments/assets/662465ef-9111-4024-b1fb-fb31b11e89f1" />
* Mir gefällt es, dass der große Footer nur auf der Landing-Page steht und es eine kleinere Version für die anderen gibt


### Responsiveness
* Das Layout vom Footer ist nicht optimal
<img width="583" height="371" alt="pic01" src="https://github.com/user-attachments/assets/20b0616f-0473-43a4-9f0a-77a37f518d4b" />

### Edition
* Ich glaube, Grau auf Weiß ist keine der besten Kombis für den Button "Zum Text". Er sollte mehr hervorgehoben werden

### Annotierte Lesefassung
* Der Navigationslink auf der ersten und der letzten Seite funktioniert nicht.
  <img width="1014" height="698" alt="pic03" src="https://github.com/user-attachments/assets/16ca6e24-9ddd-4511-8b7f-2f01f4eb866e" />

## Peter
### a11y

#### lesefassung
https://kraus1933.acdh.oeaw.ac.at/motti.html?
* Ensure each HTML document contains a non-empty <title> element
* Ensure that the page, or at least one of its frames contains a level-one heading (e.g. visually-hidden)

#### topographische umschrift
https://kraus1933.acdh.oeaw.ac.at/idPb0001.html?mode=off&view=all-columns
* Ensure every HTML document has a lang attribute

### Datenzugang

nicht möglich?
* TEI/XML
* beacon.txt?

### Register

* Breadcrumbs! (Top)
  * https://kraus1933.acdh.oeaw.ac.at/register_personen.html#DWpers1005 vielleicht bei konkretem Personeneintrag breadcrumb ergänzen

* persönlich: finde es schade wenn entitäten keine eigene Seite bekommen, 
* schade dass bibliographischer Nachweis hinter Icon versteckt ist
* gleiches Icon, unterschiedliche Funktionalität (einmal externer link, einmal ausklappen)
* gesamtzahl der Personen/Stellen?
* keine Möglichkeit nach Personen zu suchen


### Navigation
* "Zur Edition" finde ich verwirrent; besser über "Über die Edition"; zur Edition hätte ich link zu https://kraus1933.acdh.oeaw.ac.at/motti.html? erwartet
* inkonsequent Menu und Hamburgermenu; in beiden "Über die Edition" aber nicht "Zur Edition"
* über das Projekt auch im Footer

