# Tracker
Calorie Tracker

Ein einfacher Kalorientracker als einzelne HTML-Datei – keine Installation, kein Server nötig.

## Nutzung

`index.html` im Browser öffnen. Alle Daten werden lokal im Browser (localStorage) gespeichert.

Für den Barcode-Scanner per Kamera muss die Seite über HTTPS laufen (z. B. GitHub Pages) –
Browser geben die Kamera sonst nicht frei. Ohne Kamera kann die Nummer unter dem Barcode
auch von Hand eingegeben werden.

## Funktionen

- Einträge nach Mahlzeit (Frühstück, Mittagessen, Abendessen, Snacks) mit Kalorien, Eiweiß, Kohlenhydraten und Fett
- Lebensmittelsuche (Werte pro 100 g): Menge in Gramm eingeben, Nährwerte werden automatisch berechnet
- **Bundeslebensmittelschlüssel (BLS)** des Max Rubner-Instituts: Datei (Excel oder CSV) von
  [blsdb.de](https://www.blsdb.de) herunterladen und unter *Einstellungen → BLS-Datei importieren* einlesen.
  Spalten werden automatisch erkannt (BLS-Kürzel wie `ST`, `GCAL`, `ZE`, `ZK`, `ZF` oder Klartext-Überschriften),
  Angaben in mg/100 g werden umgerechnet.
- **Barcode-Scanner**: Produktcode mit der Kamera scannen, Nährwerte kommen aus
  [Open Food Facts](https://world.openfoodfacts.org) (ODbL). Gescannte Produkte werden lokal gespeichert.
- Eigene Lebensmittel werden gemerkt und stehen später zur Auswahl
- Tagesübersicht mit Fortschrittsring und Makro-Balken
- Navigation zwischen Tagen und Verlauf der letzten 7 Tage
- Bedarfsrechner (Mifflin-St-Jeor) zum Festlegen von Kalorien- und Makrozielen
- Export/Import der Daten als JSON

## Bibliotheken

In `vendor/` liegen, jeweils mit Lizenzdatei:

- [ZXing](https://github.com/zxing-js/library) 0.21.3 (MIT) – Barcode-Erkennung in Browsern ohne `BarcodeDetector`
- [SheetJS](https://sheetjs.com) 0.18.5 (Apache-2.0) – Einlesen der BLS-Datei

Beide werden erst geladen, wenn sie gebraucht werden.
