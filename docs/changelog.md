# Änderungen

Build: 1.9.5b1 (18)<br>
Commit: [d92951332852bd641901a3097a639b28c516cc9d](https://github.com/harzmann/fleet_mde/commit/d92951332852bd641901a3097a639b28c516cc9d)<br>
Build-Zeitpunkt: 2026-06-08T09:39:48Z

# ChangeLog

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

