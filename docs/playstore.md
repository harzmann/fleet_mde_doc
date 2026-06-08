# PlayStore Deployment

Das PlayStore Deployment erfolgt bewusst nicht automatisch bei einem Commit oder Push.

## Ablauf

1. Im privaten Repo den GitHub Actions Workflow playstore-release.yml manuell starten.
2. Release-Name, Track und Rollout-Prozentwert eingeben.
3. Workflow pruefen und Play Console oeffnen.
4. Review-Status, Crashs und ANRs kontrollieren.
5. Rollout manuell erhoehen, wenn keine Blocker auftreten.

## Wichtig

- Normale Pushes erzeugen nur die Kunden-Testversion.
- PlayStore Uploads werden ausschliesslich ueber workflow_dispatch gestartet.
- Vor dem Upload muss der ersionCode hoeher sein als der aktuelle PlayStore-Stand.

