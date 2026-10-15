# 002 – Pausen- und Übungszeiten erfassen

**Status:** In Umsetzung · gebaut in v0.5, Prüfung durch Fabian offen (Freigabe 2026-10-15)
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Pausenzeit & Übungszeit loggen“
**Hängt ab von:** 001 (Trainingsprotokoll)

## Problem

Der Plan nennt 60–90 Sek. Pause und ca. 35–40 Min. Gesamtdauer. Wie lange Sätze und Pausen wirklich dauern, ist unbekannt. Zu lange Pausen machen das Training länger und weniger dicht, zu kurze verschlechtern die Leistung.

## Ziel

Die App misst genau, wie lange gearbeitet und wie lange pausiert wurde, zeigt die laufende Gesamtzeit während des Trainings und fasst alles am Ende der Einheit und im Verlauf zusammen. Dafür startet jeder Satz bewusst mit einem **„Los“**.

## Neue Begriffe

- **Los:** der Moment, in dem ein Satz oder bei einseitigen Übungen eine Seite beginnt, ausgelöst über den Knopf „Los“.
- **Übungszeit:** Zeit von „Los“ bis zum Abhaken. Bei einseitigen Übungen gibt es sie pro Seite und für den ganzen Satz.
- **Wechselzeit:** bei einseitigen Übungen die Zeit vom Abhaken der linken Seite bis zum „Los“ der rechten.
- **Pausenzeit:** Zeit vom Abhaken eines Satzes bis zum nächsten „Los“.
- **Gesamtuhr:** die laufende Zeit seit dem ersten „Los“ der Einheit.

## Scope

**Drin:**
- Pflicht-Knopf „Los“ vor jedem Satz in Zirkel-Blöcken, bei einseitigen Übungen vor jeder Seite
- Ein „Los“ zu Beginn des Aufwärmens
- Laufende Gesamtuhr während des Trainings
- Gesamtdauer der Einheit
- Dauer jedes Satzes, jeder Seite und jeder Pause
- Zusammenfassung am Ende der Einheit
- Speicherung im Trainingsprotokoll (001)

**Nicht drin:**
- Automatische Anpassung der Pausenvorgabe an gemessene Pausen
- Herzfrequenz oder andere Sensordaten
- Zeitvorgaben oder Warnungen bei zu langen Pausen (möglich als Folgefeature)
- Zeiten für einzelne Aufwärm- und Abschlussübungen

## Fachliche Regeln

### Der Los-Knopf

1. **Pflicht:** Jeder Satz in einem Zirkel-Block beginnt mit „Los“. Es gibt keinen automatischen Start und keinen Rückfall, falls „Los“ fehlt.
2. **Erzwungen:** Solange für einen Satz kein „Los“ gedrückt wurde, lässt er sich nicht abhaken. Das Satzfeld zeigt dann statt „Satz 1“ den Knopf „Los“. Nach dem Tap wird daraus das Abhaken-Feld. So kann die Übungszeit nie fehlen.
3. **Einseitige Übungen:** Rudern und Schulterdrücken haben pro Seite ein eigenes „Los“. Ablauf eines Satzes:
   - „Los links“ → linke Seite ausführen → links abhaken
   - „Los rechts“ → rechte Seite ausführen → rechts abhaken
   - Erst danach startet die Pause. Zwischen den Seiten gibt es keinen Pausentimer (001, Regel 2).
   - „Los rechts“ ist erst möglich, wenn links abgehakt ist. Tippt Fabian „Los rechts“, während die Anstrengungsauswahl der linken Seite noch offen ist, gilt links „passend“ (001, Regel 3).
