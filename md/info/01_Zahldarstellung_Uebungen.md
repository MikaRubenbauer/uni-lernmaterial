---
fach: Info
typ: spickzettel
thema: Zahldarstellung & IEEE-754 half
tags: [info/kodierung, typ/spickzettel, typ/rezept]
klausur: 2026-07-31
status: done
prio: hoch
---

# Info Thema 1 — Zahldarstellung & IEEE-754 (Quellnotiz)

> Primäres Lernmaterial: [[01_Zahldarstellung_Lernskript.html|interaktives Lernskript]] (Umrechnungs-, Zweierkomplement- und IEEE-754-Trainer).
> Quellen: Prof-Altklausur 2024 A2 (15 P), [[Theoretische-Informatik-II-Arbeitsheft.pdf|Arbeitsheft]] 13–20 + [[Theoretische-Informatik-II-Loesungen-13-22.pdf|Lösungen]], Skript Kap. 2.1.
> Alle Werte gegen numpy float16 + Musterlösungen verifiziert (Master-Session 2026-07-02). Status/Plan: [[_Tracker]] · [[_MOC]].

## Rezepte (Kurzform)

1. **Dezimal→Basis b:** Potenz-Schema (Musterlösungs-Stil) bzw. Division mit Rest; Nachkomma ×b-Methode.
2. **Binär↔Oktal/Hex:** 3er-/4er-Gruppen **vom Komma aus**, Ränder mit Nullen füllen.
3. **8-Bit-Zweierkomplement (z₂ₖ):** negativ = 256−|z| binär (oder kippen+1); Rückweg: führende 1 → Wert−256; Addition: Übertrag aus Bit 8 fällt weg. Bereich −128…127.
4. **IEEE-754 half:** v(1) | e(5, Bias 15) | m(10, führende 1 implizit); Rundung „half to even".

## Verifizierte Ergebnisse

- **AH 13:** 29.875₁₀ = 11101.111₂ = 35.7₈ = 1D.E₁₆ · 1A.1₁₆ = 11010.0001₂ = 32.04₈ = 26.0625₁₀
- **AH 14:** 3A.4₁₆ = 58.25₁₀ · 213.21₈ = 139.265625₁₀ = 8B.44₁₆ · 217.4375₁₀ = 331.34₈ = D9.7₁₆
- **AH 15/16:** −68 = 10111100₂ₖ · 90+(−94): 01011010+10100010 = 11111100₂ₖ = −4
- **AH 17/18:** −3.125 → C240₁₆ · 4B40₁₆ → 14.5
- **AH 19/20 (Vertiefung):** 5008·40C0 → 54CA (round half to even auf) · 5C21−4420 → 5C10 (ML-Tippfehler „e=13", korrekt 8+15=23)
- **Klausur 2024 A2:** 117 = 1110101₂ = 165₈ · 0.625 = 0.101₂ · −117.25 → **D754₁₆** · −117.625 exakt darstellbar (9 ≤ 10 Mantissenbits)

## Verwandt

[[02_AVL_Animation_Notiz|Thema 2 AVL-Bäume]] (nächster Lernblock) · Kapitel-Nachbar im Skript: Kap. 2 Datenstrukturen.
