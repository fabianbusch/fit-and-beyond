# 001 – Ist-Leistung erfassen

**Status:** Entwurf
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Option Notiz, wie viel ich wirklich gemacht habe (Score) → für Planung next Training“

## Problem

Der Plan gibt Spannen vor (z. B. 10–12 Wdh.). Was wirklich geschafft wurde, geht verloren. Im ersten Training hat Fabian überall 2 Wiederholungen mehr gemacht, die App weiß davon nichts. Damit fehlt die Grundlage, das nächste Training sinnvoll zu planen.

## Ziel

Nach jedem Satz lässt sich mit wenigen Taps festhalten, was tatsächlich geleistet wurde und wie anstrengend es war. Die Einheit wird als **Trainingsprotokoll** gespeichert. Beim nächsten Training sieht Fabian pro Übung, was er letztes Mal geschafft hat.

## Neue Begriffe

- **Ist-Wert:** die tatsächlich geleistete Menge eines Satzes, also Wiederholungen, Schritte oder Sekunden.
- **Anstrengung:** Einschätzung eines Satzes in drei Stufen: „leicht“, „passend“, „am Limit“.
- **Trainingsprotokoll:** gespeicherte Einheit mit Datum und allen Ist-Werten, Anstrengungen und Gewichten.

## Scope

**Drin:**
- Ist-Wert pro Satz in Zirkel-Blöcken (A–C)
- Anstrengung pro Satz
- Einseitige Übungen getrennt pro Seite
- Gewicht pro Übung bei Hantelübungen
- Speichern der Einheit als Trainingsprotokoll mit Datum
- Anzeige „Letztes Mal“ pro Übung
- Liste vergangener Einheiten (Datum, Dauer, erledigte Sätze)
- Export und Import aller persönlichen Daten als Datei („Daten sichern“, „Daten laden“)

**Nicht drin:**
- Freitext-Notizen. Bewusst weggelassen, kann später nachgerüstet werden.
- Automatische Steigerungsvorschläge (eigenes Feature, baut hierauf auf)
- Diagramme und Auswertungen über Wochen
- Synchronisierung zwischen Geräten
- Erfassung für Aufwärmen und Abschluss

## Fachliche Regeln

1. **Messgröße je Übung:** Der Ist-Wert wird in der Einheit der Dosierung erfasst:
   - Wiederholungen: Goblet Squat, Liegestütze, Rudern, Glute Bridge, Schulterdrücken
   - Schritte: Band-Walks
   - Sekunden: Unterarmstütz
2. **Einseitige Übungen:** Rudern und Schulterdrücken werden pro Seite getrennt erfasst. Jede Seite hat einen eigenen Ist-Wert und eine eigene Anstrengung. Ablauf im Training:
   - Erst die linke Seite ausführen und abhaken, dann direkt die rechte. Jede Seite startet mit einem eigenen „Los“ (siehe 002).
   - Zwischen den Seiten gibt es **keine Pause**.
   - Der Pausentimer startet erst, wenn beide Seiten erfasst sind.
   - Ein Satz einer einseitigen Übung gilt erst als erledigt, wenn beide Seiten erfasst sind.
3. **Anstrengung:** Direkt nach dem Abhaken eines Satzes, bei einseitigen Übungen einer Seite, erscheint daneben die Auswahl „leicht“, „passend“, „am Limit“.
   - Tippt Fabian eine Stufe, wird sie gespeichert. Danach startet die Pause, bei der ersten Seite einer einseitigen Übung geht es direkt zur zweiten Seite.
   - Tippt er keine Stufe, gilt der Satz nach **5 Sekunden** als „passend“, und es geht genauso weiter. Die verbleibende Wartezeit ist an der Auswahl sichtbar.
   - Die Anstrengung lässt sich nachträglich ändern, solange die Einheit nicht abgeschlossen ist.
