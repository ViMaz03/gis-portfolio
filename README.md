Wo Berlin ungleich ist: Sozialstruktur nach Planungsräumen

Thematische Karte der sozialen Lage in Berlin, erstellt mit QGIS. Die Statusklasse (hoch, mittel, niedrig, sehr niedrig) wird nur auf bebauten Wohnflächen gezeigt, Wälder, Seen und Freiflächen bleiben grau.

Bild anzeigen

Daten
Planungsräume mit Statusklasse: Senatsverwaltung für Stadtentwicklung, Bauen und Wohnen, Monitoring Soziale Stadtentwicklung Berlin [Jahr]
Wohnflächen: OpenStreetMap, per QGIS-Plugin QuickOSM geladen (landuse=residential [weitere Werte ergänzen, falls verwendet]), Abruf am [Datum]
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
