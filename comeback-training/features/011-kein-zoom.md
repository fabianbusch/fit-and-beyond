# 011 – Kein Zoom

**Status:** In Umsetzung · gebaut in v0.7, Prüfung durch Fabian offen
**Erstellt:** 2026-10-15
**Bezug:** Chat 2026-10-15, Fehler beim Test von v0.6: Doppeltipp auf dem Handy hat gezoomt. Vorgabe Fabian: „Kein Zoom möglich!“

## Problem

Schnelles zweimaliges Tippen, z. B. auf „Los“ oder „+“, löst auf dem Handy den Browser-Zoom aus. Mitten im Training ist die Seite dann vergrößert und verschoben.

## Ziel

Die App lässt sich nicht zoomen, weder per Doppeltipp noch mit zwei Fingern. Scrollen bleibt möglich.

## Scope

**Drin:**
- Comeback-Training und die Startseite des Repos

**Nicht drin:**
- Eigene Schriftgrößen-Einstellung in der App (möglich als Folgefeature, falls Text zu klein ist)

## Fachliche Regeln

1. **Kein Doppeltipp-Zoom:** Zwei schnelle Tipps zählen als zwei normale Tipps, z. B. zweimal „+“.
2. **Kein Zwei-Finger-Zoom:** Auch das Aufziehen mit zwei Fingern vergrößert die Seite nicht.
3. **Scrollen und Wischen bleiben:** Senkrecht scrollen und das Wischen für Alternativen (007) funktionieren unverändert.
4. **Eingabefelder:** Das Antippen eines Eingabefelds, z. B. für die Burner-Wiederholungen, zoomt nicht. Die Schriftgröße in Feldern liegt dafür bei mindestens 16 px.

## Akzeptanzkriterien

- [ ] Doppeltipp an beliebiger Stelle zoomt auf Android und iPhone nicht.
- [ ] Zwei-Finger-Geste zoomt auf Android und iPhone nicht.
- [ ] Zweimal schnell „+“ erhöht den Wert um 2.
- [ ] Scrollen und Wischen funktionieren wie vorher.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-15 | Zoom komplett unterbinden: Viewport ohne Skalierung, `touch-action` erlaubt nur Scrollen, Zwei-Finger-Gesten auf iOS werden abgefangen | Vorgabe Fabian. Versehentliches Zoomen stört im Training. Bewusst in Kauf genommen: Wer Text vergrößern will, muss die Schriftgröße im System einstellen. |
