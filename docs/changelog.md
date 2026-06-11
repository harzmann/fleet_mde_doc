# Änderungen

Build: 1.9.5b3 (20)<br>
Commit: [1d0d1c0b33cf40da02572a9ea94b476ba6a38e31](https://github.com/harzmann/fleet_mde/commit/1d0d1c0b33cf40da02572a9ea94b476ba6a38e31)<br>
Build-Zeitpunkt: 2026-06-11T10:17:21Z

# ChangeLog

## 2026-06-11 - 1.9.5b3

### Lagerbestand
- Der Menuepunkt `Lagerbestand` ist im Hauptmenue wieder aktiv und oeffnet eine eigene read-only Lagerbestandsuebersicht.
- Lagerbestaende werden ueber die vorhandenen Webservice-Daten geladen und nach Artikel ID, Artikel Matchcode/Bezeichnung sowie Lagerstelle gefiltert.
- Artikel ID und Artikel Matchcode verwenden die gleiche Anordnung mit Barcode-Schaltflaechen wie im Lagerzugang.
- Die Artikel-ID-Eingabe oeffnet eine numerische Tastatur.
- Die Artikel-Matchcode-Lupe oeffnet die Artikelauswahl analog zum Lagerzugang und uebernimmt den ausgewaehlten Artikel in die Filter.
- Die Ergebnisliste aktualisiert sich direkt waehrend der Eingabe; `Neu laden` setzt die Eingaben zurueck und laedt die Daten neu.

### Pruefung
- Der Debug-Build wurde mit `.\gradlew.bat :app:assembleDebug` erfolgreich geprueft.

## 2026-06-10 - 1.9.5b2

### Lagerzugang Einkauf
- Der Lagerzugang ist ueber das Hauptmenue wieder aktiv aufrufbar und verwendet den gleichen aktiven Button-Stil wie die uebrigen Hauptfunktionen.
- Die Lieferantenauswahl wurde auf ein kombiniertes Such- und Dropdown-Feld umgestellt.
- Lieferanten koennen nach Lieferanten-Nr., KreditorNr. und Lieferantenname gesucht und ueber eine Auswahlliste ausgewaehlt werden.
- Lieferanten-Barcodes werden gegen die geladene Lieferantenliste aufgeloest.
- Lagerzugaenge werden ueber `CreateReceiptPosition` gebucht; die zuletzt erfolgreich gebuchte Position kann ueber `DeleteReceiptPosition` geloescht werden.
- Der Statusbereich zeigt nach Buchung oder Loeschung den letzten Vorgang der aktuellen Sitzung an.

### Bedienung und Layout
- Die Lagerzugang-Maske wurde an die Artikelerfassung im Werkstattauftrag angeglichen.
- Artikel-ID, Artikel-Matchcode, Lieferant, Menge, E-Preis und die Aktionsbuttons wurden in Ausrichtung und Bedienlogik vereinheitlicht.
- Die separate Artikel-ID-Lupe wurde in Lagerzugang und Werkstattauftrag entfernt; Suche per Enter und Barcode bleibt erhalten.
- Fuer Lieferanten wurde eine eigene Lupen-Schaltflaeche mit gefilterter Auswahlliste ergaenzt.

### Webservice
- `DeleteReceiptPosition` wurde im Webservice-Wrapper ergaenzt.

### Pruefung
- Der Debug-Build wurde mit `.\gradlew.bat assembleDebug` erfolgreich geprueft.

## 2026-05-20

### Werkstattaufträge
- Der Bereich `Werkstattauftrag` wurde um einen neuen Zwischen-Screen erweitert. Anwender können dort zwischen `Auftrag anlegen`, `Auftrag bearbeiten` und `Artikel erfassen` wählen.
- Neue Werkstattaufträge können direkt in der App angelegt werden. Die Anlage nutzt die Fahrzeugliste aus dem Webservice, unterstützt die Suche nach KFZ-Nr. und Kennzeichen und übergibt die Daten an `CreateOrder`.
- Offene Werkstattaufträge können bearbeitet werden. Die App zeigt eine filterbare Liste offener Aufträge, öffnet den gewählten Auftrag in einem Bearbeiten-Screen und speichert Änderungen über `UpdateOrder`.
- Die bestehende Artikelerfassung für Werkstattaufträge bleibt erhalten und ist weiterhin über den neuen Zwischen-Screen erreichbar.

### Zeiterfassung
- Werkstattaufträge können in der Zeiterfassung nun zusätzlich über eine filterbare Auswahlliste ausgewählt werden.
- Die Auswahl nutzt die bereits geladenen offenen Werkstattaufträge und filtert per Teilsuchbegriff nach KFZ-Nr. oder Kennzeichen.
- Direkte WA-Nr.-Eingabe und Barcode-Scan bleiben unverändert nutzbar.

### Bedienung
- Fahrzeug- und Auftragsauswahl wurden vereinheitlicht: KFZ-Nr. und Kennzeichen können über kombinierte Suchfelder gefunden werden.
- Die Liste offener Werkstattaufträge wurde für mobile Geräte verbessert und scrollt im verfügbaren Bildschirmbereich.
- Anzeigen für Fahrzeug und Datum wurden vereinheitlicht: Fahrzeugdaten erscheinen als `KFZ-Nr. / Kennzeichen`, WA-Daten ohne Uhrzeit.

### Webservice
- Die Verarbeitung von Webservice-Antworten wurde robuster gemacht, insbesondere bei variabler Feldanzahl, SOAP-Fehlern, optionalen Feldern und Datumswerten.
- Datumswerte werden für Anlage und Bearbeitung so formatiert, dass ungültige XML-Zeiten wie `24:00:00` vermieden werden.
- Leere optionale Felder werden beim Senden geeignet behandelt, damit sie serverseitig als leer bzw. `null` verarbeitet werden können.

### Android
- Manifest-Hinweise zu SDK-Angaben, Kamera/NFC-Features und Barcode-Scanner-Orientation wurden bereinigt.

### Prüfung
- Der Debug-Build wurde mit `.\gradlew.bat assembleDebug` erfolgreich geprüft.

