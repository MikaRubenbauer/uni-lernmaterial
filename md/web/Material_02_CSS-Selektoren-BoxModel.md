---
fach: Web
typ: notiz
thema: CSS — Selektoren, Box-Model, Positionierung
tags: [web/css, typ/material]
klausur: 2026-07-15
status: done
prio: hoch
aliases: []
---
# CSS-Selektoren, Box-Model & Position
> Interaktives Material: [[02_CSS-Selektoren_BoxModel_Position.html]]  ·  Säule: CSS  ·  Klausur-Aufgabe: Aufg.2 (Selektor-Matching, Box-Model, top/left)

## Was drin ist
- Live-Selektor-Matching (awe/maria-Body) selbst-verifizierend über `querySelectorAll` + komplette Lösungstabelle.
- Box-Model-Visual (content/padding/border/margin, box-sizing) und animierte top/left-Positionsaufgabe (blue/green/red).
- Klausurfallen: exakt `=` vs. `~=`, fehlender Doppelpunkt, `border:5px` ohne Stil wirkungslos, `static` ignoriert top/left.

## Quick-Reference
- Spezifität: Inline > ID > Klasse/Attribut/Pseudo > Element.
- `position:static` (Default) reagiert NICHT auf top/left/z-index.
