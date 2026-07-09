---
fach: Mathe
typ: spickzettel
thema: Fehlerrechnung & Gradient
tags: [mathe/analysis, typ/rezept]
klausur: 2026-07-23
status: done
prio: hoch
aliases: [Fehlerrechnung, Gradient, Fehlerfortpflanzung]
erstellt: 2026-06-27
deckt: [Blatt 4, Blatt 6]
---

# Rezept: Mehrdim. Ableitungen & Fehlerrechnung

> Klausur-Bezug: 2024 Aufg. 2 · 2023 Aufg. 3 · ~5–7 P · Quellen: [[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]], [[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]] · Navigation: [[_MOC]]

Klausur Reischl (23.07.2026) — Aufg. 2024/2, 2023/3. Reines Rechenrezept, ~5–7 P.

## Grundbausteine

**Partielle Ableitung** $\frac{\partial f}{\partial x_i}$: nach $x_i$ ableiten, alle anderen Variablen wie Konstanten behandeln.

**Gradient** = Spaltenvektor aller ersten partiellen Ableitungen:
$$\nabla f = \left(\frac{\partial f}{\partial x_1},\dots,\frac{\partial f}{\partial x_n}\right)^T$$

**Hesse-Matrix** = alle zweiten partiellen Ableitungen, $H_{ij}=\frac{\partial^2 f}{\partial x_i \partial x_j}$ (symmetrisch).

**Totales Differential** (lineare Näherung der Fehlerfortpflanzung):
$$df = \sum_i \frac{\partial f}{\partial x_i}\,dx_i$$

## Fehlerrechnung — DAS Rezept

Gegeben: $f(x_1,\dots,x_n)$, Messpunkt $(x_1^0,\dots)$, Messfehler $\Delta x_i$ (oft als % vom Messwert).

1. **Funktionswert** $f$ am Messpunkt berechnen (für relativen Fehler nötig).
2. **Alle partiellen Ableitungen** $\frac{\partial f}{\partial x_i}$ bilden.
3. **Am Messpunkt einsetzen** → Zahlenwerte $\frac{\partial f}{\partial x_i}\big|_0$.
4. **Absolute Messfehler** bestimmen: bei „p % Ungenauigkeit" gilt $\Delta x_i = \frac{p}{100}\cdot |x_i^0|$.
5. **Max. absoluter Fehler** = Summe der Beträge:
$$\boxed{\;\Delta f_{\max} = \sum_i \left|\frac{\partial f}{\partial x_i}\Big|_0\right|\cdot \Delta x_i\;}$$
6. **Max. relativer Fehler**:
$$\boxed{\;\frac{\Delta f_{\max}}{|f|}\;}\quad(\cdot\,100\,\%)$$

> **Beträge nicht vergessen!** Jeder Summand wird positiv addiert (Worst Case). Kein Vorzeichen-Wegkürzen.

**Welchen Parameter genau messen?** Den mit dem **größten Summanden** $\left|\frac{\partial f}{\partial x_i}\big|_0\right|\cdot\Delta x_i$ — er trägt am meisten zum Gesamtfehler bei.

## Mini-Beispiel (Klausur 2024, Aufg. 2)

$s = x_1\, e^{x_2 + x_3^2}$, Punkt $x_1=2,\ x_2=-1,\ x_3=1$, je 10 % Messfehler.

- Exponent: $x_2+x_3^2 = -1+1 = 0 \Rightarrow e^0=1$, also $s = 2$.
- $\frac{\partial s}{\partial x_1}=e^{x_2+x_3^2}=1$
- $\frac{\partial s}{\partial x_2}=x_1 e^{x_2+x_3^2}=2$
- $\frac{\partial s}{\partial x_3}=x_1 e^{x_2+x_3^2}\cdot 2x_3 = 4$
- $\Delta x_1=0.2,\ \Delta x_2=0.1,\ \Delta x_3=0.1$
- $\Delta s_{\max}=|1|\cdot0.2+|2|\cdot0.1+|4|\cdot0.1 = 0.2+0.2+0.4 = 0.8$
- relativ: $\frac{0.8}{2}=0.4 = 40\,\%$
- größter Beitrag: $x_3$ (0.4) → $x_3$ am genauesten messen.

## Verwandt

[[_MOC|Mathe-MOC]] · [[04_Lagrange_Uebungen|Thema 4 Lagrange]] (Gradient als Werkzeug dort) · [[02_Taylor_Uebungen|Thema 2 Taylor]] (nutzt dieselben Ableitungen)
