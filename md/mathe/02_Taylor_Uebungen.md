---
fach: Mathe
typ: spickzettel
thema: Taylor-Approximation
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: hoch
erstellt: 2026-07-01
aliases: []
---

# Spick: Taylor-Approximation

> Klausur-Bezug: Aufg. 2024/4 (~7P), 2023/2 (~9P) · Quelle: [[Aufgaben8_Analysis_Approximation.pdf|Blatt 8]]

## Formeln / Definitionen

$$T_2(x)=f(x_0)+f'(x_0)\,(x-x_0)+\tfrac12 f''(x_0)\,(x-x_0)^2$$

Allgemein: $n$-tes Glied $=\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n$.

## DAS Rezept (Schritt für Schritt)

1. $x_0$ prüfen: liegt es im Definitionsbereich von $f$? Sonst anderen $x_0$ wählen.
2. $f'(x)$ und $f''(x)$ bilden.
3. $f(x_0)$, $f'(x_0)$, $f''(x_0)$ als Zahlen auswerten.
4. In $T_2(x)$ einsetzen, $(x-x_0)$-Klammern ausmultiplizieren, nach Potenzen von $x$ sortieren.
5. Anwendung: Nullstellen ($T_2=0$, Mitternachtsformel) oder Extremwert ($T_2'=0$, Typ über Vorzeichen von $a$).
6. Zwei Extremstellen gesucht? $T_2$ ist immer eine Parabel (1 Extremum) → auf **Grad 3** erhöhen
   ($T_3'$ ist dann quadratisch, bis zu 2 Nullstellen).

> [!tip] Faktor $\tfrac12$ beim quadratischen Glied nicht vergessen; Nullstellen/Extremwerte von $T_n$ sind nur Näherungen für $f$, nur nahe $x_0$ verlässlich.

## Durchgerechnetes Beispiel

### Übung 8.2 — $\cosh x$ um $x_0=0$
$f'(x)=\sinh x$, $f''(x)=\cosh x$. $f(0)=1,f'(0)=0,f''(0)=1$.
$$T(x)=\sum_{i=0}^\infty \frac{x^{2i}}{(2i)!}=1+\frac{x^2}{2!}+\frac{x^4}{4!}+\dots$$
Nur gerade Potenzen ⇒ $f(-x)=f(x)$ (gerade Funktion). $T_2(x)=1+\tfrac12x^2$: Parabel mit $a=\tfrac12>0$ ⇒ Minimum bei $x=0$. Gegen Musterlösung 8.2 verifiziert.

### Übung 8.3 — $e^x$ um $x_0=0$ und $x_0=1$
Um 0: $e^x=\sum \frac{x^i}{i!}$. Um 1 (mit $f^{(i)}(1)=e$): $e^x=e\sum\frac{(x-1)^i}{i!}=e\cdot e^{x-1}=e^x$. Beide Reihen liefern exakt dasselbe Ergebnis — gilt nur für die volle Reihe, nicht für ein abgebrochenes Polynom. Gegen Musterlösung 8.3 verifiziert.

### Übung 8.4 — $\sinh x+\cosh x=e^x$
$\sinh x=x+\frac{x^3}{3!}+\frac{x^5}{5!}+\dots$, $\cosh x=1+\frac{x^2}{2!}+\frac{x^4}{4!}+\dots$. Summe $=1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+\dots=e^x$. Gegen Musterlösung 8.4 verifiziert.

### Klausur 2024, Aufgabe 4 — $f(x)=(x^3+1)\cos(2x)$, $T_2$ bei $x_0=0$ (7P)
$f'(x)=3x^2\cos(2x)-2(x^3+1)\sin(2x)$
$f''(x)=6x\cos(2x)-12x^2\sin(2x)-4(x^3+1)\cos(2x)$
$f(0)=1$, $f'(0)=0$, $f''(0)=-4$ ⇒ $T_2(x)=1-2x^2$.

**Nullstellen:** $1-2x^2=0\Rightarrow x=\pm\frac{1}{\sqrt2}\approx\pm0{,}7071$.

**Zwei Extremstellen:** $T_2$ = Parabel = 1 Extremum (Max bei 0). $f'''(0)=6$ ⇒ $T_3(x)=x^3-2x^2+1$.
$T_3'(x)=3x^2-4x=x(3x-4)=0\Rightarrow x=0$ (Max) oder $x=\tfrac43$ (Min, da $T_3''(\tfrac43)=4>0$).

Probe: $f(0{,}1)\approx0{,}98105$; $T_2(0{,}1)=0{,}98$; $T_3(0{,}1)=0{,}981$ — $T_3$ näher an $f$.
*(Keine gedruckte Musterlösung im Altklausur-PDF für diese Aufgabe — Ergebnis per Gegenprobe/Ableitungskontrolle selbst verifiziert.)*

### Klausur 2023, Aufgabe 2 — $f(x)=\ln x-3^x$, $T_2$ bei $x_0=1$ (9P)
**Falle in 2b):** $\ln x$ bei $x_0=0$ nicht definiert ⇒ kein Taylor-Polynom dort möglich. Deshalb 2d) mit $x_0=1$.

$f'(x)=\frac1x-3^x\ln3$, $f''(x)=-\frac{1}{x^2}-3^x(\ln3)^2$.
Mit $\ln3\approx1$: $f(1)=-3$, $f'(1)\approx-2$, $f''(1)\approx-4$.
$T_2(x)=-3-2(x-1)-2(x-1)^2 = -2x^2+2x-3$ (Probe: $T_2(1)=-3$ ✓).

**Extremwert schätzen:** $T_2'(x)=-4x+2=0\Rightarrow x=0{,}5$; $a=-2<0\Rightarrow$ Maximum; $T_2(0{,}5)=-2{,}5$.

**Zusätzliches Minimum (2f):** gleiche Lösung wie 2024/4.3 — Taylor-Polynom auf mind. Grad 3 erhöhen, damit die Ableitung mehr als eine Nullstelle liefern kann.
*(Keine gedruckte Musterlösung im Altklausur-PDF für diese Aufgabe — Ergebnis per Gegenprobe/Ableitungskontrolle selbst verifiziert.)*

## Siehe auch

- [[Aufgaben8_Analysis_Approximation.pdf|Blatt 8]]
- [[Reischl, Mathematik, Sem2, 2024.pdf|Altklausur 2024]] (Aufg. 4)
- [[Reischl, Mathematik, Sem2, 2023.pdf|Altklausur 2023]] (Aufg. 2)
- [[02_Taylor_Lernskript.html|Lernskript Thema 2 (interaktiv, HTML)]]
- [[01_Fehlerrechnung_Rezept]]

## Verwandt

[[_MOC|Mathe-MOC]] · [[03_lHospital_Uebungen|Thema 3 l'Hospital]] (Grenzwerte — Taylor als Alternative) · [[05_Regression_Uebungen|Thema 5 Interpolation]] (Approximation ↔ Interpolation) · [[01_Fehlerrechnung_Rezept|Thema 1 Ableitungen]]
