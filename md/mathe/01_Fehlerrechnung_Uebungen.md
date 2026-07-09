---
fach: Mathe
typ: spickzettel
thema: Fehlerrechnung Übungen
tags: [mathe/analysis, typ/spickzettel]
klausur: 2026-07-23
status: done
prio: hoch
aliases: []
erstellt: 2026-06-28
---

# Spick: Fehlerrechnung & Gradient — durchgerechnete Übungen

> Klausur-Bezug: Aufg. 2024/2 · 2023/3 · ~5–7 P · Quellen: [[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]], [[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]] · Rezept: [[01_Fehlerrechnung_Rezept]] · Navigation: [[_MOC]]

Vollständige Rechenwege zu den Übungen, jeweils gegen die Musterlösung im PDF verifiziert. Das reine Kochrezept steht in [[01_Fehlerrechnung_Rezept]]; hier sind die Schritte ausgeschrieben.

---

## Übung 6.3 — Fehlerrechnung Wahrscheinlichkeitsdichte ([[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]])

**Gegeben:** $f(x,y) = e^{-(x^2+y^2)}$, Messpunkt $x_0 = 1$, $y_0 = 2$, Ungenauigkeiten $10\,\%$ in $x$ und $20\,\%$ in $y$.

### Schritt 1 — Funktionswert am Messpunkt

Wird für den relativen Fehler gebraucht.
$$f(x_0,y_0) = e^{-(1^2 + 2^2)} = e^{-(1+4)} = e^{-5} \approx 6.7\cdot 10^{-3}$$

### Schritt 2 — Partielle Ableitungen

Innere Ableitung beachten ($\frac{\partial}{\partial x}(-(x^2+y^2)) = -2x$):
$$\frac{\partial f}{\partial x} = -2x\,e^{-(x^2+y^2)}, \qquad \frac{\partial f}{\partial y} = -2y\,e^{-(x^2+y^2)}$$

### Schritt 3 — Am Messpunkt einsetzen

$$\frac{\partial f}{\partial x}\Big|_0 = -2\cdot 1\cdot e^{-5} = -2e^{-5}, \qquad \frac{\partial f}{\partial y}\Big|_0 = -2\cdot 2\cdot e^{-5} = -4e^{-5}$$

### Schritt 4 — Absolute Messfehler

$p\,\%$ Ungenauigkeit bedeutet $\Delta = \frac{p}{100}\cdot|\text{Messwert}|$:
$$\Delta x = 0{,}10\cdot 1 = 0{,}1, \qquad \Delta y = 0{,}20\cdot 2 = 0{,}4$$

> [!warning] Stolperstein
> $\Delta y$ ist **nicht** $0{,}2$. Die Ungenauigkeit bezieht sich auf den Messwert $y_0 = 2$, also $\Delta y = 0{,}2\cdot 2 = 0{,}4$.

### Schritt 5 — Maximaler absoluter Fehler (Beträge summieren, Worst Case)

$$\Delta f_{\max} = \left|\frac{\partial f}{\partial x}\Big|_0\right|\Delta x + \left|\frac{\partial f}{\partial y}\Big|_0\right|\Delta y = |-2e^{-5}|\cdot 0{,}1 + |-4e^{-5}|\cdot 0{,}4$$
$$= 0{,}2\,e^{-5} + 1{,}6\,e^{-5} = 1{,}8\,e^{-5}$$

### Schritt 6 — Maximaler relativer Fehler

$$\frac{\Delta f_{\max}}{|f|} = \frac{1{,}8\,e^{-5}}{e^{-5}} = 1{,}8 = \boxed{180\,\%}$$

> [!check] Self-Check / Probe
> Der $e^{-5}$-Faktor kürzt sich beim relativen Fehler vollständig weg → das Ergebnis ist von der Lage des Glockenfunktions-Werts unabhängig, hängt nur an den Ableitungs-Faktoren $2x, 2y$ und den $\Delta$. Stimmt mit der PDF-Musterlösung ($180\,\%$) überein. ✅

> [!note] Interpretation
> $180\,\% > 100\,\%$ ist hier plausibel: Die Dichte fällt im Gauß-Tail extrem steil ab, daher schlagen Messfehler überproportional durch. Der $y$-Term (Beitrag $1{,}6\,e^{-5}$) dominiert — **$y$ am genauesten messen**.

---

## Übung 4.1 — Gradient & Hesse-Matrix ([[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]])

Gradient $\nabla f$ = Spaltenvektor der ersten partiellen Ableitungen, Hesse $\partial^2 f/\partial x\,\partial x^T$ = Matrix der zweiten partiellen Ableitungen (symmetrisch, $H_{ij}=\frac{\partial^2 f}{\partial x_i\partial x_j}$).

### Teil 1 — $f(x_1,x_2) = e^{-(x_1^2 + 2x_2^2)}$

