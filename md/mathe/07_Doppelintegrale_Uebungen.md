---
fach: Mathe
typ: spickzettel
thema: Doppelintegrale & div/rot
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: mittel
aliases: [Doppelintegrale, iterierte Integrale, div grad, rot grad]
erstellt: 2026-07-05
---

# Spick: Doppelintegrale & div/rot — Quellnotiz

> Quelle: [[Aufgaben10_Analysis_DoppelIntegrale_TdV.pdf|Blatt 10]] (Üb. 10.1) · interaktiv: [[07_Doppelintegrale_Lernskript.html|Lernskript]] · Navigation: [[_MOC]]

## Rezept

Von **innen nach außen**: erst inneres Integral (andere Variable konstant), dann äußeres. Innere Grenzen dürfen die äußere Variable enthalten, äußere Grenzen sind Zahlen.

## Offenes Beispiel (Üb. 10.1.1)

$\int_0^1\int_{-x}^{x} 3x\,dy\,dx$: innen $3x\cdot[y]_{-x}^{x}=3x\cdot 2x=6x^2$; außen $\int_0^1 6x^2 dx=6\cdot\tfrac13=\boxed{2}$.

## Weitere (gegen Musterlösung geprüft)

- $\int_0^1\int_{-1}^1 xe^{xy}dy\,dx=e+e^{-1}-2$ (innen $[e^{xy}]_{-1}^1=e^x-e^{-x}$).
- $\int_0^1\int_0^1 6y^2 dy\,dx=2$.
- $\int_1^2\int_1^2 \tfrac{1}{xy}dy\,dx=(\ln 2)^2$.
- $\iint \cos(x+y)dy\,dx=-\cos(x+y)\,(+c_1x+c_2)$.

## div/rot

- $\operatorname{div}(\nabla F)$ = Laplace; für $F=xyz$: $\nabla F=(yz,xz,xy)^T$, $\operatorname{div}=0$.
- $\operatorname{rot}(\nabla f)=(0,0,0)^T$ **immer**. Für $f=x^2+y+z$: $\nabla f=(2x,1,1)^T$, $\operatorname{rot}=0$.

## Stolperstein

- **Polstelle im Intervall** (Üb. 10.1.7): $\int_0^2\frac{1}{x-1}dx$ — bei $x=1$ nicht definiert → zerlegen (uneigentlich, divergiert); naive Rechnung „=0" ist falsch.

## Siehe auch
- [[07_Doppelintegrale_Lernskript.html|interaktives Lernskript]] · [[Aufgaben10_Analysis_DoppelIntegrale_TdV.pdf|Blatt 10]] · [[_MOC]]
