---
fach: Web
typ: notiz
thema: Sicherheit & Datenschutz
tags: [web/sicherheit, typ/material]
klausur: 2026-07-15
status: done
prio: mittel
aliases: []
---
# Sicherheit & Datenschutz
> Interaktives Material: [[08_Sicherheit-Datenschutz.html]]  ·  Säule: Sicherheit  ·  Klausur-Aufgabe: Restthema (XSS/CSRF/SQLi, TLS, sichere Cookies)

## Was drin ist
- Typische Angriffe: XSS, CSRF, SQL-Injection (je mit Beispiel + Gegenmaßnahme); HTTPS/TLS-Grundlagen.
- Sichere Cookies (HttpOnly, Secure, SameSite), DSGVO-Bezug.
- Klausurfalle: XSS = eingeschleustes Skript im Browser; CSRF = erzwungene Aktion mit fremder Session; SQLi = manipulierte DB-Query.

## Quick-Reference
- Schutz: Eingaben escapen/parametrisieren (XSS/SQLi), CSRF-Token + SameSite-Cookie (CSRF).
- HttpOnly = kein JS-Zugriff, Secure = nur HTTPS, SameSite = kein Cross-Site-Senden.
