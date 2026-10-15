# 010 – Fokus auf die aktuelle Übung

**Status:** In Umsetzung · gebaut in v0.6, Prüfung durch Fabian offen
**Erstellt:** 2026-10-15
**Bezug:** Chat 2026-10-15, Wunsch Fabian nach erstem Test von v0.5: „Bitte den Fokus auf die aktuelle Übung scrollen!“
**Hängt zusammen mit:** 002 (Ablaufreihenfolge, Los), 006 (Zeitübungen, Dehnungen)

## Problem

Die Seite ist lang, jede Übungskarte ist auf dem Handy mehr als eine Bildschirmhöhe groß. Während des Trainings muss man selbst suchen und scrollen, welche Übung gerade dran ist.

## Ziel

Die App scrollt von selbst zur Übung, die gerade dran ist, und hebt sie sichtbar hervor.

## Scope

**Drin:**
- Automatisches Scrollen, wenn die aktuelle Übung wechselt
- Hervorhebung der Karte der aktuellen Übung

**Nicht drin:**
- Einklappen der übrigen Karten oder eine Einzelansicht pro Übung (möglich als Folgefeature)

## Fachliche Regeln

1. **Aktuelle Übung**, in dieser Reihenfolge:
   - die laufende Übung, also nach „Los“ bis zum Abhaken, auch während 3-2-1, Haltezeit und Seitenwechsel,
   - die Übung, deren Anstrengung oder Burner-Wiederholungen gerade abgefragt werden,
   - sonst der nächste Schritt in der Ablaufreihenfolge (Fachkonzept F4). Während einer Pause ist das die Übung, die danach kommt, damit man sich vorbereiten kann.
   - Beim Aufwärmen vor dem ersten „Los“ ist es der Aufwärmblock. Beim Burner-Angebot ist es der Burner-Bereich. Ist alles erledigt, ist es „Einheit abschließen“.
2. **Wann gescrollt wird:** nur, wenn die aktuelle Übung **wechselt**, und beim Öffnen der Seite während einer laufenden Einheit. Solange sie gleich bleibt, scrollt die App nicht, damit Fabian frei nach oben oder unten schauen kann.
3. **Wohin:** Die Karte wird mit ihrer Oberkante knapp unter den oberen Bildschirmrand gescrollt. Ist die Oberkante schon im oberen Drittel sichtbar, scrollt die App nicht.
4. **Kein Scrollen** vor dem ersten „Los“ einer Einheit, während die Zusammenfassung angezeigt wird, und während ein erledigter Satz bearbeitet wird.
5. **Hervorhebung:** Die Karte der aktuellen Übung hat einen deutlich sichtbaren Rahmen in der Akzentfarbe, in hellem und dunklem Design.
6. **Bewegung:** Weich gescrollt. Bei der Systemeinstellung „Bewegung reduzieren“ springt die Seite ohne Animation.

## Akzeptanzkriterien

- [ ] Nach „Los“ beim Goblet Squat steht dessen Karte oben im Bild und ist hervorgehoben.
- [ ] Nach dem Abhaken und der Anstrengung, also mit Beginn der Pause, scrollt die Seite zur nächsten Übung.
- [ ] Nach dem automatischen Abhaken des Unterarmstützes scrollt die Seite ohne Berühren zur nächsten Übung.
- [ ] Scrollt Fabian während einer Pause selbst weg, springt die Seite nicht zurück, bis die nächste Übung beginnt.
- [ ] Nach Neuladen mitten in der Einheit steht die aktuelle Übung oben.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-15 | Automatisch zur aktuellen Übung scrollen und sie hervorheben | Direkter Wunsch Fabian nach dem ersten Test |
| 2026-10-15 | Während der Pause gilt die nächste Übung als aktuell | Man sieht schon, was als Nächstes kommt, und kann sich vorbereiten |
| 2026-10-15 | Nur beim Wechsel scrollen, nicht dauerhaft festhalten | Die App soll nicht gegen eigenes Scrollen ankämpfen |
