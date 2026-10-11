# 002 – Pausen- und Übungszeiten erfassen

**Status:** Entwurf
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Pausenzeit & Übungszeit loggen“
**Hängt ab von:** 001 (Trainingsprotokoll)

## Problem

Der Plan nennt 60–90 Sek. Pause und ca. 35–40 Min. Gesamtdauer. Wie lange Sätze und Pausen wirklich dauern, ist unbekannt. Zu lange Pausen machen das Training länger und weniger dicht, zu kurze verschlechtern die Leistung.

## Ziel

Die App misst genau, wie lange gearbeitet und wie lange pausiert wurde, und zeigt das am Ende der Einheit und im Verlauf. Dafür startet jeder Satz bewusst mit einem **„Los“**.

## Neue Begriffe

- **Los:** der Moment, in dem ein Satz beginnt, ausgelöst über den Knopf „Los“.
- **Übungszeit:** Zeit von „Los“ bis zum Abhaken eines Satzes.
- **Pausenzeit:** Zeit vom Abhaken eines Satzes bis zum nächsten „Los“.

## Scope

**Drin:**
- Pflicht-Knopf „Los“ vor jedem Satz in Zirkel-Blöcken
- Gesamtdauer der Einheit
- Dauer jedes Satzes und jeder Pause
- Zusammenfassung am Ende der Einheit
- Speicherung im Trainingsprotokoll (001)

**Nicht drin:**
- Herzfrequenz oder andere Sensordaten
- Zeitvorgaben oder Warnungen bei zu langen Pausen (möglich als Folgefeature)
- Zeiten für einzelne Aufwärm- und Abschlussübungen

## Fachliche Regeln

### Der Los-Knopf

1. **Pflicht:** Jeder Satz in einem Zirkel-Block beginnt mit „Los“. Es gibt keinen automatischen Start und keinen Rückfall, falls „Los“ fehlt.
2. **Erzwungen:** Solange für einen Satz kein „Los“ gedrückt wurde, lässt er sich nicht abhaken. Das Satzfeld zeigt dann statt „Satz 1“ den Knopf „Los“. Nach dem Tap wird daraus das Abhaken-Feld. So kann die Übungszeit nie fehlen.
3. **Wo:** „Los“ gibt es an zwei Stellen, die dasselbe tun:
   - groß in der Timer-Leiste, immer für den nächsten Satz in der Ablaufreihenfolge (Fachkonzept F4),
   - am Satzfeld auf der Übungskarte, für jeden noch offenen Satz.
4. **Nur ein laufender Satz:** Es kann immer nur ein Satz gleichzeitig laufen. Solange einer läuft, ist „Los“ an allen anderen Sätzen gesperrt.
5. **Während eines Satzes:** Die Leiste zeigt Übung, Ort (z. B. „Block A · Runde 2 von 3 · Satz 2“) und die mitlaufende Übungszeit.
6. **Los während der Pause:** Wird „Los“ gedrückt, solange der Pausentimer noch läuft, endet die Pause sofort. Die Pausenzeit ist dann entsprechend kürzer.
7. **Versehentliches Los:** Ein laufender Satz lässt sich über „Abbrechen“ zurücksetzen. Er ist dann wieder offen und braucht ein neues „Los“. Die Pausenzeit läuft in diesem Fall weiter, als wäre nichts passiert.
8. **Abhaken rückgängig:** Wird ein erledigter Satz wieder abgewählt (Fachkonzept F2), werden seine Zeiten verworfen. Er braucht ein neues „Los“.

### Zeiten

9. **Start der Einheit:** Die Einheit beginnt mit dem ersten „Los“. Das gilt auch für den allerersten Satz, vor dem es noch keine Pause gab. Der Ablauf ist dadurch immer gleich. Zum Aufwärmen siehe offene Frage 1.
10. **Ende der Einheit:** Die Einheit endet mit „Einheit abschließen“ (001).
11. **Übungszeit:** von „Los“ bis zum Abhaken des Satzes.
12. **Pausenzeit:** vom Abhaken eines Satzes bis zum nächsten „Los“. Die 5 Sek. Anstrengungsauswahl aus 001 zählen zur Pause.
13. **Einseitige Übungen:** Rudern und Schulterdrücken haben ein „Los“ pro Satz, nicht pro Seite. Die Übungszeit läuft von „Los“ bis zum Abhaken der zweiten Seite und umfasst damit beide Seiten und den Wechsel. Die Pausenzeit beginnt erst mit dem Abhaken der zweiten Seite (siehe 001, Regel 2 und 11). Siehe offene Frage 2.
14. **Überziehen:** Läuft eine Pause länger als der Timer, zählt die Überziehung zur Pausenzeit. Die Timer-Leiste zählt nach Ablauf sichtbar weiter, z. B. „+0:12“, bis „Los“ gedrückt wird.
15. **Zusammenfassung am Ende:**
    - Gesamtdauer
    - Reine Übungszeit und reine Pausenzeit, jeweils als Summe
    - Durchschnittliche Pause
    - Längste Pause, mit Übung und Runde
