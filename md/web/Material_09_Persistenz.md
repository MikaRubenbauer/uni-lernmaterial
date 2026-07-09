---
fach: Web
typ: notiz
thema: NodeJS — Persistenz
tags: [web/nodejs, typ/material]
klausur: 2026-07-15
status: done
prio: mittel
aliases: []
---
# Persistenz (Datei / DB)
> Interaktives Material: [[09_Persistenz.html]]  ·  Säule: NodeJS  ·  Klausur-Aufgabe: Restthema (fs Datei-/DB-Persistenz)

## Was drin ist
- Datei-Persistenz über `fs` (read/write, sync vs. async), Grundidee DB-Anbindung.
- Klausurfalle: synchrones `fs` blockiert den Event-Loop; asynchrone Variante bevorzugen.

## Quick-Reference
- `fs.writeFile`/`readFile` (async, Callback/Promise) vs. `*Sync` (blockierend).
- Persistenz = Zustand überlebt Prozess-Neustart (Datei/DB), im Gegensatz zu In-Memory.
