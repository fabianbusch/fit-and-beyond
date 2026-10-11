# Comeback-Training

Persönlicher Trainingsbegleiter für ein Ganzkörper-Krafttraining zu Hause. Die App führt durch die Einheit: Ablauf jeder Übung, Hilfsmittel, beanspruchte Muskeln, Satz- und Rundentracking und Pausentimer.

- **App:** [`index.html`](index.html) ist eine einzelne Datei ohne Build-Schritt und läuft in jedem Browser.
- **Live:** https://fabianbusch.github.io/fit-and-beyond/comeback-training/
- **Fachlicher Stand:** [`fachkonzept.md`](fachkonzept.md)
- **Features:** [`features/`](features/)

## Features

| Nr. | Titel | Status | Offene Fragen | Hängt ab von |
|---|---|---|---|---|
| [001](features/001-ist-leistung-erfassen.md) | Ist-Leistung erfassen und Trainingsprotokoll | Entwurf | keine | |
| [002](features/002-zeiten-erfassen.md) | Pausen- und Übungszeiten erfassen | Entwurf | keine | 001 |
| [003](features/003-countdown-signal.md) | Countdown-Signale für Pausen und Haltezeiten | Entwurf | keine | 002 |
| [004](features/004-muskelkarte.md) | Muskelkarte am Körpermodell (nur Markierung) | Entwurf | keine | |
| [005](features/005-burner.md) | Burner: optionale Zusatzübung | Entwurf | keine | 001, 002, 003, 006, 007 |
| [006](features/006-halteuebungen-auto-abhaken.md) | Zeitübungen automatisch abhaken | Entwurf | keine | 001, 002, 003 |
| [007](features/007-alternativen-per-swipe.md) | Alternative Übung per Swipe | Entwurf | keine | 001, 002 |
| [008](features/008-bewegungsmodell.md) | Bewegungsdarstellung der Übungen (menschliches Modell) | Entwurf · großes Feature | 6 | |
| [009](features/009-steigerung.md) | Automatische Steigerungsvorschläge (Progression) | Entwurf · großes Feature | 7 | 001 |

**Fachlich ohne offene Fragen:** 001 bis 007. Sie warten auf Fabians Freigabe.

**Vorgeschlagene Reihenfolge der Umsetzung:** 001 → 002 → 003 → 006 (Fundament: Erfassen, Los-Knopf, Signale, Zeitübungen) → 007 → 005 → 004. Danach die großen Features 009 (braucht echte Daten aus 001) und 008.
