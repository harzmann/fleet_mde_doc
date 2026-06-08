# Installation der Testversion

Diese Anleitung richtet sich an die Kunden-IT.

## Voraussetzungen

- Android-Geraet mit Android 6 oder neuer.
- Netzwerkzugriff auf den FLEET Webservice.
- Webservice-URL, Benutzername und Passwort oder ein vorbereiteter QR-Code.
- Optional ADB fuer Installation und Diagnose.
- Bei Zebra-Geraeten: passendes DataWedge-Profil fuer Barcode-Scans.

## Download

1. APK herunterladen: [Fleet_MDE_1.9.5_377b8482.apk](https://github.com/harzmann/fleet_mde_doc/releases/download/customer-test-latest/Fleet_MDE_1.9.5_377b8482.apk)
2. Optional Pruefsumme herunterladen: [Fleet_MDE_1.9.5_377b8482.apk.sha256](https://github.com/harzmann/fleet_mde_doc/releases/download/customer-test-latest/Fleet_MDE_1.9.5_377b8482.apk.sha256)
3. SHA256 vergleichen:

`powershell
Get-FileHash -Algorithm SHA256 ".\Fleet_MDE_1.9.5_377b8482.apk"
`

Erwartete SHA256:

`	ext
1376dec2f77a25603921e9e7c056cb9b23d8e9995cf0ee1ff71d0b60594cd6a4
`

## Manuelle Installation

1. Vorhandene App-Version und aktuelle Einstellungen dokumentieren.
2. APK auf das Android-Geraet kopieren.
3. Installation aus unbekannten Quellen fuer die verwendete Datei-App, den Browser oder das MDM erlauben.
4. APK oeffnen und Installation bestaetigen.
5. App starten und angeforderte Berechtigungen erlauben.
6. Einstellungen oeffnen und Webservice-Zugangsdaten manuell oder per QR-Code setzen.
7. App neu starten und Funktionstest durchfuehren.

## Installation per ADB

`powershell
adb devices
adb install -r "Fleet_MDE_1.9.5_377b8482.apk"
`

## Funktionstest

- App-Version in den Einstellungen pruefen.
- Anmeldung testen.
- Webservice-Verbindung testen.
- Werkstattauftrag anlegen oder bearbeiten.
- Zeiterfassung mit direkter WA-Nr., Barcode-Scan und Auswahlliste testen.
- Scanner-/Kamera-Berechtigung pruefen.
- Fehlerfall ohne Netzwerk oder mit falschen Zugangsdaten pruefen.

## Rollback

Falls ein Rollback notwendig ist:

1. Aktuelle Testversion deinstallieren oder vorherige intern gesicherte APK installieren.
2. Wenn Android ein Downgrade blockiert, App deinstallieren und die vorherige APK neu installieren.
3. Webservice-Konfiguration danach erneut per Settings oder QR-Code setzen.

