# Aenderungen

Build: $VersionName ($VersionCode)  
Commit: [377b848204ce7f531e07c70ecdd5fe0231de95dc](https://github.com/harzmann/fleet_mde/commit/377b848204ce7f531e07c70ecdd5fe0231de95dc)  
Build-Zeitpunkt: $BuildTimeUtc

# ChangeLog

## 2026-05-20

### Werkstattauftraege
- Der Bereich `Werkstattauftrag` wurde um einen neuen Zwischen-Screen erweitert. Anwender koennen dort zwischen `Auftrag anlegen`, `Auftrag bearbeiten` und `Artikel erfassen` waehlen.
- Neue Werkstattauftraege koennen direkt in der App angelegt werden. Die Anlage nutzt die Fahrzeugliste aus dem Webservice, unterstuetzt die Suche nach KFZ-Nr. und Kennzeichen und uebergibt die Daten an `CreateOrder`.
- Offene Werkstattauftraege koennen bearbeitet werden. Die App zeigt eine filterbare Liste offener Auftraege, oeffnet den gewaehlten Auftrag in einem Bearbeiten-Screen und speichert Aenderungen ueber `UpdateOrder`.
- Die bestehende Artikelerfassung fuer Werkstattauftraege bleibt erhalten und ist weiterhin ueber den neuen Zwischen-Screen erreichbar.

### Zeiterfassung
- Werkstattauftraege koennen in der Zeiterfassung nun zusaetzlich ueber eine filterbare Auswahlliste ausgewaehlt werden.
- Die Auswahl nutzt die bereits geladenen offenen Werkstattauftraege und filtert per Teilsuchbegriff nach KFZ-Nr. oder Kennzeichen.
- Direkte WA-Nr.-Eingabe und Barcode-Scan bleiben unveraendert nutzbar.

### Bedienung
- Fahrzeug- und Auftragsauswahl wurden vereinheitlicht: KFZ-Nr. und Kennzeichen koennen ueber kombinierte Suchfelder gefunden werden.
- Die Liste offener Werkstattauftraege wurde fuer mobile Geraete verbessert und scrollt im verfuegbaren Bildschirmbereich.
- Anzeigen fuer Fahrzeug und Datum wurden vereinheitlicht: Fahrzeugdaten erscheinen als `KFZ-Nr. / Kennzeichen`, WA-Daten ohne Uhrzeit.

### Webservice
- Die Verarbeitung von Webservice-Antworten wurde robuster gemacht, insbesondere bei variabler Feldanzahl, SOAP-Fehlern, optionalen Feldern und Datumswerten.
- Datumswerte werden fuer Anlage und Bearbeitung so formatiert, dass ungueltige XML-Zeiten wie `24:00:00` vermieden werden.
- Leere optionale Felder werden beim Senden geeignet behandelt, damit sie serverseitig als leer bzw. `null` verarbeitet werden koennen.

### Android
- Manifest-Hinweise zu SDK-Angaben, Kamera/NFC-Features und Barcode-Scanner-Orientation wurden bereinigt.

### Pruefung
- Der Debug-Build wurde mit `.\gradlew.bat assembleDebug` erfolgreich geprueft.

