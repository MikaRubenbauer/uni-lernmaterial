---
fach: Mathe
typ: spickzettel
thema: Differentialgleichungen (separabel + linear)
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: hoch
aliases: [DGL, Differentialgleichungen, charakteristisches Polynom, Laplace, Trennung der Variablen]
erstellt: 2026-07-05
---

# Spick: Differentialgleichungen — Quellnotiz

> Klausur-Bezug: 2024 Aufg. 6+7, 2023 Aufg. 1 · Quelle: [[Aufgaben11_Analysis_DGL .pdf|Blatt 11]] (+ Blatt 10 separabel) · interaktiv: [[08_DGL_Lernskript.html|Lernskript]] · Navigation: [[_MOC]]

## Typ A — Separabel (Trennung der Variablen)

$g(y)\,dy=f(x)\,dx$ → beide Seiten integrieren → $c$ aus Anfangsbedingung.
- $y\,y'=\frac{1}{1+x^2},\,y(0)=1$: $\frac{y^2}{2}=\arctan x+c$, $c=\frac12$ → $y=\sqrt{2\arctan x+1}$.
- $2y'y=\cos x,\,y(0)=1$: $y^2=\sin x+c$, $c=1$ → $y=\sqrt{\sin x+1}$.

## Typ B — Linear, konstante Koeffizienten

1. **Homogen:** char. Polynom ($y^{(k)}\to\lambda^k$), Nullstellen → $y_h$.
   - verschiedene reelle $\lambda_1\ne\lambda_2$: $c_1e^{\lambda_1x}+c_2e^{\lambda_2x}$.
   - doppelt $\lambda$: $c_1e^{\lambda x}+c_2x e^{\lambda x}$.
   - komplex $a\pm bi$: $e^{ax}(c_1\cos bx+c_2\sin bx)$.
2. **Speziell $y_s$:** Ansatz vom Typ der rechten Seite (Konstante→$q_0$; Polynom→$q_0+q_1x+\dots$; $e^{kx}$→$qe^{kx}$; $\sin/\cos$→$q_1\cos+q_2\sin$). Bei Resonanz $\cdot x$.
3. **Gesamt** $y=y_h+y_s$, dann **Anfangsbedingungen** → $c_1,c_2$.
4. **Summe** verschiedener Störtypen → getrennt lösen und addieren (Superposition; 2024/7.2).

## Offenes Beispiel (Blatt 11, Üb. 10.2)

$y''-4y'+4y=4$, $y(0)=1,y'(0)=1$:
- char. $(\lambda-2)^2=0$ → $\lambda=2$ doppelt → $y_h=c_1e^{2x}+c_2xe^{2x}$.
- $y_s=q_1$: $4q_1=4\Rightarrow q_1=1$.
- $y=c_1e^{2x}+c_2xe^{2x}+1$. AB: $y(0)=c_1+1=1\Rightarrow c_1=0$; $y'(0)=2c_1+c_2=1\Rightarrow c_2=1$.
- **$y(x)=xe^{2x}+1$** (auch per Laplace: $Y=\frac{1}{(s-2)^2}+\frac1s$).

## Weitere

- $y''-5y'+6y=6x+1$ (Üb. 10.4): $y=-3e^{2x}+2e^{3x}+1+x$.
- $y'''-3y'-2y=0$ (Üb. 10.1.2, Nullstelle 2): $(\lambda-2)(\lambda+1)^2$ → $y=e^{2x}-e^{-x}-3xe^{-x}$.

## Siehe auch
- [[08_DGL_Lernskript.html|interaktives Lernskript]] · [[Aufgaben11_Analysis_DGL .pdf|Blatt 11]] · [[_MOC]]
