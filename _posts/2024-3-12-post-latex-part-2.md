---
title: "LaTeX - Tabellen: Tipps & Tricks"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Latex
  - deutsch
---

Hier eine kleine Auflistung von Tabellen in Latex.

# 1. Die tabular-Umgebung
Die tabular-Umgebung ist die grundlegende Umgebung zur Erstellung von Tabellen in LaTeX.

```html
\begin{tabular}{|c|c|c|}
    \hline
    A & B & C \\
    \hline
    A1 & B1 & C1 \\
    A2 & B2 & C2 \\
    A3 & B3 & C3 \\
    \hline
\end{tabular}
```

In diesem Beispiel definiert {c|c|c} die Ausrichtung der Spalten (zentriert) und ob vertikale Linien zwischen den Spalten vorhanden sein sollen. \hline wird verwendet, um horizontale Linien einzufügen.

## 1.1 Anpassung von Spaltenbreiten und -ausrichtung
Die Breite und Ausrichtung von Spalten in der tabular-Umgebung kann angepasst werden. Zum Beispiel:

```html
\begin{tabular}{|l|c|r|}
    \hline
    Links ausgerichtet & Zentriert & Rechts ausgerichtet \\
    \hline
    A1 & B1 & C1 \\
    \hline
\end{tabular}
```
In LaTeX-Tabellen kann '@{}' verwendet werden, um den Abstand zwischen den Spalten anzupassen oder zusätzlichen Inhalt zwischen den Spalten hinzuzufügen. Zum Beispiel '{@{}}' entfernt den Abstand zwischen den Spalten, während '{@{\hspace{2em}}}' einen horizontalen Abstand von 2em zwischen den Spalten hinzufügt.

3. Die Spaltenausrichtungen: m, b, X, L, R
`m`: Mitten (vertikal zentriert)
`b`: Unten (vertikal am unteren Rand)
`X`: Dehnbar (automatische Breitenanpassung)
`L`: Links ausgerichtet
`R`: Rechts ausgerichtet

## 1.2 Verwendung von \multirow und \multicolumn
\multirow und \multicolumn sind nützliche Befehle zur Zusammenführung von Zellen über mehrere Zeilen bzw. Spalten:

```html
\begin{tabular}{|c|c|c|}
    \hline
    \multicolumn{2}{|c|}{\multirow{2}{*}{Gesamt}} & Daten 1 \\
    \cline{3-3}
    \multicolumn{2}{|c|}{} & Daten 2 \\
    \hline
\end{tabular}
```

# 2. Die longtable-Umgebung für mehrseitige Tabellen
Für längere Tabellen, die über eine Seite hinausgehen, bietet die longtable-Umgebung eine Lösung:

```html
\begin{longtable}{|c|c|}
    \hline
    Spalte 1 & Spalte 2 \\
    \hline
    \endhead % Kennzeichnet das Ende der Kopfzeile
    Daten 1 & Daten 2 \\
    Daten 3 & Daten 4 \\
    % Weitere Daten
    \hline
\end{longtable}
```

# 3. Die longtabu-Umgebung
Die longtabu-Umgebung ist eine Erweiterung der longtable-Umgebung, die durch das tabu-Paket bereitgestellt wird. Sie bietet zusätzliche Funktionen und Flexibilität beim Erstellen von Tabellen über mehrere Seiten hinweg.

```html
\usepackage{tabu}

\begin{longtabu} to \linewidth {|X[1,c]|X[2,l]|}
    \hline
    Spalte 1 & Spalte 2 \\
    \hline
    \endhead % Ende der Kopfzeile
    Daten 1 & Daten 2 \\
    Daten 3 & Daten 4 \\
    % Weitere Daten
    \hline
\end{longtabu}
```


