# 007 – Alternative Übung per Swipe

**Status:** Entwurf
**Erstellt:** 2026-10-11
**Bezug:** Handzettel „Slide for Alternative → Alternative Übung nach Tinder-Art, max. 2 mal“

## Problem

Manchmal passt eine Übung an dem Tag nicht: Das Handgelenk zwickt bei Liegestützen, die Übung ist langweilig geworden, oder es fehlt ein Stuhl. Heute gibt es dann nur „machen“ oder „weglassen“.

## Ziel

Eine Übung lässt sich vor dem Start mit einer Wischgeste gegen eine gleichwertige Alternative tauschen, mit höchstens 2 Wechseln, damit das Training nicht zum Durchblättern wird.

## Neuer Begriff

**Alternative:** eine Übung, die dieselbe Hauptmuskulatur mit demselben Bewegungsmuster trainiert und nur vorhandene Hilfsmittel nutzt.

## Scope

**Drin:**
- Pro Zirkel-Übung eine feste Liste von 2 Alternativen
- Wechsel per Wischgeste auf der Übungskarte, zusätzlich per Knopf
- Wechsel gilt für die laufende Einheit
- Erfassung im Protokoll, welche Übung tatsächlich gemacht wurde (001)

**Nicht drin:**
- Alternativen für Aufwärmen und Abschluss
- Dauerhaftes Ersetzen im Plan (möglich als Folgefeature)
- Eigene Übungen anlegen

## Fachliche Regeln

1. **Geste:** Nach links wischen heißt „Andere Übung zeigen“, die Karte fliegt raus und die nächste Alternative erscheint. Eine sichtbare Schaltfläche „Alternative“ macht dasselbe, für Desktop und Barrierefreiheit.
2. **Limit:** Pro Übung und Einheit sind höchstens 2 Wechsel möglich. Danach steht die zuletzt gezeigte Übung fest. Die Karte zeigt die verbleibenden Wechsel an, z. B. „1 Alternative übrig“. Siehe offene Frage 1.
3. **Zurück zum Original:** Nach rechts wischen holt die vorherige Variante zurück, ohne einen Wechsel zu verbrauchen. Siehe offene Frage 2.
4. **Zeitpunkt:** Gewechselt werden kann nur, solange noch kein Satz dieser Übung erledigt ist. Sonst wären die Sätze nicht vergleichbar.
5. **Inhalt der Alternative:** Sie hat alle Angaben einer normalen Übung: Ablauf, Hilfsmittel, Muskeln, Dosierung, Tipp.
6. **Protokoll und „Letztes Mal“:** Werte werden der tatsächlich gemachten Übung zugeordnet. „Letztes Mal“ zeigt den Wert der Variante, die gerade angezeigt wird.
7. **Alternativen-Katalog (Vorschlag):**

   | Übung | Alternative 1 | Alternative 2 |
   |---|---|---|
   | Goblet Squat | Rückwärts-Ausfallschritt mit Hantel | Sumo-Kniebeuge mit Hantel |
   | Liegestütze | Floor Press (Hantel im Liegen drücken) | Erhöhte Liegestütze, Hände auf einem Stuhl |
   | Einarmiges Rudern | Kurzhantel-Pullover am Boden | Y-T-W-Heben in Bauchlage, ohne Gewicht |
   | Glute Bridge mit Band | Einbeinige Hüftbrücke | Hüftbrücke mit Hantel auf dem Becken |
   | Einarmiges Schulterdrücken | Pike-Liegestütze | Einarmiges Arnold Press |
   | Seitliche Band-Walks | Clamshells mit Band | Monster Walks mit Band (diagonal) |
   | Unterarmstütz | Dead Bug | Seitstütz, pro Seite |

## Akzeptanzkriterien

- [ ] Auf dem Handy lässt sich eine Übungskarte nach links wischen, und die Alternative erscheint mit allen Angaben.
- [ ] Nach 2 Wechseln ist kein weiterer Wechsel möglich, und das ist erkennbar.
- [ ] Nach dem ersten erledigten Satz ist Wechseln gesperrt.
- [ ] Die gewählte Alternative erscheint im Protokoll unter ihrem eigenen Namen.
- [ ] Der Wechsel funktioniert auch ohne Geste über die Schaltfläche.

## Offene Fragen

1. **„Max. 2 mal“:** Gilt das pro Übung, wie hier angenommen, oder für die ganze Einheit, z. B. 2 Joker insgesamt?
2. **Zurückwischen:** Soll man zum Original zurück können, oder ist ein Wisch endgültig wie bei Tinder?
3. **Katalog:** Passen die Alternativen? Die Kurzhantel-Varianten brauchen teils ein anderes Gewicht, wodurch du Scheiben umbauen musst.
4. **Merken:** Soll eine Alternative, die du mehrfach wählst, irgendwann vorgeschlagen werden, den Plan dauerhaft zu ändern?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| | | |
