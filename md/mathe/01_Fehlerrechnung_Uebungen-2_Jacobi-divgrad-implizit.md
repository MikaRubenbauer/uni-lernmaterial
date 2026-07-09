---
fach: Mathe
typ: spickzettel
thema: Jacobi, div/grad, implizite Ableitung
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: mittel
aliases: [Jacobi, Funktionaldeterminante, Divergenz, implizite Ableitung]
erstellt: 2026-06-29
---

# Spick: Jacobi, div/grad & implizite Ableitung — durchgerechnete Übungen

> Klausur-Bezug: 2023 Aufg. 4c (div/grad), 2023 Aufg. 7b + 2024 (implizite Abl.) · Quellen: [[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]], [[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]] · Rezept: [[01_Fehlerrechnung_Rezept]] · Navigation: [[_MOC]]

Restliche Aufgabentypen von Thema 1. Alle Rechenwege gegen die PDF-Musterlösungen verifiziert.

---

## Übung 4.2 — Jacobi-Matrix & Funktionaldeterminante ([[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]])

**Gegeben:** $f=\begin{pmatrix} x_1\,e^{x_1x_2}\\[1mm] \dfrac{x_1}{\ln x_2}\end{pmatrix}$.

Die **Jacobi-Matrix** ist zeilenweise der Gradient jeder Komponente: $\dfrac{\partial f}{\partial x^T}=\begin{pmatrix}\partial f_1/\partial x_1 & \partial f_1/\partial x_2\\ \partial f_2/\partial x_1 & \partial f_2/\partial x_2\end{pmatrix}$.

**Zeile 1** ($f_1=x_1 e^{x_1x_2}$, Produkt- und Kettenregel):

$\dfrac{\partial f_1}{\partial x_1}=e^{x_1x_2}+x_1\cdot x_2\,e^{x_1x_2}=e^{x_1x_2}(1+x_1x_2)$

$\dfrac{\partial f_1}{\partial x_2}=x_1\cdot x_1\,e^{x_1x_2}=x_1^2\,e^{x_1x_2}$

**Zeile 2** ($f_2=x_1(\ln x_2)^{-1}$):

$\dfrac{\partial f_2}{\partial x_1}=\dfrac{1}{\ln x_2}$

$\dfrac{\partial f_2}{\partial x_2}=x_1\cdot(-1)(\ln x_2)^{-2}\cdot\dfrac{1}{x_2}=-\dfrac{x_1}{x_2(\ln x_2)^2}$

$$\frac{\partial f}{\partial x^T}=\begin{pmatrix} e^{x_1x_2}(1+x_1x_2) & x_1^2\,e^{x_1x_2}\\[2mm] \dfrac{1}{\ln x_2} & -\dfrac{x_1}{x_2(\ln x_2)^2}\end{pmatrix}$$

**Funktionaldeterminante** (Hauptdiagonale minus Nebendiagonale):
$$\det = -\frac{x_1\,e^{x_1x_2}(1+x_1x_2)}{x_2(\ln x_2)^2}-\frac{x_1^2\,e^{x_1x_2}}{\ln x_2}.$$

> [!check] Self-Check
> Jacobi deckt sich exakt mit der PDF-Musterlösung. (Determinante dort nicht angegeben, hier ergänzt.)

---

## Übung 4.3 — Divergenz & Gradient ([[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]])

**(1)** $F(x,y,z)=xyz$ (Skalarfeld). Erst Gradient, dann Divergenz:
$$\nabla F=(yz,\,xz,\,xy)^T,\qquad \operatorname{div}(\nabla F)=\frac{\partial(yz)}{\partial x}+\frac{\partial(xz)}{\partial y}+\frac{\partial(xy)}{\partial z}=0+0+0=0.$$
(Das ist der Laplace-Operator $\Delta F$; für $xyz$ gleich null.)

**(2)** $F(x,y,z)=(x,\,y^2,\,z^3)^T$ (Vektorfeld). Erst Divergenz (Skalar), dann Gradient:
$$\operatorname{div}F=1+2y+3z^2,\qquad \nabla(\operatorname{div}F)=(0,\,2,\,6z)^T.$$

> [!warning] Stolperstein
> Reihenfolge & Objekttyp: $\operatorname{div}(\nabla F)$ startet mit einem **Skalarfeld** (Ergebnis Skalar), $\nabla(\operatorname{div}F)$ mit einem **Vektorfeld** (Ergebnis Vektor).

---

## Übung 6.1 — Implizite Ableitung ([[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]])

**Rezept.** Gleichung auf $F(x,y)=0$ bringen, dann
$$\frac{dy}{dx}=-\frac{F_x}{F_y}\qquad(F_x=\partial F/\partial x,\ y\text{ konstant};\quad F_y=\partial F/\partial y,\ x\text{ konstant}).$$

**(1)** $F=y\ln x-2x\ln y=0$. $\;F_x=\dfrac{y}{x}-2\ln y,\quad F_y=\ln x-\dfrac{2x}{y}.$
$$\frac{dy}{dx}\Big|_{(1,1)}=-\frac{1-0}{0-2}=\frac12.$$

**(2)** $xy^2=16-x^2y\Rightarrow F=xy^2+x^2y-16=0$. $\;F_x=y^2+2xy,\quad F_y=2xy+x^2.$
$$\frac{dy}{dx}\Big|_{(2,2)}=-\frac{4+8}{8+4}=-1.$$

**(3)** $F=ye^x-xe^y=0$. $\;F_x=ye^x-e^y,\quad F_y=e^x-xe^y.$
$$\frac{dy}{dx}\Big|_{(0,0)}=-\frac{0\cdot1-1}{1-0}=1.$$

> [!warning] Stolperstein
> An $(1,1)$ liefert (3) $F_x=e-e=0$ und $F_y=e-e=0$, also $\tfrac00$ — ein **singulärer Punkt**, die Steigung ist mit dieser Formel nicht bestimmbar. (Die reproduzierte Altklausur-Lösung wertet abweichend bei $(0,1)$ aus, $e-1$; vermutlich Tippfehler im Blatt.)

---

## Merksätze

1. **Jacobi = zeilenweise Gradienten** der Komponenten; Funktionaldeterminante nur bei quadratischer Jacobi.
2. **Produkt-/Kettenregel** sauber trennen (Eintrag $(1,1)$ in 4.2 ist der Klassiker für Vorzeichen-/Term-Fehler).
3. $\operatorname{div}(\nabla F)$ vs. $\nabla(\operatorname{div}F)$: erst prüfen, ob $F$ Skalar- oder Vektorfeld ist.
4. **Implizit:** immer zuerst auf $F=0$ bringen, dann $-F_x/F_y$. Bei $\tfrac00$ liegt ein singulärer Punkt vor.

## Siehe auch

- [[01_Fehlerrechnung_Rezept]] · [[01_Fehlerrechnung_Uebungen]] · [[01_Fehlerrechnung_Lernskript.html|interaktives Lernskript]]
- [[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]] · [[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]] · [[_MOC]]