4. **Gewicht:** Hantelübungen (Goblet Squat, Rudern, Schulterdrücken) haben ein Gewichtsfeld in kg, in 0,5-kg-Schritten. Das Gewicht gilt für alle Sätze und beide Seiten der Übung, solange es nicht geändert wird.
5. **Vorbelegung:** Das Ist-Wert-Feld ist vorbelegt:
   - mit dem Ist-Wert desselben Satzes, bei einseitigen Übungen derselben Seite, aus der letzten Einheit,
   - ohne Vorwert mit der **oberen Grenze** der Plan-Spanne, z. B. 12 beim Goblet Squat.
6. **Schnellweg:** Wird ein Satz ohne Änderung abgehakt und keine Anstrengung getippt, gelten Vorbelegung und „passend“. Der typische Fall braucht also keinen zusätzlichen Tap.
7. **Anpassen:** Über „−“ und „+“ neben dem Wert lässt er sich in Einerschritten ändern, bei Sekunden in 5er-Schritten. Das geht auch nachträglich, solange die Einheit nicht abgeschlossen ist.
8. **Einheit abschließen:** Sind alle Pflichtsätze erledigt, bietet die App „Einheit abschließen“ an. Erst dann wird das Protokoll endgültig gespeichert, und der Tagesfortschritt wird zurückgesetzt.
9. **Abgebrochene Einheit:** Ist eine Einheit nach 12 Stunden noch nicht abgeschlossen, wird sie beim nächsten Öffnen als „abgebrochen“ mit den bis dahin erfassten Sätzen gespeichert.
10. **Letztes Mal:** Jede Übungskarte zeigt eine Zeile wie „Letztes Mal: 12 · 12 · 11 Wdh. mit 10 kg“, sobald ein Protokoll existiert. Bei einseitigen Übungen getrennt, z. B. „L 10 · 10 · 9 / R 10 · 9 · 9 mit 8 kg“.
11. **Bezug zu 002 (Zeiten):** Bei einseitigen Übungen hat jede Seite ein eigenes „Los“ und eine eigene Übungszeit. Die Pausenzeit beginnt mit dem Abhaken der zweiten Seite. Die Zeit zwischen den Seiten ist Wechselzeit und zählt zur Übungszeit des Satzes, nicht zur Pause.
12. **Datenhaltung:** Siehe Abschnitt „Rahmenbedingungen“ im Fachkonzept. Alles bleibt lokal im Browser.
13. **Daten sichern (Export):** Ein Knopf „Daten sichern“ lädt eine Datei mit allen persönlichen Daten herunter: alle Trainingsprotokolle, die laufende Einheit und Einstellungen. Der Dateiname enthält das Datum, z. B. `comeback-training-2026-10-12.json`. Das Format ist geräteunabhängig und funktioniert auf Handy und Laptop.
14. **Daten laden (Import):** Ein Knopf „Daten laden“ liest eine solche Datei wieder ein.
    - Vor dem Übernehmen zeigt die App, was in der Datei steckt, z. B. „8 Einheiten vom 11.10. bis 02.11.“, und fragt nach Bestätigung.
    - Die Bestätigung weist deutlich darauf hin, dass die Daten auf diesem Gerät **ersetzt** werden, mit Anzahl der vorhandenen Einheiten, z. B. „Ersetzt deine 3 Einheiten auf diesem Gerät“.
    - Nach Bestätigung **ersetzt** der Inhalt der Datei den gesamten lokalen Datenbestand: Protokolle, laufende Einheit und Einstellungen. Es wird nichts zusammengeführt.
    - Ohne Bestätigung ändert sich nichts.
    - Ist die Datei keine gültige Sicherung, meldet die App das verständlich und ändert nichts.
    - **Möglicher späterer Ausbau:** „Zusammenführen“ für den Mehr-Geräte-Fall, also Einheiten aus der Datei ergänzen und Dubletten erkennen. Bewusst zurückgestellt.
15. **Ort der Knöpfe:** „Daten sichern“ und „Daten laden“ stehen bei der Verlaufsliste, nicht im Trainingsablauf.
16. **Hinweis Auslieferung:** Export funktioniert in der über GitHub Pages ausgelieferten App. Im Claude-Artefakt sind Downloads technisch gesperrt, dort ist nur der Import nutzbar.

## Akzeptanzkriterien

