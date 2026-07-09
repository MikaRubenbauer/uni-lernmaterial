---
fach: Web
typ: notiz
thema: JavaScript — Trace & DOM
tags: [web/js, typ/material]
klausur: 2026-07-15
status: done
prio: hoch
aliases: []
---
# JS-Trace-Stepper & DOM-Insert
> Interaktives Material: [[01_JS-Trace-Stepper_und_DOM.html]]  ·  Säule: JavaScript  ·  Klausur-Aufgabe: Aufg.3 (Calculator-Trace, DOM-Insert)

## Was drin ist
- Schritt-für-Schritt-Tracer des Calculator-Codes: `new` vs. plain Call, `this`-Bindung, globales `b`, Shadowing/TDZ.
- DOM-Insert-Demo: `li` mit `land="de"` in `div#inhalt` einfügen (createElement/setAttribute/append).
- Klausurfalle: plain Call setzt `this` global → verändert äußere Variable; `new` erzeugt eigenes Objekt.

## Quick-Reference
- Verifiziertes Trace-Ergebnis: x1={m:1401,n:"Tolle Welt"}, x2=1401, x3="Tolle", x4=[{…}], x5=6.
- `new` → frisches `this`; Funktionsaufruf ohne `new` → `this` = global/undefined (strict).
