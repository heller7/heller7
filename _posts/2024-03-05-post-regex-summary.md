---
title: "RegEx - Syntax und Beispiel"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - RegEx
  - deutsch
---

# RegEx-Befehle

Im folgenden erst eine (nicht vollständige) Auflistung der Syntax, danach ein paar Beispiele, die ich hilfreich fand. 

## Grundlegendes
- `.`: jeden beliebigen Einzelzeichenausdruck außer Zeilenumbruch
- `\d`: eine Ziffer (0-9)
- `\D`: jeden beliebigen Nicht-Ziffernausdruck
- `\w`: Wortzeichen (a-z, A-Z, 0-9, _)
- `\W`: Nicht-Wortzeichen
- `\s`: Whitespace-Zeichen (Leerzeichen, Tabulator, Zeilenumbruch)
- `\S`: Nicht-Whitespace-Zeichen
- `\b`: eine Wortgrenze
- `^`: den Anfang einer Zeichenkette
- `$`: das Ende einer Zeichenkette

## Zeichenklassen
- `[a-z]`: Ein beliebiges kleingeschriebenes Buchstaben von a bis z.
- `[A-Z]`: Ein beliebiges großgeschriebenes Buchstaben von A bis Z.
- `[0-9]`: Eine beliebige Ziffer von 0 bis 9.
- `[a-zA-Z]`: Ein beliebiger Buchstabe, sowohl klein- als auch großgeschrieben.
- `[a-zA-Z0-9]`: Ein beliebiger Buchstabe oder eine beliebige Ziffer.

## Quantifizierer
- `?` 0 oder 1 Vorkommen des vorhergehenden Elements.
- `*` 0 oder mehr Vorkommen des vorhergehenden Elements.
- `+` 1 oder mehr Vorkommen des vorhergehenden Elements.
- `{2}` exakt 2 Vorkommendes vorhergehenden Elements.
- `{2,4}` 2 bis 4 Vorkommen des vorhergehenden Elements.
- `{2,}` 2 oder mehr Vorkommen des vorhergehenden Elements.

## Gruppierung und Alternativen
- `(abc)` Gruppiert Ausdrücke in Klammern
- `(abc|def)` Matcht abc oder def


# Beispiele
Folgende Beispiele habe ich in der Vergangenheit genutzt und/oder fand sie hilfreich.

## Testen auf eine gültige Email-Adresse
`/^[\w.%+-]+@[\w.-]+\.[a-zA-Z]{2,}$/`

`^` matcht den Anfang der Zeichenkette. `[\w.%+-]+` erlaubt Wortzeichen, Punkte, Prozentzeichen, Pluszeichen und Minuszeichen vor dem @-Zeichen. `@` matcht das @-Zeichen. `[\w.-]+` Erlaubt Wortzeichen, Punkte und Bindestriche nach dem @-Zeichen`\.` matcht einen Punkt (Achtung: Mit einem Backslash, da der Punkt ein eigene Funktionalität hat). `[a-zA-Z]{2,}` matcht mindestens zwei Buchstaben (die Top-Level-Domain). `$` matcht das Ende der Zeichenkette.
