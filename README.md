# fit-and-beyond

Fabians Sammlung rund um Training, Fitness und Wohlbefinden. Jedes Projekt liegt in einem eigenen Ordner.

## Projekte

| Projekt | Inhalt | Stand |
|---|---|---|
| [`comeback-training/`](comeback-training/) | Trainingsbegleiter für das Ganzkörper-Krafttraining zu Hause mit Kurzhantel, Hip-Band und Matte | v0.4 |

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
<projekt>/
  fachkonzept.md         Fachlicher Ist-Stand inkl. Glossar
  features/              Eine Spezifikation pro Feature
  …                      Code des Projekts
```
