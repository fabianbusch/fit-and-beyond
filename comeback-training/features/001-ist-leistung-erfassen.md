# 001 – Ist-Leistung erfassen

**Status:** Entwurf
**Erstellt:** 2026-10-11
**Bezug:** Handzettel „Option Notiz, wie viel ich wirklich gemacht habe (Score) → für Planung next Training“

## Problem

Der Plan gibt Spannen vor (z. B. 10–12 Wdh.). Was wirklich geschafft wurde, geht verloren. Im ersten Training hat Fabian überall 2 Wiederholungen mehr gemacht, die App weiß davon nichts. Damit fehlt die Grundlage, das nächste Training sinnvoll zu planen.

## Ziel

Nach jedem Satz lässt sich mit wenigen Taps festhalten, was tatsächlich geleistet wurde. Die Einheit wird als **Trainingsprotokoll** gespeichert. Beim nächsten Training sieht Fabian pro Übung, was er letztes Mal geschafft hat.

## Scope

**Drin:**
- Ist-Wert pro Satz in Zirkel-Blöcken (A–C)
- Gewicht pro Übung bei Hantelübungen
- Speichern der Einheit als Trainingsprotokoll mit Datum
- Anzeige „Letztes Mal“ pro Übung
- Liste vergangener Einheiten (Datum, Dauer, erledigte Sätze)

**Nicht drin:**
- Automatische Steigerungsvorschläge (eigenes Feature, baut hierauf auf)
- Diagramme und Auswertungen über Wochen
- Synchronisierung zwischen Geräten
- Erfassung für Aufwärmen und Abschluss

## Fachliche Regeln

1. **Messgröße je Übung:** Die Ist-Leistung wird in der Einheit der Dosierung erfasst:
   - Wiederholungen: Goblet Squat, Liegestütze, Rudern, Glute Bridge, Schulterdrücken
   - Schritte: Band-Walks
   - Sekunden: Unterarmstütz
2. **Übungen pro Seite:** Rudern und Schulterdrücken erfassen einen Wert, der für beide Seiten gilt. Siehe offene Frage 4.
3. **Gewicht:** Hantelübungen (Goblet Squat, Rudern, Schulterdrücken) haben ein Gewichtsfeld in kg, in 0,5-kg-Schritten. Das Gewicht gilt für alle Sätze der Übung, solange es nicht geändert wird.
4. **Vorbelegung:** Das Eingabefeld ist vorbelegt mit dem Ist-Wert desselben Satzes aus der letzten Einheit. Gibt es noch keinen, mit der oberen Grenze der Plan-Spanne. Siehe offene Frage 2.
5. **Schnellweg:** Wird ein Satz ohne Änderung abgehakt, gilt der vorbelegte Wert als geleistet. Der typische Fall braucht also keinen zusätzlichen Tap.
6. **Anpassen:** Über „−“ und „+“ neben dem Wert lässt er sich in Einerschritten ändern, bei Sekunden in 5er-Schritten. Das geht auch nachträglich, solange die Einheit nicht abgeschlossen ist.
7. **Einheit abschließen:** Sind alle Pflichtsätze erledigt, bietet die App „Einheit abschließen“ an. Erst dann wird das Protokoll endgültig gespeichert, und der Tagesfortschritt wird zurückgesetzt.
8. **Abgebrochene Einheit:** Ist eine Einheit nach 12 Stunden noch nicht abgeschlossen, wird sie beim nächsten Öffnen als „abgebrochen“ mit den bis dahin erfassten Sätzen gespeichert.
9. **Letztes Mal:** Jede Übungskarte zeigt eine Zeile wie „Letztes Mal: 12 · 12 · 11 Wdh. mit 10 kg“, sobald ein Protokoll existiert.
10. **Datenhaltung:** Siehe Abschnitt „Rahmenbedingungen“ im Fachkonzept. Alles bleibt lokal im Browser.

## Akzeptanzkriterien

- [ ] Fabian kann im Training jeden Satz mit höchstens einem zusätzlichen Tap von der Vorbelegung abweichend erfassen.
- [ ] Nach „Einheit abschließen“ erscheint die Einheit mit Datum in der Verlaufsliste.
- [ ] Beim nächsten Öffnen zeigt jede Zirkel-Übung „Letztes Mal“ mit den Werten aller 3 Sätze und dem Gewicht.
- [ ] Die Felder sind beim nächsten Training mit den Werten der letzten Einheit vorbelegt.
- [ ] Nach Neuladen der Seite mitten im Training sind die bereits erfassten Werte noch da.

## Offene Fragen

1. **Anstrengung erfassen?** Zusätzlich pro Satz eine Einschätzung wie „leicht / passend / am Limit“ oder Reserve-Wiederholungen (RIR 0–4)? Das wäre die beste Grundlage für Steigerungsvorschläge, kostet aber einen weiteren Tap.
2. **Vorbelegung ohne Vorwert:** obere Grenze der Spanne, untere Grenze oder leer?
3. **Freitext-Notiz:** Pro Übung oder pro Einheit ein Notizfeld, z. B. „linke Schulter zwickt“?
4. **Seiten getrennt?** Rudern und Schulterdrücken links und rechts getrennt erfassen? Genauer, aber doppelte Eingabe.
5. **Sicherung:** Daten im Browser können beim Leeren des Browsers verloren gehen. Soll es einen Export als Datei geben, um das abzusichern?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-11 | Daten lokal im Browser | Vorgabe Fabian: erst lokal, bis es ein echtes Backend gibt |
