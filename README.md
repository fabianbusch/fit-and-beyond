# fit-and-beyond

Fabians Sammlung rund um Training, Fitness und Wohlbefinden. Jedes Projekt liegt in einem eigenen Ordner.

## Projekte

| Projekt | Inhalt | Stand |
|---|---|---|
| [`comeback-training/`](comeback-training/) | Trainingsbegleiter für das Ganzkörper-Krafttraining zu Hause mit Kurzhantel, Hip-Band und Matte | v0.4 |

## Auslieferung

Die Apps laufen über GitHub Pages: **https://fabianbusch.github.io/fit-and-beyond/**

- Jeder Push auf `main` veröffentlicht automatisch, siehe [`.github/workflows/pages.yml`](.github/workflows/pages.yml).
- Ausgeliefert werden nur Dateien für den Browser. Markdown, `docs/` und `.github/` bleiben draußen.
- Jede App ist eine eigenständige HTML-Datei mit vollständigem Grundgerüst (`<!doctype html>`, Viewport-Angabe).
- **Achtung:** Eine Pages-Seite ist öffentlich erreichbar, auch wenn das Repo privat ist. Persönliche Daten landen deshalb nie im Repo, sondern nur im Browser (siehe Datenhaltung im jeweiligen Fachkonzept).

## Architektur und Datenschutz

Heute läuft alles lokal im Browser, ohne Server. Für die Zukunft gilt: kein zentraler Datenspeicher, Austausch von Gerät zu Gerät, Ende-zu-Ende-verschlüsselt, Zero Trust. Details und offene Fragen stehen in [`docs/architektur.md`](docs/architektur.md).

## Arbeitsweise: erst fachlich, dann technisch

In diesem Repo wird nichts implementiert, bevor es fachlich beschrieben und abgestimmt ist.

1. **Beschreiben:** Jede Änderung bekommt eine Spezifikation im Ordner `features/` des jeweiligen Projekts, nach der [Vorlage](docs/feature-vorlage.md).
2. **Abstimmen:** Die Spezifikation startet als `Entwurf`. Umgesetzt wird erst, wenn Fabian sie auf `Abgestimmt` setzt.
3. **Umsetzen:** Der Code folgt der Spezifikation. Weicht er ab, wird zuerst die Spezifikation angepasst.
4. **Abschließen:** Die Spezifikation steht danach auf `Umgesetzt`, und das Fachkonzept des Projekts beschreibt den neuen Stand.

Details stehen in [`docs/prozess.md`](docs/prozess.md).

## Aufbau

```
docs/                    Repo-weite Regeln
  prozess.md             Ablauf von der Idee bis zur Umsetzung
  feature-vorlage.md     Vorlage für Feature-Spezifikationen
  architektur.md         Ist-Stand und Zielbild der Architektur, Datenschutz-Leitlinien
<projekt>/
  fachkonzept.md         Fachlicher Ist-Stand inkl. Glossar
  features/              Eine Spezifikation pro Feature
  …                      Code des Projekts
```
