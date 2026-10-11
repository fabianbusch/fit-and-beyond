# 002 – Pausen- und Übungszeiten erfassen

**Status:** Entwurf
**Erstellt:** 2026-10-11
**Bezug:** Handzettel „Pausenzeit & Übungszeit loggen“
**Hängt ab von:** 001 (Trainingsprotokoll)

## Problem

Der Plan nennt 60–90 Sek. Pause und ca. 35–40 Min. Gesamtdauer. Wie lange Sätze und Pausen wirklich dauern, ist unbekannt. Zu lange Pausen machen das Training länger und weniger dicht, zu kurze verschlechtern die Leistung.

## Ziel

Die App misst automatisch, wie lange gearbeitet und wie lange pausiert wurde, und zeigt das am Ende der Einheit und im Verlauf.

## Scope

**Drin:**
- Gesamtdauer der Einheit
- Dauer jedes Satzes und jeder Pause in Zirkel-Blöcken
- Zusammenfassung am Ende der Einheit
- Speicherung im Trainingsprotokoll (001)

**Nicht drin:**
- Herzfrequenz oder andere Sensordaten
- Zeitvorgaben oder Warnungen bei zu langen Pausen (möglich als Folgefeature)
- Zeiten für Aufwärmen und Abschluss einzeln (nur als Blockdauer)

## Fachliche Regeln

1. **Start der Einheit:** Die Einheit beginnt mit dem ersten abgehakten Eintrag oder dem ersten gestarteten Timer, je nachdem, was zuerst passiert.
2. **Ende der Einheit:** Die Einheit endet mit „Einheit abschließen“ (001).
3. **Pausenzeit:** von dem Moment, in dem ein Satz abgehakt wird, bis zum Beginn des nächsten Satzes. Bei einseitigen Übungen beginnt sie erst mit dem Abhaken der zweiten Seite. Die Zeit zwischen den Seiten zählt zur Übungszeit (siehe 001, Regel 2 und 11).
4. **Übungszeit:** vom Beginn eines Satzes bis zu seinem Abhaken.
5. **Beginn eines Satzes:** Siehe offene Frage 1, das ist der Kern dieses Features.
6. **Überziehen:** Läuft eine Pause länger als der Timer, zählt die Überziehung zur Pausenzeit. Die Timer-Leiste zählt nach Ablauf sichtbar weiter, z. B. „+0:12“.
7. **Zusammenfassung am Ende:**
   - Gesamtdauer
   - Reine Übungszeit und reine Pausenzeit, jeweils als Summe
   - Durchschnittliche Pause
   - Längste Pause, mit Übung und Runde
8. **Verlauf:** Die Liste vergangener Einheiten (001) zeigt zusätzlich die Gesamtdauer.

## Akzeptanzkriterien

- [ ] Nach einer kompletten Einheit stimmt die Gesamtdauer auf etwa eine Minute mit der Uhr überein.
- [ ] Eine bewusst auf 2 Min. verlängerte Pause erscheint in der Zusammenfassung als längste Pause mit etwa 2:00.
- [ ] Nach Ablauf eines Pausentimers zählt die Leiste sichtbar die Überziehung hoch.
- [ ] Die Zeiten überstehen ein Neuladen der Seite mitten im Training.

## Offene Fragen

1. **Wann beginnt ein Satz?**
   - **Variante A, automatisch:** Der Satz beginnt, wenn der Pausentimer abläuft oder gestoppt wird. Kein Extra-Tap, aber ungenau, wenn man nach dem Signal noch trinkt.
   - **Variante B, mit Tap:** Ein großer Knopf „Los“ in der Leiste startet den Satz. Genau, aber ein Tap mehr pro Satz. Er wäre zugleich ein natürlicher Startpunkt für den Halte-Timer (006).
   - **Variante C, gemischt:** wie A, aber mit „Los“ als optionaler Korrektur.
2. **Pausenvorgabe anpassen:** Soll die gemessene Durchschnittspause künftig die Standardpause vorbelegen, z. B. 75 statt 60 Sek.? Oder bleibt das bewusst manuell?
3. **Zeitanzeige im Training:** Soll während der Einheit eine laufende Gesamtuhr sichtbar sein, oder reicht die Zusammenfassung am Ende?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| | | |
