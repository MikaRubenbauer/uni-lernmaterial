---
fach: Mathe
typ: spickzettel
thema: Lagrange-Optimierung & Höhenlinien
tags: [mathe/analysis, typ/spickzettel, typ/rezept]
klausur: 2026-07-23
status: done
prio: hoch
---

# Thema 4 — Lagrange & Höhenlinien (Quellnotiz)

> Primäres Lernmaterial: [[04_Lagrange_Lernskript.html|interaktives Lernskript]] (Höhenlinien-Labor mit beiden Klausur-Szenarien).
> Quellen: [[Aufgaben7_Analysis_Lagrange_Regression.pdf|Blatt 7]] (Übung 7.1), Altklausur 2024 A3 (9 P), 2023 A5 (8 P).
> Alle Rechnungen SymPy-verifiziert (Master-Session 2026-07-04).

## Rezept

**Weg A — Einsetzen** (Restriktion $y=r(x)$): $h(x)=Q(x,r(x))$ → $h'(x)=0$ → Kandidat; **Min/Max über $h''$** begründen; $Q^*=h(x^*)$.

**Weg B — Lagrange:** $g(x,y)=0$ (Nullform!) → $L=Q+\lambda g$ → $\partial_x L=\partial_y L=\partial_\lambda L=0$ → lösen.
Reischl-Muster: $Q$ linear in $y$ → $\partial_y L$ liefert sofort $\lambda$ (meist $\lambda=-1$).

**Weg C — zeichnerisch:** Höhenlinien $Q=c$ nach $y$ auflösen, Restriktion einzeichnen, Optimum = Berührpunkt. $\nabla Q$ steht senkrecht auf Höhenlinien.

## Blatt 7.1 — Q = x²+y, y = mx+1 (verifiziert)

- Höhenlinien: $y=c-x^2$ (Parabeln nach unten, Scheitel $(0,c)$).
- Zeichnerisch: $m=0$ → Min $(0,1)$; $m=1$ → Min $(-\tfrac12,\tfrac12)$.
- Rechnerisch $m=2$: $L=x^2+y+\lambda(y-2x-1)$; $\lambda=-1$, $x=-1$, $y=-1$ → $P(-1,-1)$, $Q^*=0$.
- ⚠️ **Musterlösungsfehler:** Blatt sagt „$Q\to\max$" — tatsächlich **Minimum**: $h(x)=(x+1)^2\ge 0$, $h''=2>0$. Ein Maximum existiert entlang der Geraden nicht.
- Max. Anzahl Lösungen: **1** ($h'$ linear).

## Klausur 2024 A3 — Q = y + cosh x, y = ax (verifiziert)

⚠️ **Protokollfehler:** PDF schreibt $y\cdot\cosh x$ — damit existiert entlang $y=ax$ kein Optimum ($h'=a(\cosh x+x\sinh x)\ge a$) und der Hinweis $\sinh(0{,}88)=1$ wäre sinnlos. Korrekt: $y+\cosh x$.

- 3.1 Höhenlinien: $y=c-\cosh x$ (Scheitel $(0,c-1)$).
- 3.3 **Minimum** für jedes $a$: $h''=\cosh x>0$.
- 3.4 $\nabla Q=(\sinh x,\,1)^T$; $\nabla Q(0,0)=(0,1)^T$ (Pfeil nach oben).
- 3.5 Höhenlinie durch $(0,0)$: $c=1$ → $y=1-\cosh x$.
- 3.6 $a=1$: $\partial_y$: $\lambda=-1$ → $\sinh x=-1$ → $x^*=y^*=-0{,}88$; $Q^*=-0{,}88+\sqrt2\approx 0{,}53$ (denn $\cosh=\sqrt{1+\sinh^2}=\sqrt2$).
- 3.7 Ohne Optimum: senkrechte Gerade $x=c$ ($Q$ dann linear in $y$).

## Klausur 2023 A5 — Schema (Zielfunktion im Protokoll verloren)

Restriktion $y=-(x-1)^2+2$. Teilaufgaben identisch zum 2024-Schema (Gradienten, $\nabla Q$ in $(0|0)$, Optimum + Begründung, Höhenlinie durch $(0|0)$, lösen, Konzeptfrage).
f) Gerade ohne Extremum ⇔ $f'(x)=-m$ unlösbar ⇔ Gerade nie tangential zu einer Höhenlinie.

## Stolpersteine

Nullform vor $\lambda g$ · alle 3 Gleichungen hinschreiben · Min/Max nur über $h''$ · $\cosh=\sqrt{1+\sinh^2}$ · Quellenfehler (s.o.) kennen.

## Verwandt

[[_MOC|Mathe-MOC]] · [[01_Fehlerrechnung_Rezept|Thema 1 Gradienten/Hesse]] (∇Q ist dasselbe Werkzeug) · [[05_Regression_Uebungen|Thema 5 Regression/Interpolation]] (zweiter Block des Wochenendes)
