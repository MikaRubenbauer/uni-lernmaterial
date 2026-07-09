---
fach: Info
typ: spickzettel
thema: AVL-Bäume
tags: [info/datenstrukturen, typ/spickzettel, typ/rezept]
klausur: 2026-07-31
status: done
prio: hoch
---

# Info Thema 2 — AVL-Bäume (Quellnotiz)

> Primäres Lernmaterial: [[02_AVL_Lernskript.html|interaktives Lernskript]] (AVL-Trainer mit Zwischenzuständen + Rotationslog).
> Anschauung: [[02_AVL-RS_Animation.html|AVL/RS-Animation]].
> Quellen: Prof-Altklausur 2024 A5 (15 P, Bäume aus PDF-Figur), [[Theoretische-Informatik-II-Arbeitsheft.pdf|Arbeitsheft]] 53–60 + [[Theoretische-Informatik-II-Loesungen-47-60.pdf|Lösungen 47–60]], Skript Kap. 2.4.
> Alle Rotationen programmatisch verifiziert (Python-AVL, |BF|≤1 je Zwischenzustand). Status/Plan: [[_Tracker]] · [[_MOC]].

## Rezepte (Kurzform)

1. **AVL-Eigenschaft:** BST + in jedem Knoten $|\mathrm{BF}| \le 1$, mit $\mathrm{BF} = h(\text{links}) - h(\text{rechts})$.
2. **4 Rotationen:** LL → Rechtsrotation · RR → Linksrotation · LR → links(Kind)+rechts · RL → rechts(Kind)+links. Typ am BF des Kindes ablesen.
3. **Einfügen:** BST-einfügen → nach oben BF prüfen → am ersten $|\mathrm{BF}|=2$ rotieren. **Genau eine** (Doppel-)Rotation reicht.
4. **Löschen:** BST-löschen (2 Kinder → **kleinstes Element aus rechtem Teilbaum**) → nach oben rebalancieren. Kann **mehrere** Rotationen auslösen.

## Verifizierte Ergebnisse (Klausur 2024 A5)

- **Baum A** `7(0(·,1),8)` → **+5:** RR/Linksrotation an 0 → `7(1(0,5),8)` · **+4:** LR an 7 → `5(1(0,4),7(·,8))` · **+2:** keine Rotation → **`5(1(0,4(2,·)),7(·,8))`**
- **Baum B** `5(3(·,4),8(6(·,7),9))` → **−4:** RL an 5 → `6(5(3,·),8(7,9))` · **−5:** Ersatz durch linkes Kind → **`6(3,8(7,9))`**
- ⚠️ **Dritter Löschwert „4" ist Reproduktionsfehler** (4 existiert nur einmal) → echten Wert aus eigener Erinnerung klären.

## Verwandt

[[01_Zahldarstellung_Uebungen|Thema 1 Zahldarstellung]] · [[03_Heap-Huffman_Uebungen|Thema 3 Heap/Huffman]] · Kapitel-Nachbar: Kap. 2 Datenstrukturen.
