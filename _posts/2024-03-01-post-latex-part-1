---
title: "LaTeX - eine praktische Einführung: 1"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Latex
  - deutsch
---

LaTeX ist eine markup language für das Schreiben und Layouten von (mathematischen) Texten und Artikeln.  Dieser Artikel ist Teil der Artikelserie "LaTeX - eine praktische Einführung" und soll als Nachschlagewerk für mich dienen. Vielleicht ist es ja hilfreich :) 
<!--mehr-->

## Grundlegendes

- durch `\` wird der Beginn von einem Befehl gekennzeichnet. 
- Parameter werden entweder in `{}`-Klammern, `[]` oder `()` übergeben (nicht alle Befehle benötigen einen Parameter)
- durch `{}` kann der gültige Bereich eines Befehles eingeschränkt werden, z.b. `{ \small }`.
- Umgebungen werden durch `\begin{}` und `\end{}` gekennzeichnet.
- Umgebungen müssen korrekt geschachtelt sein, d.h. eine Umgebung muss entweder komplett in einer anderen enthalten sein, oder komplett außerhalb.

## Dokumentstruktur

- `\documentclass{...}`: Definiert die Dokumentenklasse (z.B. article, book, report).
- `\begin{document}` und `\end{document}`: Begrenzt den Dokumenteninhalt.
- `\title{...}`, `\author{...}` und `\date{...}`: Definiert Titel, Autor und Datum.
- `\maketitle`: Erzeugt die Titelseite.
- `\section{...}`, `\subsection{...}` und `\subsubsection{...}`: Erstellt Abschnitte und Unterabschnitte.

## Textformatierung

- `\textbf{...}` und `\textit{...}`: Macht Text fett bzw. kursiv.
- `\underline{...}`: Unterstreicht Text.
- `\emph{...}`: Betont Text (normalerweise kursiv).
- `\uppercase{...}` und `\lowercase{...}`: Wandelt Text in Groß- bzw. Kleinbuchstaben um.

## Listen

- `\begin{enumerate}` und `\end{enumerate}`: Erstellt eine nummerierte Liste.
- `\begin{itemize}` und `\end{itemize}`: Erstellt eine Aufzählungsliste mit Symbolen.
- `\item`: Fügt einen neuen Listeneintrag hinzu.

## Mathematische Formeln

- `$....$` oder `\(...\)`: Für eingebettete Formeln.
- `\begin{equation}` und `\end{equation}`: Für nummerierte Gleichungen.
- `\frac{...}{...}`: Erstellt einen Bruch.
- `\sqrt{...}`: Erzeugt eine Quadratwurzel.

## Referenzen und Zitate

- `\label{...}`: Erstellt eine Referenz.
- `\ref{...}`: Verweist auf eine Referenz.
- `\cite{...}`: Zitiert eine Quelle aus der Bibliographie.
- `\bibliography{...}`: Fügt die Bibliographie ein.

## Grafiken und Tabellen

- `\includegraphics[options]{filename}`: Fügt eine Grafik ein. Mögliche Optionen sind z.B. `width=\linewidth` (Breite der Grafik), `height=5cm` (Höhe der Grafik), `angle=90` (Rotation der Grafik) und `scale=0.5` (Skalierung der Grafik).
- `\begin{figure}[placement]` und `\end{figure}`: Umschließt eine Grafik und erstellt eine Bildunterschrift. Mögliche Platzierungsoptionen sind `h` (hier), `t` (oben), `b` (unten) und `p` (Sonderseite).
- `\caption{...}`: Erstellt eine Bildunterschrift innerhalb eines `figure`-Umgebung.
- `\begin{table}[placement]` und `\end{table}`: Umschließt eine Tabelle. Mögliche Platzierungsoptionen sind `h` (hier), `t` (oben), `b` (unten) und `p` (Sonderseite).
- `\begin{tabular}{cols}` und `\end{tabular}`: Erstellt eine Tabelle. `cols` definiert die Spaltenausrichtung, z.B. `l` (links), `c` (zentriert) und `r` (rechts).
- `\hline`: Erzeugt eine horizontale Linie in einer Tabelle.
- `\\`: Erzwingt einen Zeilenumbruch in einer Tabelle.
- `\multicolumn{n}{cols}{text}`: Verschmilzt `n` Spalten und richtet den Text entsprechend `cols` aus.

Mit diesen Befehlen können Grafiken und Tabellen in LaTeX-Dokumente eingefügt und angepasst werden. Die Platzierung und Größe lässt sich steuern, und Beschriftungen hinzufügen. Zu Tabellen wirds noch mehr geben. 
