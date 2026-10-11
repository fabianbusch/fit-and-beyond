# 007 – Alternative Übung per Swipe

**Status:** Entwurf
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Slide for Alternative → Alternative Übung nach Tinder-Art, max. 2 mal“
**Hängt zusammen mit:** 001 (Protokoll, Letztes Mal), 002 (Los), 005 (Burner)

## Problem

Manchmal passt eine Übung an dem Tag nicht: Das Handgelenk zwickt bei Liegestützen, die Übung ist langweilig geworden, oder es fehlt ein Stuhl. Heute gibt es dann nur „machen“ oder „weglassen“.

## Ziel

Eine Übung lässt sich vor dem Start mit einer Wischgeste gegen eine gleichwertige Alternative tauschen. Pro Training gibt es dafür **zwei Joker**, damit das Training nicht zum Durchblättern wird.

## Neue Begriffe

- **Alternative:** eine Übung, die dieselbe Hauptmuskulatur mit demselben Bewegungsmuster trainiert und nur vorhandene Hilfsmittel nutzt.
- **Variante:** die Original-Übung oder eine ihrer Alternativen.
- **Joker:** ein Wechsel zu einer noch nicht gezeigten Variante. Pro Einheit gibt es 2 Joker.

## Scope

**Drin:**
- Pro Zirkel-Übung eine feste Liste von 2 Alternativen
- Wechsel des Burners innerhalb der Burner-Liste aus 005
- Zwei Joker pro Einheit, frei verteilbar
- Zurückwischen ohne Joker-Verbrauch
- Wechsel per Wischgeste, zusätzlich per Knopf
- Erfassung im Protokoll, welche Variante tatsächlich gemacht wurde (001)

**Nicht drin:**
- Alternativen für Aufwärmen und Abschluss
- Dauerhaftes Ersetzen im Plan (siehe offene Frage 2)
- Eigene Übungen anlegen

## Fachliche Regeln

### Bedienung

1. **Geste:** Nach links wischen heißt „Andere Übung zeigen“. Die Karte fliegt raus, und die nächste Variante erscheint. Nach rechts wischen holt die vorherige Variante zurück.
2. **Knöpfe:** Sichtbare Schaltflächen „Alternative“ und „Zurück“ tun dasselbe wie die Gesten, für Desktop und Barrierefreiheit.
3. **Inhalt einer Variante:** Jede Alternative hat alle Angaben einer normalen Übung: Ablauf, Hilfsmittel, Muskeln, Dosierung, Tipp, und bei Hantelübungen ein eigenes Gewichtsfeld.

### Joker

4. **Zwei Joker pro Einheit:** Das Limit gilt für das ganze Training, nicht pro Übung. Die Joker sind frei verteilbar, z. B. zweimal bei einer Übung oder je einmal bei zwei Übungen.
5. **Was einen Joker kostet:** Ein Joker wird verbraucht, wenn bei einer Übung eine Variante zum **ersten Mal** angezeigt wird.
6. **Zurück ist frei:** Zurückwischen zum Original oder zu einer bereits gezeigten Variante kostet keinen Joker. Ein Wisch ist also nicht endgültig. Ein verbrauchter Joker kommt durch Zurückwischen aber nicht zurück.
7. **Anzeige:** Die verbleibenden Joker sind sichtbar, z. B. „Joker: 1 von 2“, an der Übungskarte und im Kopf der Seite.
8. **Keine Joker mehr:** Sind beide Joker verbraucht, ist „Alternative“ bei allen Übungen gesperrt. Zurückwischen zu bereits gezeigten Varianten bleibt möglich.

### Zeitpunkt

9. **Nur vor dem Anfangen:** Gewechselt werden kann nur, solange die Übung noch nicht angefangen wurde. Sobald für den ersten Satz der Übung „Los“ gedrückt wurde (002), steht die Variante fest, damit die Sätze vergleichbar bleiben.
10. **Abbrechen gibt frei:** Wird dieser erste Satz über „Abbrechen“ zurückgesetzt (002, Regel 10), ist die Übung wieder nicht angefangen, und Wechseln ist wieder möglich.

### Burner

