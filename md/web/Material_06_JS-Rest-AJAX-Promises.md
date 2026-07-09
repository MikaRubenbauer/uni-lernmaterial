---
fach: Web
typ: notiz
thema: JavaScript — Rest (AJAX, Promises, Events, Gleichheit)
tags: [web/js, typ/material]
klausur: 2026-07-15
status: done
prio: mittel
aliases: []
---
# JS-Rest: AJAX, Promises, Events, Gleichheit
> Interaktives Material: [[06_JS-Rest_AJAX_Promises_Events_Gleichheit.html]]  ·  Säule: JavaScript  ·  Klausur-Aufgabe: Restthemen (==/===, Fetch/XHR, Promises, Events)

## Was drin ist
- ==/=== Coercion (gegen Node geprüft), AJAX Fetch vs. XMLHttpRequest, Promises/async-await, Arrow Functions, ES6-Classes.
- Events als Live-Demo (addEventListener, Bubbling), JSON parse/stringify, Browser-APIs.
- Klausurfalle: `==` führt Typumwandlung durch (`0 == ""` → true), `===` nicht.

## Quick-Reference
- Fetch gibt Promise zurück; XHR ist callback-basiert/älter.
- `===` vergleicht Typ + Wert ohne Coercion — im Zweifel immer `===`.
