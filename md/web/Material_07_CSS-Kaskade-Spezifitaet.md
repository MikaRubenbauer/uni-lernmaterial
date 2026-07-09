---
fach: Web
typ: notiz
thema: CSS — Kaskade & Spezifität
tags: [web/css, typ/material]
klausur: 2026-07-15
status: done
prio: mittel
aliases: []
---
# CSS-Kaskade & Spezifität
> Interaktives Material: [[07_CSS-Kaskade-Spezifitaet.html]]  ·  Säule: CSS  ·  Klausur-Aufgabe: Restthema (Kaskade, !important, Spezifität)

## Was drin ist
- Kaskaden-Reihenfolge, `!important`, Spezifitäts-Berechnung mit durchgerechnetem Unbekannt-II-Beispiel.
- Klausurfalle: `!important` schlägt höhere Spezifität; bei Gleichstand gewinnt die spätere Regel.

## Quick-Reference
- Spezifität (a,b,c) = (ID, Klasse/Attribut/Pseudo-Klasse, Element). Inline überschreibt alles außer `!important`.
- Reihenfolge bei Gleichstand: zuletzt deklarierte Regel gewinnt.