16. **Verlauf:** Die Liste vergangener Einheiten (001) zeigt zusätzlich die Gesamtdauer.

### Bezug zu anderen Features

17. **006 (Zeitübungen):** Beim Unterarmstütz übernimmt „Los“ die Rolle des heutigen Knopfs „Halten“. Wie „Los“, Vor-Countdown und automatisches Abhaken dort zusammenspielen, wird in 006 festgelegt.
18. **Bisherige automatische Pause (Fachkonzept F5):** Die Pause startet weiterhin nach dem Abhaken, wie in 001 beschrieben. Neu ist nur, dass sie durch „Los“ beendet wird.

## Akzeptanzkriterien

- [ ] Ein Satz, für den kein „Los“ gedrückt wurde, lässt sich nicht abhaken. Das gilt auch für den allerersten Satz der Einheit.
- [ ] Nach „Los“ zeigt die Leiste die mitlaufende Übungszeit, und der Satz lässt sich abhaken.
- [ ] Solange ein Satz läuft, lässt sich kein anderer Satz starten.
- [ ] „Los“ während einer laufenden Pause beendet die Pause sofort.
- [ ] Bei Rudern und Schulterdrücken genügt ein „Los“ für beide Seiten.
- [ ] Nach Ablauf eines Pausentimers zählt die Leiste sichtbar die Überziehung hoch, bis „Los“ gedrückt wird.
- [ ] Nach einer kompletten Einheit stimmt die Gesamtdauer auf etwa eine Minute mit der Uhr überein, gemessen ab dem ersten „Los“.
- [ ] Eine bewusst auf 2 Min. verlängerte Pause erscheint in der Zusammenfassung als längste Pause mit etwa 2:00.
- [ ] Die Zeiten, auch ein gerade laufender Satz, überstehen ein Neuladen der Seite mitten im Training.

## Offene Fragen

1. **Aufwärmen:** Das Aufwärmen hat keine Sätze, nur ein „Erledigt“ pro Übung. Braucht es auch ein „Los“?
   - Vorschlag: ein einziges „Los“ zu Beginn des Aufwärmens. Damit beginnt die Einheit, die Aufwärmübungen lassen sich danach ohne weiteres „Los“ abhaken. Die Gesamtdauer enthält so das Aufwärmen.
   - Alternative: Aufwärmen ohne „Los“, die Einheit beginnt erst mit dem ersten Satz von Block A. Die Gesamtdauer enthält dann kein Aufwärmen.
2. **Einseitige Übungen:** Reicht ein „Los“ pro Satz, wie in Regel 13 angenommen? Oder soll auch die zweite Seite ein eigenes „Los“ bekommen, um die Zeit pro Seite zu messen?
3. **Pausenvorgabe anpassen:** Soll die gemessene Durchschnittspause künftig die Standardpause vorbelegen, z. B. 75 statt 60 Sek.? Oder bleibt das bewusst manuell?
4. **Gesamtuhr im Training:** Soll während der Einheit eine laufende Gesamtuhr sichtbar sein, oder reichen die Satzzeit in der Leiste und die Zusammenfassung am Ende?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Jeder Satz startet über einen Pflicht-Knopf „Los“, kein automatischer Start und kein Automatik-Rückfall | Genaue Übungszeit statt geschätzter. Trinken oder Gewicht umbauen nach dem Pausensignal zählt so zur Pause. |
| 2026-10-12 | Abhaken ist gesperrt, bis für den Satz „Los“ gedrückt wurde | „Los“ kann nicht vergessen werden, die Übungszeit fehlt nie |
| 2026-10-12 | Auch der allererste Satz braucht „Los“, die Einheit beginnt mit dem ersten „Los“ | Ablauf immer gleich, eindeutiger Startpunkt für die Gesamtdauer |
