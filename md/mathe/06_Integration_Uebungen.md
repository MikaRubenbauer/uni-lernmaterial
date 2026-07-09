---
fach: Mathe
typ: spickzettel
thema: Integration (Substitution / partielle Integration / PBZ)
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: hoch
aliases: [Integration, Substitution, partielle Integration, Partialbruchzerlegung, PBZ]
erstellt: 2026-07-05
---

# Spick: Integration — Quellnotiz

> Klausur-Bezug: 2024 Aufg. 1, 2023 Aufg. 4 (~7 P) · Quelle: [[Aufgaben9_Analysis_Integrale.pdf|Blatt 9]] · interaktiv: [[06_Integration_Lernskript.html|Lernskript]] · Navigation: [[_MOC]]

## Drei Werkzeuge

- **Substitution:** innere Funktion $u$ setzen, $du$ bilden, alles in $u$ übersetzen, integrieren, rück-substituieren.
- **Partielle Integration:** $\int u\,v' = uv - \int u'\,v$. $u$ nach **LIATE** (Log, Inverse, Algebraisch, Trig, Exp).
- **Partialbruchzerlegung (PBZ):** gebrochen-rationale Funktion in einfache Brüche zerlegen, einzeln integrieren.

## PBZ-Rezept

1. **Echt gebrochen?** Zählergrad < Nennergrad, sonst zuerst Polynomdivision.
2. **Nenner faktorisieren** (Aufgaben-Hinweis nutzen).
3. **Ansatz je Faktor:** einfach $(x-r)\to\frac{a}{x-r}$; $k$-fach $\to\frac{a_1}{x-r}+\dots+\frac{a_k}{(x-r)^k}$; irreduzibel quadratisch $(x^2+p)\to\frac{ax+b}{x^2+p}$.
4. **Koeffizienten:** Nenner wegmultiplizieren, geschickte $x$-Werte einsetzen.
5. **Integrieren:** $\frac{a}{x-r}\to a\ln|x-r|$; $\frac{ax+b}{x^2+p}$ aufspalten in $\frac a2\cdot\frac{2x}{x^2+p}\,(\to\ln)$ und $\frac{b}{x^2+p}\,(\to\arctan)$.

## Offenes Beispiel (Üb. 9.2.2, gegen Musterlösung geprüft)

$\displaystyle\int\frac{x^2+x}{(x^2+1)(x-1)}\,dx$. Ansatz $\frac{ax+b}{x^2+1}+\frac{c}{x-1}$, also $x^2+x=(ax+b)(x-1)+c(x^2+1)$.

- $x=1$: $2=2c\Rightarrow c=1$.
- $x=0$: $0=-b+c\Rightarrow b=1$.
- $x=-1$: $0=2a-2b+2c\Rightarrow a=0$.

$\Rightarrow \frac{1}{x^2+1}+\frac{1}{x-1}$, integriert: $\boxed{\arctan x+\ln|x-1|+C}$.

## Weitere Aufgaben (Blatt 9 + Klausur)

- **9.1.1 Substitution:** $\int e^{\sqrt{x+1}}dx=2e^{\sqrt{x+1}}(\sqrt{x+1}-1)$ ($u=\sqrt{x+1}$).
- **9.1.3 partielle Integration:** $\int\frac{x}{\sqrt{x+1}}dx=\frac23\sqrt{x+1}(x-2)$.
- **9.3 PBZ + bestimmtes Integral:** $\int_0^1\frac{10}{x^4+3x^3+3x^2+3x+2}dx=\frac\pi4+\frac{11}{2}\ln2-2\ln3$.
- **Klausur 2024/1:** $\int\frac{2}{(x^2+1)(x+1)}dx=-\frac12\ln|x^2+1|+\arctan x+\ln|x+1|+C$ ($a=-1,b=1,c=1$).

## Stolpersteine

1. PBZ nur bei echt gebrochen (sonst Polynomdivision).
2. Irreduzibel quadratischer Faktor → Zähler $ax+b$, kein reines $a$.
3. Mehrfache Nullstelle → alle Potenzen ansetzen.
4. $\frac{ax+b}{x^2+p}$ in ln-Teil ($\frac{2x}{x^2+p}$) und arctan-Teil ($\frac{1}{x^2+p}$) aufspalten.
5. Substitution: $dx$ mitübersetzen, am Ende rück-substituieren.

## Siehe auch
- [[06_Integration_Lernskript.html|interaktives Lernskript]] · [[Aufgaben9_Analysis_Integrale.pdf|Blatt 9]] · [[_MOC]]
