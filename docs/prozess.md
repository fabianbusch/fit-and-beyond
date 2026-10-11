# Prozess: von der Idee zur Umsetzung

## Grundregel

Fachlichkeit vor Technik. Kein Code ohne abgestimmte Spezifikation.

## Statuswerte einer Feature-Spezifikation

| Status | Bedeutung | Wer wechselt |
|---|---|---|
| `Entwurf` | Idee ist aufgeschrieben, Fragen sind noch offen | Claude oder Fabian |
| `Abgestimmt` | Scope, Regeln und Akzeptanzkriterien sind von Fabian freigegeben | nur Fabian |
| `In Umsetzung` | Code wird geschrieben | Claude |
| `Umgesetzt` | Akzeptanzkriterien sind erfüllt, Fachkonzept ist nachgezogen | Claude, nach Prüfung durch Fabian |
| `Verworfen` | Wird nicht gemacht, Begründung steht in der Spezifikation | Fabian |

## Ablauf

1. **Feedback sammeln:** Fabian gibt Feedback oder Wünsche.
2. **Spezifikation schreiben:** Claude legt pro Feature eine Datei `<projekt>/features/NNN-kurzname.md` nach der [Vorlage](feature-vorlage.md) an und trägt sie in die Feature-Tabelle im README des Projekts ein. Offene Fragen stehen ausdrücklich im Abschnitt „Offene Fragen“.
3. **Klären:** Offene Fragen werden besprochen, bis keine mehr übrig sind.
4. **Freigeben:** Fabian setzt den Status auf `Abgestimmt` oder sagt es im Chat.
5. **Umsetzen:** Ein Commit oder Pull Request pro Feature, mit Verweis auf die Spezifikation.
6. **Prüfen:** Fabian prüft die Akzeptanzkriterien im Training.
7. **Nachziehen:** `<projekt>/fachkonzept.md` beschreibt danach den neuen Ist-Stand.

## Nummerierung

Features werden pro Projekt fortlaufend dreistellig nummeriert (`001`, `002`, …). Verworfene Nummern werden nicht neu vergeben.

## Fachliche Begriffe

Begriffe aus der Trainingsplanung werden einheitlich verwendet, wie im Glossar des jeweiligen Fachkonzepts definiert, z. B. [Comeback-Training](../comeback-training/fachkonzept.md#glossar). Neue Begriffe kommen zuerst ins Glossar.
