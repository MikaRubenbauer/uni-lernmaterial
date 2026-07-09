---
fach: Web
typ: notiz
thema: Webserver / HTTP
tags: [web/webserver, typ/material]
klausur: 2026-07-15
status: done
prio: hoch
aliases: []
---
# Webserver-HTTP-Sandbox-Pack
> Interaktives Material: [[05_Webserver-HTTP-Sandbox-Pack.html]]  ·  Säule: Webserver/HTTP  ·  Klausur-Aufgabe: Aufg.4 (Webserver-Aufgaben, Prozessmodelle/CGI, HTTP-Status, Sandbox)

## Was drin ist
- Webserver-Aufgaben + Prozessmodelle (CGI = getrennter Prozess / In-Process); minimaler http-Server (gegen Node verifiziert) + Express-Variante + npm.
- Interaktiver HTTP-Status-Explorer (1xx–5xx) + Methoden; JS-Sandbox (verhinderte Zugriffe + Schutzfunktion).
- Klausurfalle: CGI startet pro Request neuen Prozess (langsam, isoliert) vs. In-Process (schnell, geteilter Speicher).

## Quick-Reference
- Status: 2xx ok, 3xx redirect, 4xx Client-Fehler, 5xx Server-Fehler. 404 = nicht gefunden, 500 = Serverfehler.
- Sandbox isoliert Browser-JS vom Dateisystem/anderen Origins (Same-Origin-Policy).
