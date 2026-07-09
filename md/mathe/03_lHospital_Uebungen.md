---
fach: Mathe
typ: spickzettel
thema: l'Hospital & Grenzwerte
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: niedrig
aliases: [l'Hospital, lHospital, Grenzwerte, Regel von de l'Hospital]
erstellt: 2026-07-02
---

# Spick: l'Hospital & Grenzwerte — Quellnotiz

> Klausur-Bezug: 2024 Aufg. 7, 2023 Aufg. 7a · Quelle: [[Aufgaben5_Analysis_Hospital.pdf|Blatt 5]] (Übung 5.1) · interaktiv: [[03_lHospital_Lernskript.html|Lernskript]] · Navigation: [[_MOC]]

## Regel

Bei $\frac{f(x)}{g(x)}\to\frac00$ oder $\frac{\infty}{\infty}$:
$$\lim_{x\to a}\frac{f(x)}{g(x)}\overset{\text{H}}{=}\lim_{x\to a}\frac{f'(x)}{g'(x)}.$$
Zähler und Nenner **getrennt** ableiten (keine Quotientenregel). Ggf. mehrfach anwenden — aber **stoppen, sobald der Ausdruck bestimmt ist**.

## Andere Formen zuerst umformen

- $0\cdot\infty$ → einen Faktor in den Nenner: $f\cdot g=\dfrac{f}{1/g}$ → $\tfrac00$/$\tfrac{\infty}{\infty}$.
- $\infty-\infty$ → Hauptnenner bilden → $\tfrac00$.
- $0^0,\,1^\infty,\,\infty^0$ → $e$-Trick $u^v=e^{v\ln u}$, Exponent $v\ln u$ untersuchen.

## Übung 5.1 (Ergebnisse gegen Musterlösung geprüft)

1. $\displaystyle\lim_{x\to\infty}x\tan\tfrac1x$: $0\cdot\infty\to\frac{\tan(1/x)}{1/x}$, l'Hospital $=\mathbf{1}$.
2. $\displaystyle\lim_{x\to0}\left(\tfrac1{\sin x}-\tfrac1x\right)$: $\infty-\infty\to\frac{x-\sin x}{x\sin x}$, 2× l'Hospital $=\mathbf{0}$.
3. $\displaystyle\lim_{x\to\infty}x\ln\!\left(1+\tfrac ax\right)=\mathbf{a}$ (via $\frac{\ln(1+a/x)}{1/x}$).
4. $\displaystyle\lim_{x\to\infty}x\ln\tfrac{x+1}{x-1}=\mathbf{2}$.
5. $\displaystyle\lim_{x\to0^+}x^{2x}=e^{\lim 2x\ln x}=e^0=\mathbf{1}$.
6. **„Was ist falsch?"** Nach dem 1. Schritt ist $\frac{3x^2-2}{2x}\big|_{1}=\frac12$ **bestimmt** → man darf l'Hospital **nicht** noch einmal anwenden. Richtiger Grenzwert $\mathbf{0{,}5}$.

## Klausur-Limits

- $\displaystyle\lim_{x\to0}\frac{\sin(5x^2)}{x^2}\overset{H}{=}\lim\frac{10x\cos(5x^2)}{2x}=5\cos(5x^2)\to\mathbf{5}$.
- $\displaystyle\lim_{x\to\infty}\frac{\cos^2 x}{x}$: **l'Hospital versagt** (Ableitung $-\sin(2x)$ hat keinen Grenzwert). Einschnürung: $0\le\frac{\cos^2x}{x}\le\frac1x\to0\Rightarrow\mathbf{0}$.

## Stolpersteine

1. Nur $\tfrac00$ / $\tfrac{\infty}{\infty}$; sobald bestimmt → aufhören (5.1.6).
2. Getrennt ableiten, keine Quotientenregel.
3. l'Hospital kann versagen (oszillierender Zähler) → dann Einschnürung/Umformen.
4. $0\cdot\infty$, $\infty-\infty$, $0^0$ erst umschreiben.

## Siehe auch
- [[03_lHospital_Lernskript.html|interaktives Lernskript]] · [[Aufgaben5_Analysis_Hospital.pdf|Blatt 5]] · [[_MOC]]
- Taylor-Übung (gehört zum selben Kalenderblock): [[02_Taylor_Lernskript.html]]

## Verwandt

[[_MOC|Mathe-MOC]] · [[02_Taylor_Uebungen|Thema 2 Taylor]] (Grenzwert-Schätzung über T₂)