11. **Burner-Liste als Variantenpool:** Beim Burner (005) sind die vier Burner der Liste die Varianten. Start ist der von der App vorgeschlagene Burner, links wischen zeigt den nächsten in der Reihenfolge des Vorschlags.
12. **Gleiche Joker:** Ein Burner-Wechsel verbraucht dieselben zwei Joker. Einen separaten Burner-Wechsel gibt es nicht.
13. **Zeitpunkt beim Burner:** Wie bei allen Übungen bis zum ersten „Los“ des Burners.

### Protokoll

14. **Tatsächliche Variante:** Werte werden der Variante zugeordnet, die tatsächlich gemacht wurde (001). Das Protokoll hält zusätzlich fest, für welche Original-Übung sie eingesetzt wurde.
15. **„Letztes Mal“ und Vorbelegung:** Beide beziehen sich auf die gerade angezeigte Variante, also auf die letzte Einheit, in der genau diese Variante gemacht wurde (001, Regel 5 und 10). Gibt es keinen Vorwert, gilt die Obergrenze ihrer Plan-Spanne.
16. **Einseitige und zeitbasierte Varianten:** Ist eine Variante einseitig oder zeitbasiert, z. B. Seitstütz pro Seite, gelten die Regeln dafür aus 001, 002 und 006, auch wenn das Original anders war.

### Katalog

17. **Alternativen-Katalog (Vorschlag):**

   | Übung | Alternative 1 | Alternative 2 |
   |---|---|---|
   | Goblet Squat | Rückwärts-Ausfallschritt mit Hantel | Sumo-Kniebeuge mit Hantel |
   | Liegestütze | Floor Press (Hantel im Liegen drücken) | Erhöhte Liegestütze, Hände auf einem Stuhl |
   | Einarmiges Rudern | Kurzhantel-Pullover am Boden | Y-T-W-Heben in Bauchlage, ohne Gewicht |
   | Glute Bridge mit Band | Einbeinige Hüftbrücke | Hüftbrücke mit Hantel auf dem Becken |
   | Einarmiges Schulterdrücken | Pike-Liegestütze | Einarmiges Arnold Press |
   | Seitliche Band-Walks | Clamshells mit Band | Monster Walks mit Band (diagonal) |
   | Unterarmstütz | Dead Bug | Seitstütz, pro Seite |
   | Burner | die vier Burner aus 005 | |

## Akzeptanzkriterien

- [ ] Auf dem Handy lässt sich eine Übungskarte nach links wischen, und die Alternative erscheint mit allen Angaben.
- [ ] Nach zwei Wechseln im ganzen Training ist bei keiner Übung mehr ein Wechsel zu einer neuen Variante möglich, und das ist erkennbar.
- [ ] Die zwei Joker lassen sich auf zwei verschiedene Übungen verteilen oder bei einer Übung beide nutzen.
- [ ] Zurückwischen zum Original verbraucht keinen Joker.
- [ ] Nach dem ersten „Los“ einer Übung ist Wechseln für diese Übung gesperrt.
- [ ] Der Burner-Vorschlag lässt sich gegen einen anderen Burner der Liste tauschen, und das kostet einen der zwei Joker.
- [ ] Die gewählte Variante erscheint im Protokoll unter ihrem eigenen Namen, mit Verweis auf die Original-Übung.
- [ ] Der Wechsel funktioniert auch ohne Geste über die Schaltflächen.

## Offene Fragen

1. **Katalog:** Passen die Alternativen? Für jede Alternative fehlen noch Dosierung und Ablauf, z. B. ob der Rückwärts-Ausfallschritt pro Seite gezählt wird. Die Kurzhantel-Varianten brauchen teils ein anderes Gewicht, wodurch du Scheiben umbauen musst.
2. **Merken:** Soll eine Alternative, die du mehrfach wählst, irgendwann vorgeschlagen werden, den Plan dauerhaft zu ändern?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | „Max. 2 mal“ gilt als zwei Joker fürs ganze Training, frei verteilbar | Genug Spielraum für schlechte Tage, ohne dass das Training zum Durchblättern wird |
| 2026-10-12 | Der Burner-Wechsel zählt in dieselben zwei Joker, die Burner-Liste aus 005 ist sein Variantenpool | Einfach halten, eine Regel für alles |
| 2026-10-12 | Zurückwischen ist erlaubt und kostet keinen Joker | Entspannter bei Vertippen oder Umentscheiden |
| 2026-10-12 | Wechseln nur, solange die Übung nicht angefangen ist, also bis zum ersten „Los“ | Die Sätze einer Übung bleiben vergleichbar |