**Gradient.** Innere Ableitungen: $\frac{\partial}{\partial x_1}(-(x_1^2+2x_2^2)) = -2x_1$, $\frac{\partial}{\partial x_2}(\dots) = -4x_2$.
$$\nabla f = \begin{pmatrix} \dfrac{\partial f}{\partial x_1} \\[2mm] \dfrac{\partial f}{\partial x_2} \end{pmatrix} = \begin{pmatrix} -2x_1\,e^{-(x_1^2+2x_2^2)} \\[2mm] -4x_2\,e^{-(x_1^2+2x_2^2)} \end{pmatrix}$$

**Hesse-Matrix.** Mit der Produktregel, Kurzschreibweise $E := e^{-(x_1^2+2x_2^2)}$:

$\dfrac{\partial^2 f}{\partial x_1^2} = \dfrac{\partial}{\partial x_1}\big(-2x_1 E\big) = -2E + (-2x_1)(-2x_1)E = E(-2 + 4x_1^2) = -2E(1-2x_1^2)$

$\dfrac{\partial^2 f}{\partial x_1\partial x_2} = \dfrac{\partial}{\partial x_2}\big(-2x_1 E\big) = -2x_1\cdot(-4x_2)E = 8x_1 x_2 E$

$\dfrac{\partial^2 f}{\partial x_2^2} = \dfrac{\partial}{\partial x_2}\big(-4x_2 E\big) = -4E + (-4x_2)(-4x_2)E = E(-4 + 16x_2^2) = -4E(1-4x_2^2)$

$$\frac{\partial^2 f}{\partial x\,\partial x^T} = \begin{pmatrix} -2e^{-(x_1^2+2x_2^2)}(1-2x_1^2) & 8x_1 x_2\,e^{-(x_1^2+2x_2^2)} \\[2mm] 8x_1 x_2\,e^{-(x_1^2+2x_2^2)} & -4e^{-(x_1^2+2x_2^2)}(1-4x_2^2) \end{pmatrix}$$

> [!check] Self-Check
> Matrix ist symmetrisch (Satz von Schwarz erfüllt). Deckt sich exakt mit der PDF-Musterlösung. ✅

### Teil 2 — $f(x_1,x_2) = 4x_1^3 x_2^2$

**Gradient.** Reine Potenzregel:
$$\nabla f = \begin{pmatrix} \dfrac{\partial f}{\partial x_1} \\[2mm] \dfrac{\partial f}{\partial x_2} \end{pmatrix} = \begin{pmatrix} 12x_1^2 x_2^2 \\[2mm] 8x_1^3 x_2 \end{pmatrix}$$

**Hesse-Matrix.**

$\dfrac{\partial^2 f}{\partial x_1^2} = \dfrac{\partial}{\partial x_1}(12x_1^2 x_2^2) = 24x_1 x_2^2$

$\dfrac{\partial^2 f}{\partial x_1\partial x_2} = \dfrac{\partial}{\partial x_2}(12x_1^2 x_2^2) = 24x_1^2 x_2$

$\dfrac{\partial^2 f}{\partial x_2^2} = \dfrac{\partial}{\partial x_2}(8x_1^3 x_2) = 8x_1^3$

$$\frac{\partial^2 f}{\partial x\,\partial x^T} = \begin{pmatrix} 24x_1 x_2^2 & 24x_1^2 x_2 \\[2mm] 24x_1^2 x_2 & 8x_1^3 \end{pmatrix}$$

> [!check] Self-Check
> Gegenprobe der gemischten Ableitung über den anderen Weg: $\frac{\partial}{\partial x_1}(8x_1^3 x_2) = 24x_1^2 x_2$ — identisch zum Eintrag oben, Symmetrie bestätigt. Deckt sich mit der PDF-Musterlösung. ✅

---

## Merksätze (Stolpersteine)

1. **Prozent-Fehler immer auf den Messwert beziehen:** $\Delta x_i = \frac{p}{100}\cdot|x_i^0|$. Häufigster Fehler in 6.3: $\Delta y = 0{,}4$, nicht $0{,}2$.
2. **Beträge im Worst Case:** Beim max. Fehler jeden Summanden positiv addieren — keine Vorzeichen wegkürzen.
3. **Relativer Fehler kürzt Konstanten:** Bei $e^{-5}$ fällt der Exponentialfaktor komplett raus. Schnelle Plausibilitätsprüfung.
4. **Hesse ist symmetrisch:** gemischte Ableitung über beide Wege rechnen = kostenlose Probe.
5. **Innere Ableitung nicht vergessen** bei $e^{-(\dots)}$: Faktor $-2x$ bzw. $-4x_2$ (wegen des $2x_2^2$).

## Siehe auch

- [[01_Fehlerrechnung_Rezept]] — Kochrezept Gradient/Hesse/Fehlerfortpflanzung
- [[Aufgaben6_Analysis_ImplAbl_Fehlerrechnung.pdf|Blatt 6]] · [[Aufgaben4_Analysis_Ableitungen_mehrdim.pdf|Blatt 4]]
- [[_MOC]]