4. **Aufwärmen:** Das Aufwärmen hat ein einziges „Los“ am Blockanfang. Damit beginnt die Einheit. Die Aufwärmübungen lassen sich danach ohne eigenes „Los“ abhaken. Vor diesem ersten „Los“ ist nichts abhakbar.
5. **Abschluss:** Abschlussübungen ohne Zeitangabe brauchen kein „Los“, weil die Einheit dann längst läuft. Dehnungen mit Zeitangabe starten mit „Los“, weil dort der Timer läuft (006, Regel 12–17). Ihre Zeiten werden nicht einzeln erfasst.
6. **Wo:** „Los“ gibt es an zwei Stellen, die dasselbe tun:
   - groß in der Timer-Leiste, immer für den nächsten Schritt in der Ablaufreihenfolge (Fachkonzept F4),
   - am Satzfeld auf der Übungskarte, für jeden noch offenen Satz beziehungsweise jede offene Seite.
7. **Nur ein laufender Satz:** Es kann immer nur ein Satz gleichzeitig laufen. Solange einer läuft, ist „Los“ an allen anderen Sätzen gesperrt. Ein einseitiger Satz läuft von „Los links“ bis zum Abhaken rechts.
8. **Während eines Satzes:** Die Leiste zeigt Übung, Ort (z. B. „Block B · Runde 2 von 3 · Satz 2 · rechts“) und die mitlaufende Übungszeit.
9. **Los während der Pause:** Wird „Los“ gedrückt, solange der Pausentimer noch läuft, endet die Pause sofort. Die Pausenzeit ist dann entsprechend kürzer.
10. **Versehentliches Los:** Ein laufender Satz oder eine laufende Seite lässt sich über „Abbrechen“ zurücksetzen und braucht dann ein neues „Los“. Die Pausenzeit läuft in diesem Fall weiter, als wäre nichts passiert.
11. **Abhaken rückgängig:** Wird ein erledigter Satz wieder abgewählt (Fachkonzept F2), werden seine Zeiten verworfen. Er braucht ein neues „Los“.

### Zeiten

12. **Start der Einheit:** Die Einheit beginnt mit dem ersten „Los“, also dem „Los“ des Aufwärmens. Die Gesamtdauer enthält das Aufwärmen.
13. **Ende der Einheit:** Die Einheit endet mit „Einheit abschließen“ (001).
14. **Übungszeit:** von „Los“ bis zum Abhaken. Bei einseitigen Übungen wird sie pro Seite gespeichert. Die Übungszeit des ganzen Satzes reicht von „Los links“ bis zum Abhaken rechts und umfasst die Wechselzeit.
15. **Pausenzeit:** vom Abhaken eines Satzes bis zum nächsten „Los“, bei einseitigen Übungen ab dem Abhaken der rechten Seite. Die 5 Sek. Anstrengungsauswahl aus 001 zählen zur Pause.
16. **Pausenvorgabe:** Die Pausenvorgabe bleibt fest auf dem eingestellten Wert, heute 60 Sek. Die App passt sie nicht an die gemessenen Pausen an. Die Durchschnittspause erscheint nur in der Zusammenfassung.
17. **Überziehen:** Läuft eine Pause länger als der Timer, zählt die Überziehung zur Pausenzeit. Die Timer-Leiste zählt nach Ablauf sichtbar weiter, z. B. „+0:12“, bis „Los“ gedrückt wird.

### Gesamtuhr

18. **Anzeige:** Ab dem ersten „Los“ zeigt die App dezent eine laufende Gesamtuhr, z. B. „Gesamt 12:34“. Sie steht in der Timer-Leiste, kleiner und ruhiger als Pausen- und Satzzeit, damit der Blick auf der Übung bleibt.
19. **Lauf:** Die Gesamtuhr läuft durchgehend, auch während Pausen. Sie stoppt mit „Einheit abschließen“.
20. **Neuladen:** Nach Neuladen der Seite zeigt die Gesamtuhr die richtige Zeit ab dem ersten „Los“, nicht ab dem Neuladen.

### Auswertung

21. **Zusammenfassung am Ende:**
    - Gesamtdauer
    - Reine Übungszeit und reine Pausenzeit, jeweils als Summe
    - Durchschnittliche Pause
    - Längste Pause, mit Übung und Runde
22. **Verlauf:** Die Liste vergangener Einheiten (001) zeigt zusätzlich die Gesamtdauer.