- [ ] Fabian kann im Training jeden Satz mit höchstens einem zusätzlichen Tap von der Vorbelegung abweichend erfassen.
- [ ] Nach dem Abhaken erscheint die Anstrengungsauswahl. Ein Tap auf eine Stufe startet die Pause.
- [ ] Ohne Tap auf eine Stufe startet die Pause nach kurzer Zeit von selbst, und der Satz ist als „passend“ gespeichert.
- [ ] Bei Rudern und Schulterdrücken werden links und rechts getrennt erfasst, zwischen den Seiten startet keine Pause, nach der rechten Seite schon.
- [ ] Beim ersten Training ist jedes Feld mit der oberen Grenze der Plan-Spanne vorbelegt.
- [ ] Nach „Einheit abschließen“ erscheint die Einheit mit Datum in der Verlaufsliste.
- [ ] Beim nächsten Öffnen zeigt jede Zirkel-Übung „Letztes Mal“ mit den Werten aller 3 Sätze, bei einseitigen Übungen pro Seite, und dem Gewicht.
- [ ] Die Felder sind beim nächsten Training mit den Werten der letzten Einheit vorbelegt.
- [ ] Nach Neuladen der Seite mitten im Training sind die bereits erfassten Werte und Anstrengungen noch da.
- [ ] Ohne Tap auf eine Anstrengung startet die Pause nach 5 Sekunden.
- [ ] „Daten sichern“ lädt auf Handy und Laptop eine Datei mit Datum im Namen herunter.
- [ ] Nach Leeren der Browserdaten stellt „Daten laden“ mit dieser Datei Verlauf und „Letztes Mal“ vollständig wieder her.
- [ ] Eine beliebige andere Datei wird mit verständlicher Meldung abgelehnt, die vorhandenen Daten bleiben unverändert.
- [ ] Vor dem Laden einer Sicherung warnt die App, dass die vorhandenen Daten ersetzt werden. Nach Bestätigung entspricht der Datenbestand genau der Datei.
- [ ] Bricht Fabian die Bestätigung ab, bleiben die vorhandenen Daten unverändert.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-11 | Daten lokal im Browser | Vorgabe Fabian: erst lokal, bis es ein echtes Backend gibt |
| 2026-10-12 | Anstrengung pro Satz mit drei Stufen „leicht / passend / am Limit“. Ohne Tap gilt „passend“, die Pause startet trotzdem. | Bleibt schlank, nur ein Tap mehr. Beste Grundlage für spätere Steigerungsvorschläge. Wörter statt Reserve-Zahlen (RIR), bewusst zum Einstieg. |
| 2026-10-12 | Vorbelegung ohne Vorwert: obere Grenze der Plan-Spanne. Mit Vorwert: Ist-Wert desselben Satzes der letzten Einheit. | Im Normalfall reicht Abhaken. Passt zur Erfahrung aus dem ersten Training (überall 2 Wdh. mehr). |
| 2026-10-12 | Keine Freitext-Notiz | Schlank halten, kann später nachgerüstet werden |
| 2026-10-12 | Einseitige Übungen pro Seite getrennt erfassen, ohne Pause zwischen den Seiten, Pause erst nach beiden Seiten | Gerade beim Wiedereinstieg sind die Seiten unterschiedlich stark, beide Werte sollen sichtbar sein. Ersetzt die frühere Annahme eines gemeinsamen Werts. |
| 2026-10-12 | Wartezeit auf die Anstrengung: 5 Sek., danach gilt „passend“ | Lang genug zum Tippen, kurz genug, dass es nicht bremst |
| 2026-10-12 | Export und Import der persönlichen Daten als Datei („Daten sichern“, „Daten laden“) | Schutz vor Datenverlust bei lokaler Datenhaltung. Ein Export ohne Import bringt wenig. |
| 2026-10-12 | Import ersetzt den lokalen Datenbestand nach Vorschau und Bestätigung, kein Zusammenführen | Fokus zunächst auf ein einziges Gerät, das hält die Umsetzung schlank. Zusammenführen für den Mehr-Geräte-Fall kann später nachgerüstet werden. |
