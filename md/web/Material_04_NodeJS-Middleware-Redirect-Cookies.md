---
fach: Web
typ: notiz
thema: NodeJS — Middleware, Redirect, Cookies
tags: [web/nodejs, typ/material]
klausur: 2026-07-15
status: done
prio: hoch
aliases: []
---
# NodeJS-Pack: Middleware, Redirect & Cookies
> Interaktives Material: [[04_NodeJS-Pack_Middleware_Redirect_Cookies.html]]  ·  Säule: NodeJS  ·  Klausur-Aufgabe: Aufg.5 (Middleware param==42, Forward/Redirect, Cookies, URLs)

## Was drin ist
- Express-Middleware `param==42 → /spezial` + Redirect-Handler; animierter Forward-vs-Redirect-Flow (Client/Server-Pfeile).
- Animierter Cookie-Flow (Set-Cookie → speichern → automatisch mitschicken); URL-Arten (absolut/protokoll-/root-/dokument-relativ).
- Klausurfalle: Redirect = neue Client-Anfrage (URL ändert sich, 3xx); Forward = serverintern (URL bleibt).

## Quick-Reference
- Redirect: `res.redirect()` / Status 302 → Browser holt neu. Forward: Server liefert anderes Ressourcen-Ergebnis ohne neue Anfrage.
- Cookie wird nach Set-Cookie bei jeder Folge-Anfrage an dieselbe Domain automatisch mitgesendet.
