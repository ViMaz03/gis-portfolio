Wo Berlin ungleich ist: Sozialstruktur nach Planungsräumen

Thematische Karte der sozialen Lage in Berlin, erstellt mit QGIS. Die Statusklasse (hoch, mittel, niedrig, sehr niedrig) wird nur auf bebauten Wohnflächen gezeigt, Wälder, Seen und Freiflächen bleiben grau.

Daten
Planungsräume mit Statusklasse: Senatsverwaltung für Stadtentwicklung, Bauen und Wohnen, Monitoring Soziale Stadtentwicklung Berlin (2025)
Wohnflächen: OpenStreetMap, per QGIS-Plugin QuickOSM geladen (landuse=residential) , Abruf am 18.10.26
KBS: EPSG:25833

Methode (QGIS)
Wohnflächen mit QuickOSM laden (nur Polygone)
Layer ins KBS EPSG:25833 bringen, falls nötig
Geometrien reparieren (Wohnflächen und Planungsräume)
Verschneiden: Wohnflächen mit Planungsräumen, damit jede Fläche den Status ihres Planungsraums erhält
Berlin-Umriss per Auflösen der Planungsräume erzeugen, grau färben, ganz unten platzieren
Verschneidung kategorisiert nach der Statusspalte einfärben, ohne Kontur
Drucklayout mit Titel, Legende, Maßstabsleiste, Fußnote und Impressum, Export mit 300 dpi
Reflexion

Gelungen: Die Beschränkung auf Wohnflächen macht die Karte deutlich lesbarer als eine flächendeckende Einfärbung.

Schwierigkeiten: Der erste QuickOSM-Download schlug fehl, ein erneuter Versuch funktionierte. Ungültige Geometrien mussten vor dem Verschneiden repariert werden. Nach dem Verschneiden hatte die Statusspalte teils einen neuen Namen, die Symbologie musste neu zugewiesen werden.

Quellen
Senatsverwaltung für Stadtentwicklung, Bauen und Wohnen Berlin
© OpenStreetMap-Mitwirkende (ODbL)
Autor: Victor Mazurov

<img width="3507" height="2480" alt="karte_berlin" src="https://github.com/user-attachments/assets/1009f7f1-bd44-41a9-8ada-97b06b70900f" />


Reflexion: Objektiv betrachtet?

Für diese Aufgabe sollte ich in QGIS eine Karte der Berliner Planungsräume (2019) nachbauen, die vier Darstellungen derselben Bevölkerungsdaten nebeneinander zeigt: die absolute Einwohnerzahl nach Jenks und die Bevölkerungsdichte nach Jenks, Quantilen und gleichen Intervallen. Dazu kamen eine eigene Farbrampe und zwei Maßstäbe.

Die meiste Zeit hat nicht die Karte gekostet, sondern die Daten. Beim Verknüpfen der Excel-Tabelle mit dem Shapefile war bei der Hälfte der Planungsräume NULL eingetragen. Der Grund war, dass Excel bei den Schlüsseln die führende Null abgeschnitten hatte (1011101 statt 01011101). Das habe ich mit einem virtuellen Feld und lpad() angeglichen. Außerdem hatte ich erstmal zu viele Klassen gewählt und bekam dadurch Unmengen an Klassen.

Inhaltlich zeigt der Vergleich, wie stark Bezugsgröße und Klassifizierung den Eindruck bestimmen. Die absolute Einwohnerzahl täuscht, weil große Randräume dunkel erscheinen, obwohl sie dünn besiedelt sind. Erst die Dichte (Einwohner/km²) zeigt die hohe Verdichtung der Innenstadt. Auch die Klassifizierung verändert das Bild: Bei gleichen Intervallen fallen die meisten Räume in die untersten Klassen, die Karte wirkt hell. Bei Quantilen erscheinen weite Teile Berlins dunkel, weil schon Werte ab etwa 15.400 Einwohner/km² zur obersten Klasse zählen. Dieselben Daten erzeugen also unterschiedliche Aussagen, das Fragezeichen im Titel ist deshalb berechtigt.

<img width="3519" height="2480" alt="Berlin_lor_drucklayout" src="https://github.com/user-attachments/assets/e2eb2c85-0afd-412d-b057-c17cb96f377e" />


