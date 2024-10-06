---
title: "LaTeX - Package spreadtab"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Latex
  - deutsch
---

Dieser Artikel beschreibt die Nutzung des LaTeX-Packets spreadtab. <!--more-->

# Verwendung des LaTeX-Pakets `spreadtab`

Das `spreadtab`-Paket ist ein Paket zur Erstellung von Tabellen, in denen einfache arithmetische Berechnungen eingebettet werden können. 

### Erstellen einer einfachen Tabelle mit `spreadtab`

Um `spreadtab` zu benutzen, muss zunächst das Paket geladen werden:

```

```

Nun können Tabellen definiert und Berechnungen einfügt werden. Die Struktur folgt einer typischen `tabular`-Umgebung, aber mit `spreadtab`-Syntax, um automatische Berechnungen zu ermöglichen.

## Beispiel: Eine einfache Tabelle mit Summen

```
\begin{spreadtab}{llll|l}
    & @ Spalte1 & @ Spalte2 & @ Spalte3 & \\
@ Zeile1 & 1 & 2 & 3 & sum(b2:d2) \\
@ Zeile2 & 6 & 5 & 4 & sum(b3:d3) \\
@ Zeile3 & 7 & 8 & 9 & Summe(b4:d4) \\ \hline
    & sum(b2:b4) & sum(c2:c4) & sum(d2:d4) &
\end{spreadtab}
```

### Aufschlüsselung des Beispiels

1. **Kopfzeilen und Beschriftungen:**
    - Die erste Zeile `& @ Spalte1 & @ Spalte2 & @ Spalte3 & \\` definiert die Spaltenüberschriften (`Spalte1`, `Spalte2`, und `Spalte3`).
    - Das Symbol „@“ wird verwendet, um eine Textbeschriftung anzugeben, die nicht berechnet wird.

2. **Daten und Berechnungen:**
    - Jede Zeile beginnt mit einer Bezeichnung (z. B. `@ Zeile1`, `@ Zeile2`, `@ Zeile3`), gefolgt von den Daten für diese Zeile.
    - Am Ende jeder Zeile wird die Funktion „Summe“ verwendet, um die Werte in dieser Zeile zu addieren (z. B. „Summe(b2:d2)“ addiert die Werte in den Spalten „b“, „c“ und „d“ für Zeile 2).

3. **Summenbildung in Spalten:**
    - Nach der horizontalen Linie werden die Spaltensummen wieder mit der Funktion `sum` berechnet (z.B. `sum(b2:b4)` addiert alle Werte der Spalte `b` in den Zeilen 2 bis 4).

### Berechnungsfunktionen

Mittels **sum(range)** werden die Werte in einem bestimmten Bereich addiert. Weitere Funktionalitäten finden sich in der [Doku](https://ftp.rrzn.uni-hannover.de/pub/mirror/tex-archive/macros/latex/contrib/spreadtab/spreadtab-en.pdf)

### Weiteres

- **Zellreferenzen:** Zellen in `spreadtab` werden ähnlich wie in Tabellenkalkulationen referenziert, wobei das Format `b2` sich auf die Zelle in Spalte `b` und Zeile 2 bezieht.
- **Beschriftungen:** Mittels `@` können Textbeschriftungen verwenden werden, die nicht in die Berechnungen einbezogen werden.
- **Ausrichten:** Funktioniert mittels `l`, `c`oder `r`wie bei normalen Tabellen.

### Example Output

Der Output des obigen Beispiels sieht wie folgt aus:

|        | Spalte1 | Spalte2 | Spalte3 | Total |
|--------|-----|-----|-----|-------|
| Zeile1  |  1  |  2  | 3  | 6    |
| Zeile2 |  6 |  5  | 4 | 15    |
| Zeile3  | 7  | 8  | 9  | 24    |
| **Summe**| 14  | 15  | 16  |       |
