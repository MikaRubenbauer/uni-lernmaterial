---
fach: Info
typ: spickzettel
thema: Heap, Heap-Sort & Huffman
tags: [info/algorithmen, info/kodierung, typ/spickzettel, typ/rezept]
klausur: 2026-07-31
status: done
prio: hoch
---

# Info Thema 3 — Heap, Heap-Sort & Huffman (Quellnotiz)

> Primäres Lernmaterial: [[03_Heap-Huffman_Lernskript.html|interaktives Lernskript]] (Heap-Build/-Sort-Trainer + Huffman-Trainer).
> Anschauung: [[03_SortRace_Animation.html|Sort Race]] · [[Huffman-Animation]] (Codebaum) · Restrisiko: [[LZW-Animation (standalone)|LZW]], [[BWT Animation standalone|BWT]] (Ordner `Info/Animations/`, im Lernskript §8 verlinkt).
> Quellen: Prof-Altklausur 2024 A3 (12 P) + A8 (10 P, Figuren aus PDF), [[Theoretische-Informatik-II-Arbeitsheft.pdf|Arbeitsheft]] 65–66 (+ [[Theoretische-Informatik-II-Loesungen-61-70.pdf|Lös. 61–70]]) & 81–86 (Kap. 5, ⚠️ ohne Lösung), Skript Kap. 2.4/3.2/5.2.
> Heap-Zustände, Heap-Sort, Huffman-Codelängen programmatisch verifiziert (Python). Status/Plan: [[_Tracker]] · [[_MOC]].

## Rezepte (Kurzform)

1. **Max-Heap (0-basiert):** Kinder von $i$ = $2i{+}1, 2i{+}2$; Elter = $\lfloor(i{-}1)/2\rfloor$. Jeder Knoten ≥ Kinder.
2. **Build-Max-Heap:** siftDown von $\lfloor n/2\rfloor{-}1$ **rückwärts** bis 0.
3. **Heap-Sort:** Wurzel ↔ letztes Heap-Element (fixieren), Heap verkleinern, siftDown — wiederholen → aufsteigend, in-place.
4. **Huffman:** zwei kleinste Häufigkeiten verschmelzen bis Wurzel; Pfad 0/1 = Code. $H = -\sum p_i\log_2 p_i$; Redundanz $= L - H$ (bzw. $8 - H$ bei 8-Bit-Speicherung).

## Verifizierte Ergebnisse

- **A3b** BFS-Array des Baums = `[1,4,3,5,9,8]`
- **A3c** Build-Max-Heap `[1,4,3,5,9,8]` → `[1,4,8,5,9,3]` → `[1,9,8,5,4,3]` → **`[9,5,8,1,4,3]`**
- **A3d** Heap-Sort `[9,5,8,1,4,3]` → … → **`[1,3,4,5,8,9]`** (alle Zwischenzustände im Lernskript, Abschnitt 4d)
- **A8** Huffman: Codelängen A4 B2 E2 G4 L2 R3 · gewichtete Gesamtlänge **254 Bit** · **ALGEBRA = 21 Bit** · Entropie ≈ 2,27 Bit/Zeichen
- **AH 65** `[2,1,4,6,5,3,7]` → Max-Heap `[7,6,4,1,5,3,2]` · **AH 66** `[1,5,3,4,6,2,7]` → `[7,6,3,4,5,2,1]`

## Verwandt

[[02_AVL_Uebungen|Thema 2 AVL-Bäume]] · [[01_Zahldarstellung_Uebungen|Thema 1 Zahldarstellung]] · Kapitel-Nachbarn: Kap. 3 Algorithmen, Kap. 5 Kodierung.
