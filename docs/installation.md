# Installation der Testversion

Diese Anleitung richtet sich an die Kunden-IT.

## Voraussetzungen

- Android-Gerät mit Android 6 oder neuer.
- Netzwerkzugriff auf den FLEET Webservice.
- Webservice-URL, Benutzername und Passwort oder ein vorbereiteter QR-Code.
- Optional ADB für Installation und Diagnose.
- Bei Zebra-Geräten: passendes DataWedge-Profil für Barcode-Scans.

## Download

1. APK herunterladen: [Fleet_MDE_1.9.5b3_1d0d1c0b.apk](https://github.com/harzmann/fleet_mde_doc/releases/download/customer-test-latest/Fleet_MDE_1.9.5b3_1d0d1c0b.apk)
2. Optional Prüfsumme herunterladen: [Fleet_MDE_1.9.5b3_1d0d1c0b.apk.sha256](https://github.com/harzmann/fleet_mde_doc/releases/download/customer-test-latest/Fleet_MDE_1.9.5b3_1d0d1c0b.apk.sha256)
3. SHA256 vergleichen:

`powershell
Get-FileHash -Algorithm SHA256 ".\Fleet_MDE_1.9.5b3_1d0d1c0b.apk"
`

Erwartete SHA256:

`	ext
2d12b42775e7cca17d2b5654b1befee452267e99d3e574d00a08a4da9fdf474f
`

## Manuelle Installation

1. Vorhandene App-Version und aktuelle Einstellungen dokumentieren.
2. APK auf das Android-Gerät kopieren.
3. Installation aus unbekannten Quellen für die verwendete Datei-App, den Browser oder das MDM erlauben.
4. APK öffnen und Installation bestätigen.
5. App starten und angeforderte Berechtigungen erlauben.
6. Einstellungen öffnen und Webservice-Zugangsdaten manuell oder per QR-Code setzen.
7. App neu starten und Funktionstest durchführen.

## Installation per ADB

`powershell
adb devices
adb install -r "Fleet_MDE_1.9.5b3_1d0d1c0b.apk"
`

## Funktionstest

- App-Version in den Einstellungen prüfen.
- Anmeldung testen.
- Webservice-Verbindung testen.
- Werkstattauftrag anlegen oder bearbeiten.
- Zeiterfassung mit direkter WA-Nr., Barcode-Scan und Auswahlliste testen.
- Scanner-/Kamera-Berechtigung prüfen.
- Fehlerfall ohne Netzwerk oder mit falschen Zugangsdaten prüfen.

## Rollback

Falls ein Rollback notwendig ist:

1. Aktuelle Testversion deinstallieren oder vorherige intern gesicherte APK installieren.
2. Wenn Android ein Downgrade blockiert, App deinstallieren und die vorherige APK neu installieren.
3. Webservice-Konfiguration danach erneut per Settings oder QR-Code setzen.