### Bezug zu anderen Features

23. **006 (Zeitübungen):** Beim Unterarmstütz übernimmt „Los“ die Rolle des heutigen Knopfs „Halten“. Wie „Los“, Vor-Countdown und automatisches Abhaken dort zusammenspielen, wird in 006 festgelegt.
24. **Bisherige automatische Pause (Fachkonzept F5):** Die Pause startet weiterhin nach dem Abhaken, wie in 001 beschrieben. Neu ist nur, dass sie durch „Los“ beendet wird.

## Akzeptanzkriterien

- [ ] Vor dem „Los“ des Aufwärmens ist nichts abhakbar. Danach lassen sich alle Aufwärmübungen ohne weiteres „Los“ abhaken.
- [ ] Ein Satz in Block A–C, für den kein „Los“ gedrückt wurde, lässt sich nicht abhaken.
- [ ] Bei Rudern und Schulterdrücken braucht jede Seite ein eigenes „Los“. „Los rechts“ ist erst nach dem Abhaken links möglich. Zwischen den Seiten startet keine Pause.
- [ ] Im Protokoll stehen bei einseitigen Übungen getrennte Übungszeiten für links und rechts.
- [ ] Nach „Los“ zeigt die Leiste die mitlaufende Übungszeit, und der Satz lässt sich abhaken.
- [ ] Solange ein Satz läuft, lässt sich kein anderer Satz starten.
- [ ] „Los“ während einer laufenden Pause beendet die Pause sofort.
- [ ] Nach Ablauf eines Pausentimers zählt die Leiste sichtbar die Überziehung hoch, bis „Los“ gedrückt wird.
- [ ] Die Pausenvorgabe bleibt auch nach mehreren Einheiten mit längeren Pausen bei 60 Sek.
- [ ] Ab dem ersten „Los“ ist eine laufende Gesamtuhr sichtbar, die auch in Pausen weiterläuft und mit „Einheit abschließen“ stoppt.
- [ ] Nach einer kompletten Einheit stimmt die Gesamtdauer auf etwa eine Minute mit der Uhr überein, gemessen ab dem „Los“ des Aufwärmens.
- [ ] Eine bewusst auf 2 Min. verlängerte Pause erscheint in der Zusammenfassung als längste Pause mit etwa 2:00.
- [ ] Gesamtuhr und alle Zeiten, auch ein gerade laufender Satz, überstehen ein Neuladen der Seite mitten im Training.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Jeder Satz startet über einen Pflicht-Knopf „Los“, kein automatischer Start und kein Automatik-Rückfall | Genaue Übungszeit statt geschätzter. Trinken oder Gewicht umbauen nach dem Pausensignal zählt so zur Pause. |
| 2026-10-12 | Abhaken ist gesperrt, bis für den Satz „Los“ gedrückt wurde | „Los“ kann nicht vergessen werden, die Übungszeit fehlt nie |
| 2026-10-12 | Auch der allererste Satz braucht „Los“, die Einheit beginnt mit dem ersten „Los“ | Ablauf immer gleich, eindeutiger Startpunkt für die Gesamtdauer |
| 2026-10-12 | Ein einziges „Los“ zu Beginn des Aufwärmens startet die Einheit, die Aufwärmübungen brauchen kein eigenes „Los“ | Die Gesamtdauer enthält das Aufwärmen, ohne das Aufwärmen mit Tipps zu überfrachten |
| 2026-10-12 | Einseitige Übungen: ein eigenes „Los“ pro Seite, Übungszeit getrennt für links und rechts | Konsistent zur getrennten Erfassung pro Seite in 001 |
| 2026-10-12 | Pausenvorgabe bleibt fest, keine automatische Anpassung an gemessene Pausen | Vorhersehbarkeit. Eine sich selbst verschiebende Vorgabe fühlt sich ungefragt an. |
| 2026-10-12 | Laufende Gesamtuhr dezent sichtbar, ab dem ersten „Los“ | Gefühl fürs Tempo, ohne vom Satz abzulenken |
