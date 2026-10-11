# 009 – Automatische Steigerungsvorschläge (Progression)

**Status:** Entwurf
**Erstellt:** 2026-10-12
**Bezug:** Sprachgespräch 2026-10-12, abgespalten aus [006](006-halteuebungen-auto-abhaken.md) (Haltezeit steigern) und aus dem Gesamtkonzept
**Hängt ab von:** [001 – Ist-Leistung erfassen](001-ist-leistung-erfassen.md)

> **Hinweis zum Umfang:** Dies ist ein großes Feature. Es baut auf den Daten aus 001 auf und ist bewusst zurückgestellt, bis 001 umgesetzt ist und erste echte Trainingsdaten vorliegen. Die zentralen Fragen unten sind offen.

## Problem

Der Wiedereinstieg soll mit kontrollierter Steigerung erfolgen. Bisher gibt es keine Logik, die aus der erfassten Ist-Leistung (001) und der Anstrengung („leicht“, „passend“, „am Limit“) ableitet, wann mehr Wiederholungen, mehr Gewicht oder eine längere Haltezeit sinnvoll sind. Ohne Vorschlag bleibt man entweder zu lange auf derselben Stufe oder steigert zu schnell.

## Ziel

Die App schlägt pro Übung eine sinnvolle Steigerung vor, basierend auf den vergangenen Einheiten (001), der Anstrengung und den Plan-Spannen.

## Neuer Begriff

**Steigerung (Progression):** planmäßige Erhöhung der Belastung von Einheit zu Einheit, über mehr Wiederholungen, mehr Gewicht oder längere Haltezeit.

## Scope

**Drin (vorläufig):**
- Steigerung der Wiederholungen
- Steigerung des Gewichts in kg
- Steigerung der Haltezeit in Sekunden
- Eine einheitliche Steigerungslogik an **einer** Stelle für alle Übungen

**Nicht drin (vorläufig):**
- Neue Übungen oder schwerere Varianten vorschlagen (z. B. von erhöhten zu normalen Liegestützen)
- Änderung des Trainingsplans selbst (Blöcke, Runden, Pausen)
- Langfristige Periodisierung über Wochen

## Fachliche Regeln

Noch nicht festgelegt. Die Regeln ergeben sich aus den offenen Fragen, vor allem aus Frage 1.

Bereits fest:

1. **Datengrundlage:** Vorschläge stützen sich ausschließlich auf die eigenen erfassten Daten aus 001: Ist-Werte, Anstrengung und Gewicht pro Satz, bei einseitigen Übungen pro Seite.
2. **Eine Stelle:** Wiederholungen, Gewicht und Haltezeit folgen derselben Logik. Kein Feature regelt die Steigerung für sich allein, auch 006 nicht.

## Akzeptanzkriterien

Vorläufig, werden nach Klärung der offenen Fragen geschärft:

- [ ] Nach einer Einheit, in der alle Sätze einer Übung an der Obergrenze und mit „leicht“ oder „passend“ lagen, schlägt die App für diese Übung eine Steigerung vor.
- [ ] Nach einer Einheit mit „am Limit“ in mehreren Sätzen schlägt die App keine Steigerung vor.
- [ ] Der Vorschlag ist an der Übungskarte klar als Vorschlag erkennbar, mit kurzer Begründung, z. B. „Letztes Mal 3 × 12 mit ‚passend‘ → heute 11 kg“.

## Offene Fragen

> **Zentrale Fragen, vor jeder Umsetzung zu klären.**

1. **Steigerungsregel:** Nach welcher Regel wird gesteigert? Naheliegend ist die sogenannte **doppelte Progression**:
   - Erst die Wiederholungen steigern, bis alle Sätze die Obergrenze der Spanne erreichen, bei Anstrengung „leicht“ oder „passend“.
   - Dann das Gewicht erhöhen und die Wiederholungen auf die Untergrenze zurücksetzen.
   - Bei Übungen ohne Gewicht, z. B. Liegestütze, Band-Walks oder Unterarmstütz: Was folgt nach der Obergrenze? Spanne verschieben, schwerere Variante (007) oder nichts?
2. **Schrittgröße:** Wie stark pro Schritt? Gewicht in 0,5 oder 1 kg? Die vorhandenen Hantelscheiben begrenzen, welche Schritte überhaupt möglich sind. Haltezeit in 5 Sek.?
3. **Übernahme:** Wird der Vorschlag automatisch als Vorbelegung übernommen, oder nur angezeigt und erst nach Bestätigung übernommen?
4. **Rückschritt (Deload):** Was passiert bei wiederholtem „am Limit“ oder sinkenden Ist-Werten? Gewicht oder Wiederholungen reduzieren, und ab wann?
5. **Burner:** Gilt die Steigerung auch für den Burner (005)? Dort gibt es keine Spanne, nur „so viele wie möglich“.
6. **Einseitige Übungen:** Wird pro Seite getrennt gesteigert, oder richtet sich der Vorschlag nach der schwächeren Seite?
7. **Pausen und Abwesenheit:** Wie reagiert die App nach einer längeren Trainingspause, z. B. zwei Wochen ohne Einheit?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Aus 006 abgespalten, eigenes großes Feature | Steigerung betrifft Wiederholungen, Gewicht und Haltezeit gleichermaßen und soll an einer Stelle geregelt werden. Sinnvoll erst mit echten Daten aus 001. |
