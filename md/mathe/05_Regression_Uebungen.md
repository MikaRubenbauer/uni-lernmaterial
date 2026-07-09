---
fach: Mathe
typ: spickzettel
thema: Regression & Interpolation (Newton/Lagrange)
tags: [mathe/analysis, typ/spickzettel, typ/rezept]
klausur: 2026-07-23
status: done
prio: hoch
---

# Thema 5 — Regression & Interpolation (Quellnotiz)

> Primäres Lernmaterial: [[05_Regression_Lernskript.html|interaktives Lernskript]] (Newton-Rechner + Normalgleichungs-Rechner).
> Quellen: [[Aufgaben7_Analysis_Lagrange_Regression.pdf|Blatt 7]] (Übung 7.2), Altklausur 2024 A5 (7 P), 2023 A6 (10 P).
> Alle Rechnungen SymPy-verifiziert (Master-Session 2026-07-04).

## Rezepte

**Regression aufstellen:** Ansatz $f=\sum a_j\varphi_j(x)$ → $A$: Zeile pro Messpunkt, Spalte pro Basisfunktion ($A_{ij}=\varphi_j(x_i)$); $x=(a_j)$, $y=(y_i)$. Grad 0 → Lösung = Mittelwert. Lösung allgemein: $A^TA\,x=A^Ty$.

**Linearisieren (Klausur-Twist):** $e^{a_0+a_1x}$ → $\ln y=a_0+a_1x$ ($y$-Vektor: $\ln y_i$). $\sqrt{1+a_0+a_1x}$ → $y^2-1=a_0+a_1x$ ($y$-Vektor: $y_i^2-1$).

**Newton:** Ansatz $b_0+b_1(x-x_0)+b_2(x-x_0)(x-x_1)+\dots$ → gestaffeltes GLS ODER dividierte Differenzen (durch Spannweite $x_{i+k}-x_i$ teilen!) → ausmultiplizieren → Probe.

**Lagrange-Interpolation:** $p=\sum y_iL_i$, $L_i=\prod_{j\ne i}\frac{x-x_j}{x_i-x_j}$.

## Klausur 2024 A5 — Punkte (−1|1),(0|1),(1|1),(2|7) (verifiziert)

- Ansatz: $p=b_0+b_1(x+1)+b_2(x+1)x+b_3(x+1)x(x-1)$.
- GLS gestaffelt: $b_0=1$; $b_0+b_1=1$; $b_0+2b_1+2b_2=1$; $b_0+3b_1+6b_2+6b_3=7$.
- $b=(1,0,0,1)$ (DD-Tabelle: Stufe 1: 0,0,6 · Stufe 2: 0,3 · Stufe 3: 1).
- Kompakt: $p(x)=1+(x+1)x(x-1)=\mathbf{x^3-x+1}$; Probe an allen 4 Punkten ✓.
- 5.5 $\sqrt{1+a_0+a_1x}$: quadrieren → $A=\begin{pmatrix}1&-1\\1&0\\1&1\\1&2\end{pmatrix}$, $x=(a_0,a_1)^T$, $y=(0,0,0,48)^T$.
- 5.6 Grad 0 nicht sinnvoll: Daten nicht konstant ($P_3$ bricht aus, Trend).

## Klausur 2023 A6 — Punkte (1|1),(2|3),(3|3),(4|1) (verifiziert)

- a) Grad 0: $A=(1,1,1,1)^T$ · Grad 1: $A=\begin{pmatrix}1&1\\1&2\\1&3\\1&4\end{pmatrix}$ · $e^{a_0+a_1x}$: logarithmieren, $y=(0,\ln3,\ln3,0)^T$.
- b) Nicht sinnvoll: Daten steigen und fallen — weder konstant noch monoton.
- c) Besser: Polynom 2. Grades, $A=\begin{pmatrix}1&1&1\\1&2&4\\1&3&9\\1&4&16\end{pmatrix}$. (Vertiefung: Lösung $a=(-3,5,-1)$.)
- d) Grad 0: Mittelwert $=2$.
- e) Lagrange durch $(-1|4),(0|-2),(1|12)$: $L_0=\frac{x(x-1)}2$, $L_1=-(x^2-1)$, $L_2=\frac{x(x+1)}2$ → $p(x)=\mathbf{10x^2+4x-2}$ (Probe ✓).

## Blatt 7.2 (verifiziert)

Grad 2 wie oben; $a_0e^{-x}+a_1e^x$ ist bereits linear in den Koeffizienten → $A$ mit Spalten $e^{-x_i}, e^{x_i}$. Grad 1 nicht sinnvoll (nicht monoton); Grad 0 → Mittelwert 2, waagrechte Gerade. Nebenbefund: Ausgleichsgerade (Grad 1) ist $a=(2,0)$ — waagrecht wegen Symmetrie.

## Stolpersteine

Zeile=Punkt/Spalte=Basisfunktion · „linear" = linear in Koeffizienten · transformierte $y$-Werte beim Linearisieren · DD durch Spannweite teilen · immer Endprobe.

## Verwandt

[[_MOC|Mathe-MOC]] · [[02_Taylor_Uebungen|Thema 2 Taylor]] (Approximation ↔ Interpolation) · [[04_Lagrange_Uebungen|Thema 4 Lagrange]] (erster Block des Wochenendes)
